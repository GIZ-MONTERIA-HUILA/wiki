# HU-PIGCCT-SYM-191  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Gestionar usuarios

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** gestionar los usuarios del sistema, sus roles y estados de acceso.  
> **Para:** administrar de forma segura quién puede ingresar al sistema PIGCCT y qué funcionalidades puede utilizar.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la gestión de usuarios
1.1 El sistema debe permitir el acceso al módulo **Gestión de usuarios** únicamente a usuarios con rol **administrador**.  
1.2 El acceso debe estar disponible desde el menú principal, dentro del módulo de **Administración**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos administrativos.

### 2. Visualización del listado de usuarios
2.1 El sistema debe mostrar un **listado de usuarios registrados**.  
2.2 El listado debe incluir como mínimo la siguiente información:
- Nombre del usuario.  
- Correo electrónico.  
- Rol asignado.  
- Estado de acceso (activo / inactivo).  

2.3 El listado debe cargarse correctamente al acceder al módulo.

### 3. Creación de usuarios
3.1 El sistema debe permitir al administrador **crear nuevos usuarios**.  
3.2 Durante la creación, el sistema debe permitir asignar:
- Rol del usuario.
- Estado inicial de acceso.

3.3 El sistema debe validar que el correo electrónico sea único.

### 4. Edición de usuarios
4.1 El administrador debe poder **editar la información de un usuario existente**.  
4.2 Debe ser posible modificar:
- Rol asignado.
- Estado de acceso.

4.3 El sistema debe registrar los cambios realizados.

### 5. Gestión de roles
5.1 El sistema debe permitir asignar y actualizar los **roles del usuario**, tales como:
- Registrador.
- Validador entidad.
- Validador CAR.
- Administrador.
- Consulta.

5.2 El sistema debe aplicar inmediatamente los cambios de rol.

### 6. Estados de acceso
6.1 El sistema debe permitir definir el **estado de acceso** del usuario:
- Activo.
- Inactivo.

6.2 Los usuarios inactivos:
- No deben poder iniciar sesión.
- Deben conservar su información histórica.

### 7. Control de acceso y seguridad
7.1 El sistema debe aplicar validaciones de seguridad para garantizar que solo usuarios autorizados puedan acceder al sistema.  
7.2 El acceso a funcionalidades debe depender del rol y estado del usuario.

### 8. Auditoría y trazabilidad
8.1 El sistema debe registrar automáticamente:
- Usuario administrador que realizó la acción.
- Fecha y hora.
- Tipo de operación (creación, edición, cambio de rol, activación/inactivación).

8.2 Esta información debe estar disponible para fines de auditoría y control institucional.

### 9. Usabilidad y experiencia de usuario
9.1 La gestión de usuarios debe ser clara y fácil de usar.  
9.2 El sistema debe mostrar mensajes claros de confirmación o error.  
9.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El administrador puede **gestionar de forma segura los usuarios del sistema PIGCCT**, controlando roles y estados de acceso, garantizando la correcta asignación de permisos, la seguridad del sistema y la trazabilidad de todas las operaciones administrativas.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-191.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-191.png)


