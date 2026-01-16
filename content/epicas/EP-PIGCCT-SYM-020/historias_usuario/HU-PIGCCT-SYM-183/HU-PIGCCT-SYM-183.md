# HU-PIGCCT-SYM-183  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Validar acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario validador.  
> **Quiero:** validar una acción del PIGCCT.  
> **Para:** aprobar formalmente la acción, dejando registro de la decisión, la fecha, el usuario responsable y las observaciones correspondientes.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la validación de acciones
1.1 El sistema debe permitir la opción **“Validar acción”** únicamente a usuarios con rol de **validador** (entidad o CAR) y **administrador**.  
1.2 La opción debe estar disponible desde:
- El listado de acciones pendientes de validación.
- La vista de detalle de la acción.

1.3 El sistema no debe permitir la validación a usuarios sin permisos.

### 2. Estados permitidos para validación
2.1 El sistema debe permitir validar únicamente acciones que se encuentren en estado **En validación**.  
2.2 Las acciones en otros estados no deben poder validarse.

### 3. Registro de la validación
3.1 Al validar una acción, el sistema debe permitir registrar:
- **Fecha de validación** (automática).
- **Usuario validador** (automático).
- **Observaciones de la validación** (opcional u obligatorio según reglas definidas).

3.2 El sistema debe almacenar esta información como parte del historial de la acción.

### 4. Cambio de estado de la acción
4.1 Al confirmar la validación, el sistema debe cambiar el estado de la acción a **Validada** o al estado definido según el flujo de validación.  
4.2 El cambio de estado debe reflejarse inmediatamente en:
- El listado de acciones.
- El historial de la acción.

### 5. Confirmación de la validación
5.1 Antes de completar la validación, el sistema debe solicitar confirmación explícita al usuario.  
5.2 El mensaje de confirmación debe indicar que la acción quedará aprobada y continuará en el flujo correspondiente.

### 6. Auditoría y trazabilidad
6.1 El sistema debe registrar automáticamente:
- Usuario que realizó la validación.
- Fecha y hora del evento.
- Estado anterior y nuevo estado.

6.2 Esta información debe estar disponible para fines de auditoría y control institucional.

### 7. Control de acceso y seguridad
7.1 El sistema debe garantizar que solo usuarios autorizados puedan validar acciones.  
7.2 El acceso a la validación por navegación directa debe estar bloqueado para usuarios no autorizados.

### 8. Usabilidad y experiencia de usuario
8.1 El proceso de validación debe ser claro y sencillo.  
8.2 El sistema debe mostrar mensajes de confirmación exitosos o de error, según corresponda.  
8.3 El usuario debe poder identificar fácilmente el resultado de la validación.

---

## Resultado esperado

El usuario validador puede **validar correctamente una acción del PIGCCT**, registrando la fecha, el usuario responsable y las observaciones, cambiando su estado dentro del flujo institucional y garantizando la trazabilidad y control del proceso de aprobación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-183.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-183.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-183.png)
