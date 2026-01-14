# HU-PIGCCT-SYM-135  
## Épica: Autenticación, gestión de usuarios, y control de acceso del sistema PIGCCT  
### Asignar roles al usuario

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** asignar roles y permisos a los usuarios.  
> **Para:** controlar el acceso a las funcionalidades de la aplicación y garantizar que cada usuario solo pueda realizar las operaciones correspondientes a su función institucional.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Concepto de roles
1.1 El sistema debe implementar **control de acceso basado en roles (RBAC - Role-Based Access Control)**.  
1.2 Cada rol define un conjunto de permisos y funcionalidades que el usuario puede ejecutar.  
1.3 Los roles deben estar definidos en **Strapi** y ser sincronizados con el backend del sistema PIGCCT.

### 2. Asignación de rol al crear usuario
2.1 Durante la creación de usuario (HU-133), el administrador debe asignar obligatoriamente al menos un rol.  
2.2 El sistema debe mostrar una lista de roles disponibles para selección.  
2.3 La lista debe incluir descripción breve de cada rol y sus funciones principales.

### 3. Lista de roles disponibles
3.1 El sistema debe cargar los roles desde Strapi mediante su API:
```
GET /api/users-permissions/roles
```

3.2 Los roles mostrados deben estar activos y disponibles para asignación.

### 4. Selección de rol único o múltiple
4.1 El sistema debe permitir asignar **un solo rol principal** por usuario (recomendado para simplicidad).  
4.2 Opcionalmente, puede soportar **múltiples roles** si la política institucional lo requiere.  
4.3 Si se permiten roles múltiples, el sistema debe aplicar la **unión de permisos** de todos los roles asignados.

### 5. Roles del sistema PIGCCT
5.1 El sistema debe tener definidos los siguientes roles estándar (ver HU-136 para detalle completo):
- **Usuario registrador**: Crea y actualiza información, genera eventos de validación
- **Usuario validador de entidad**: Valida información registrada por su entidad
- **Usuario validador CAR**: Valida información aprobada por las entidades
- **Administrador del sistema**: Administra catálogos, usuarios y parámetros
- **Usuario consulta**: Acceso de solo lectura a información validada

5.2 Cada rol debe estar configurado en Strapi con sus permisos correspondientes.

### 6. Modificación de roles
6.1 El administrador del sistema debe poder **cambiar el rol** de un usuario existente.  
6.2 Al cambiar el rol, el sistema debe:
- Solicitar confirmación explícita
- Mostrar advertencia sobre cambio de permisos
- Actualizar el rol en Strapi
- Actualizar permisos del usuario en el sistema
- Invalidar sesiones activas del usuario (requerir nuevo inicio de sesión)

6.3 El cambio debe registrarse en logs de auditoría.

### 7. Permisos asociados a roles
7.1 Cada rol debe definir permisos sobre:
- **Entidades/Tablas**: Cuáles puede consultar, crear, editar, eliminar
- **Funcionalidades**: Qué módulos y opciones del sistema puede acceder
- **Operaciones especiales**: Validar, aprobar, administrar, exportar, etc.

7.2 Los permisos deben estar configurados en Strapi y consultarse al iniciar sesión.

### 8. Contexto de rol en la sesión
8.1 Al iniciar sesión, el sistema debe incluir información del rol en el **token JWT** o contexto de usuario:
```json
{
  "user": {
    "id": 123,
    "username": "usuario",
    "role": {
      "id": 5,
      "name": "Usuario Registrador",
      "type": "registrador",
      "permissions": {...}
    }
  }
}
```

8.2 Esta información debe validarse en cada petición al backend.

### 9. Validación de permisos en el backend
9.1 El backend debe validar el rol y permisos del usuario antes de ejecutar cualquier operación.  
9.2 Si el usuario no tiene permisos, debe retornar:
- Código HTTP 403 Forbidden
- Mensaje: "No tienes permisos para realizar esta acción"
- Registro del intento en logs de seguridad

