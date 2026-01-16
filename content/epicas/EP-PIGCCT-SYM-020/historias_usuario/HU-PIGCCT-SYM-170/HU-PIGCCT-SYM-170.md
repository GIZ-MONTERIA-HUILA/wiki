# HU-PIGCCT-SYM-170  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Navegación basada en roles

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** que el sistema muestre u oculte las opciones del menú según mi rol.  
> **Para:** garantizar el control de acceso a las funcionalidades del sistema y una experiencia de navegación acorde a mis responsabilidades.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Roles del sistema
1.1 El sistema debe manejar como mínimo los siguientes roles:
- **Usuario registrador**.  
- **Usuario validador entidad**.  
- **Usuario validador CAR**.  
- **Usuario administrador**.  
- **Usuario consulta**.

1.2 Cada rol debe contar con un conjunto de permisos definidos y configurables.


### 2. Visualización de opciones del menú
2.1 El sistema debe mostrar en el menú principal **únicamente las opciones permitidas** para el rol del usuario autenticado.  
2.2 Las opciones no autorizadas:
- No deben ser visibles en el menú.
- No deben ser accesibles por navegación directa mediante URL.


### 3. Configuración de permisos por rol
3.1 El sistema debe permitir definir y mantener una **matriz de permisos** que relacione:
- Rol.
- Módulo.
- Funcionalidad o acción.

3.2 Esta configuración debe ser gestionada por usuarios con rol **administrador**.


### 4. Comportamiento dinámico
4.1 El menú debe adaptarse dinámicamente al rol del usuario autenticado al iniciar sesión.  
4.2 Si el rol o permisos del usuario cambian:
- El sistema debe actualizar las opciones visibles del menú.
- Los cambios deben reflejarse sin requerir reinicio del sistema.


### 5. Control de acceso y seguridad
5.1 El sistema debe implementar validaciones de seguridad tanto en:
- Capa de presentación (ocultamiento de opciones).
- Capa de backend (restricción de acceso).

5.2 El acceso a una funcionalidad no autorizada debe:
- Ser bloqueado.
- Generar un mensaje de acceso no permitido.


### 6. Navegación coherente por rol
6.1 La estructura del menú debe ser coherente y consistente para cada rol.  
6.2 El sistema debe evitar mostrar opciones que no correspondan al contexto o responsabilidades del rol.


### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar:
- Cambios en la configuración de permisos por rol.
- Usuario que realizó el cambio.
- Fecha y hora del evento.

7.2 Esta información debe estar disponible para fines de auditoría y control institucional.


### 8. Usabilidad y experiencia de usuario
8.1 El menú debe facilitar una experiencia de navegación clara y sencilla para cada rol.  
8.2 El usuario debe poder identificar fácilmente las funcionalidades a las que tiene acceso.  
8.3 El sistema debe reducir el ruido visual ocultando opciones no relevantes.

---

### Resultado esperado

El sistema **garantiza una navegación basada en roles**, mostrando únicamente las opciones del menú autorizadas para cada tipo de usuario, reforzando el control de acceso, la seguridad y una experiencia de usuario clara y coherente dentro del sistema PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-170.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-170.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-170.png)
