# HU-PIGCCT-SYM-134  
## Épica: Autenticación, gestión de usuarios, y control de acceso del sistema PIGCCT  
### Asignar entidad al usuario

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** asignar una entidad específica a cada usuario.  
> **Para:** controlar el ámbito institucional de su operación y garantizar que solo acceda y gestione información de su entidad.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Obligatoriedad de la entidad
1.1 Todo usuario del sistema **debe pertenecer a una y solo una entidad**.  
1.2 No debe ser posible crear un usuario sin asignarle una entidad.  
1.3 La entidad es un atributo fundamental que condiciona el comportamiento del sistema para ese usuario.

### 2. Catálogo de entidades
2.1 El sistema debe mantener un **catálogo maestro de entidades** que incluya:
- Corporaciones Autónomas Regionales (CARs)
- Municipios
- Departamentos
- Entidades del gobierno nacional
- Otras entidades participantes del PIGCCT

2.2 El catálogo debe ser administrable por usuarios con rol de administrador del sistema.

### 3. Selección de entidad al crear usuario
3.1 Durante la creación de usuario (HU-133), el administrador debe seleccionar la entidad desde una lista desplegable.  
3.2 La lista debe mostrar:
- Nombre completo de la entidad
- Tipo de entidad (CAR, Municipio, Departamento, etc.)
- Código o identificador si aplica

3.3 La lista debe permitir búsqueda/filtrado para facilitar la selección.

### 4. Información de la entidad
4.1 El catálogo de entidades debe incluir:
- **Nombre oficial**: Nombre completo de la entidad
- **Tipo de entidad**: Clasificación institucional
- **Código**: Identificador único (ej: código DIVIPOLA para municipios)
- **Departamento/Región**: Ubicación geográfica
- **Estado**: Activa/Inactiva
- **Información de contacto**: Dirección, teléfono, correo institucional

### 5. Condiciona visibilidad de información
5.1 La entidad asignada al usuario determina **qué información puede ver**:
- Un usuario de una CAR solo ve información de entidades bajo su jurisdicción
- Un usuario de un municipio solo ve información de su municipio
- Un validador de entidad solo valida información de su propia entidad

5.2 Esta restricción se aplica automáticamente en todas las consultas del sistema.

### 6. Condiciona flujo de validación
6.1 La entidad determina el **flujo de validación** de eventos:
- Los eventos generados por un usuario se asignan a validadores de su misma entidad
- Solo validadores de la entidad correspondiente pueden validar eventos de esa entidad
- El validador CAR valida eventos de entidades bajo su jurisdicción regional

6.2 El sistema debe verificar la entidad al asignar eventos a validadores.

### 7. Modificación de entidad
7.1 El administrador del sistema debe poder **cambiar la entidad** de un usuario existente.  
7.2 Al cambiar la entidad, el sistema debe:
- Solicitar confirmación explícita
- Mostrar advertencia sobre las implicaciones del cambio
- Registrar el cambio en logs de auditoría
- Actualizar los permisos de acceso del usuario automáticamente

7.3 El cambio debe aplicarse inmediatamente o en el siguiente inicio de sesión del usuario.

### 8. Impacto en permisos de acceso
8.1 La entidad asignada afecta los permisos de acceso a:
- **Acciones del PIGCCT**: Solo las de su entidad
- **Indicadores**: Solo los asociados a acciones de su entidad
- **Eventos de validación**: Solo los de su entidad (para validadores)
- **Reportes**: Filtrados automáticamente por su entidad

8.2 El sistema debe aplicar estos filtros en todas las operaciones de lectura.

### 9. Validación de coherencia
9.1 El sistema debe validar la coherencia entre:
- Entidad del usuario y entidad de las acciones que crea
- Entidad del validador y entidad de los eventos que valida
- Entidad del usuario y entidades que puede consultar

9.2 Si hay inconsistencia, el sistema debe rechazar la operación.

### 10. Consulta de usuarios por entidad
10.1 El sistema debe permitir al administrador consultar todos los usuarios de una entidad específica.  
10.2 Debe mostrar:
- Lista de usuarios de la entidad
- Roles asignados a cada usuario
- Estado (activo/inactivo)
- Última fecha de acceso

### 11. Entidad en el contexto del usuario
11.1 Al iniciar sesión, el sistema debe incluir la información de entidad en el **contexto del usuario**:
```json
{
  "user": {
    "id": 123,
    "username": "usuario",
    "email": "usuario@entidad.gov.co",
    "role": "registrador",
    "entidad": {
      "id": 45,
      "nombre": "CAR Huila",
      "tipo": "CAR",
      "codigo": "HUI"
    }
  }
}
```

11.2 Esta información debe estar disponible en todas las sesiones del usuario.

### 12. Filtrado automático de datos
12.1 El sistema debe aplicar filtros automáticos en las consultas según la entidad del usuario:
```sql
SELECT * FROM accion 
WHERE entidad_id = [entidad_del_usuario]
  AND validado_por_entidad = true 
  AND validado_por_car = true
```

12.2 Este filtro debe aplicarse en el backend, no depender del frontend.

### 13. Restricciones para validadores CAR
13.1 Los usuarios con rol de **validador CAR** pueden tener acceso a múltiples entidades dentro de su región.  
13.2 El sistema debe permitir configurar el ámbito regional del validador CAR.  
13.3 El validador CAR ve información de todas las entidades bajo su jurisdicción.

### 14. Transferencia de registros entre entidades
14.1 Si un registro necesita transferirse a otra entidad (caso excepcional), el sistema debe:
- Requerir aprobación de administrador
- Registrar la transferencia en auditoría
- Notificar a ambas entidades
- Actualizar los eventos asociados

14.2 Esta funcionalidad debe estar altamente restringida.

### 15. Estadísticas por entidad
15.1 El sistema debe mantener estadísticas por entidad:
- Número de usuarios activos
- Número de acciones registradas
- Número de eventos pendientes de validación
- Estado de avance del PIGCCT

15.2 Estas estadísticas deben estar disponibles para reportes gerenciales.

### 16. Desactivación de entidad
16.1 Si una entidad se desactiva en el catálogo, el sistema debe:
- Bloquear automáticamente a todos los usuarios de esa entidad
- Notificar al administrador del sistema
- Mantener los datos históricos intactos
- Permitir reactivación futura

### 17. Identificación visual de entidad
17.1 En la interfaz de usuario, el sistema debe mostrar claramente:
- Nombre de la entidad del usuario en el header o perfil
- Logo de la entidad (si está disponible)
- Indicador de que la información mostrada está filtrada por entidad

17.2 Esto ayuda al usuario a tener contexto de su ámbito de operación.

### 18. Notificaciones por entidad
18.1 Las notificaciones del sistema deben respetar el ámbito de entidad:
- Un usuario solo recibe notificaciones relevantes para su entidad
- Los validadores reciben notificaciones de eventos de su entidad
- Los administradores pueden configurar notificaciones globales

### 19. Auditoría de asignación
19.1 El sistema debe registrar en logs:
- Asignación inicial de entidad al crear usuario
- Cambios de entidad de un usuario
- Administrador que realizó el cambio
- Fecha y hora
- Justificación del cambio (opcional)

---

### Resultado esperado

Cada usuario del sistema tiene **una entidad asignada obligatoriamente** que determina su ámbito de operación, la información que puede visualizar y gestionar, el flujo de validación aplicable, y los permisos de acceso específicos, garantizando segregación institucional correcta y control de acceso apropiado en el sistema PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-134.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-134.png)