### 10. Restricciones por rol
10.1 El sistema debe implementar las siguientes restricciones según el rol (ver HU-137 para detalle):

**Usuario Registrador**:
- Puede crear y editar acciones, indicadores, valores
- No puede validar eventos
- Solo ve información de su entidad

**Usuario Validador de Entidad**:
- Puede validar eventos de su entidad
- No puede crear acciones
- No puede validar sus propios registros

**Usuario Validador CAR**:
- Puede validar eventos ya aprobados por entidades
- Ve información de múltiples entidades bajo su jurisdicción
- No puede crear acciones

**Administrador del Sistema**:
- Acceso completo a todas las funcionalidades
- Puede administrar usuarios, roles y catálogos
- Ve información de todas las entidades

**Usuario Consulta**:
- Solo lectura de información validada
- No puede crear, editar ni validar
- Puede exportar reportes

### 11. Interfaz según rol
11.1 El frontend debe adaptar la interfaz según el rol del usuario:
- Mostrar solo las opciones de menú disponibles para ese rol
- Deshabilitar botones de acciones no permitidas
- Ocultar funcionalidades restringidas

11.2 Esto mejora la experiencia de usuario evitando opciones inaccesibles.

### 12. Consulta de usuarios por rol
12.1 El sistema debe permitir al administrador consultar usuarios por rol.  
12.2 Debe mostrar:
- Cantidad de usuarios por cada rol
- Lista detallada de usuarios de un rol específico
- Distribución de roles por entidad

### 13. Restricción de asignación de roles
13.1 El sistema debe validar que ciertos roles solo puedan asignarse bajo condiciones específicas:
- **Validador CAR**: Solo a usuarios de entidades tipo CAR
- **Administrador**: Con aprobación especial o restricción numérica

13.2 Mostrar mensaje de error si se intenta asignación inválida.

### 14. Herencia de permisos
14.1 Opcionalmente, el sistema puede implementar jerarquía de roles donde roles superiores heredan permisos de roles inferiores.  
14.2 Ejemplo: Administrador hereda todos los permisos de Registrador + Validador + propios.

### 15. Roles temporales
15.1 Opcionalmente, el sistema puede permitir asignar roles de forma temporal:
- Con fecha de inicio y fin
- Automáticamente revocados al expirar
- Útil para reemplazos o colaboraciones temporales

### 16. Notificación de cambio de rol
16.1 Cuando se cambia el rol de un usuario, el sistema debe:
- Notificar al usuario por correo electrónico
- Explicar el nuevo rol y sus permisos
- Indicar fecha efectiva del cambio
- Proporcionar contacto de soporte si tiene dudas

### 17. Auditoría de asignación de roles
17.1 El sistema debe registrar en logs:
- Asignación inicial de rol al crear usuario
- Cambios de rol de un usuario
- Administrador que realizó el cambio
- Fecha y hora
- Rol anterior y nuevo rol
- Justificación (opcional)

### 18. Sincronización con Strapi
18.1 El sistema debe mantener sincronización entre:
- Roles definidos en Strapi
- Roles utilizados en el backend del sistema PIGCCT
- Permisos aplicados en el frontend

18.2 Cualquier cambio en configuración de roles en Strapi debe reflejarse en el sistema.

### 19. Documentación de roles
19.1 El sistema debe incluir documentación accesible que explique:
- Cada rol disponible
- Permisos y funcionalidades de cada rol
- Casos de uso apropiados para cada rol
- Proceso para solicitar cambio de rol

### 20. Testing de permisos
20.1 El administrador debe poder "simular" ser un usuario con cierto rol para verificar permisos.  
20.2 Esto facilita pruebas de configuración de roles sin necesidad de crear usuarios de prueba.

---

### Resultado esperado

Cada usuario del sistema tiene **uno o más roles asignados** que determinan sus permisos de acceso a funcionalidades, con control implementado en Strapi, validación en backend, adaptación de interfaz en frontend, y registro completo de auditoría de asignaciones y cambios de roles.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-135.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-135.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-135.png)
