# HU-PIGCCT-SYM-184  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Rechazar acción con observaciones

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario validador.  
> **Quiero:** rechazar una acción del PIGCCT registrando observaciones obligatorias.  
> **Para:** retroalimentar al usuario registrador, indicando los ajustes requeridos antes de una nueva validación.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al rechazo de acciones
1.1 El sistema debe permitir la opción **“Rechazar acción”** únicamente a usuarios con rol de **validador** (entidad o CAR) y **administrador**.  
1.2 La opción debe estar disponible desde:
- El listado de acciones pendientes de validación.
- La vista de detalle de la acción.

1.3 El sistema no debe permitir el rechazo a usuarios sin permisos.

### 2. Estados permitidos para el rechazo
2.1 El sistema debe permitir rechazar únicamente acciones que se encuentren en estado **En validación**.  
2.2 Las acciones en otros estados no deben poder rechazarse.

### 3. Registro de observaciones obligatorias
3.1 Al rechazar una acción, el sistema debe requerir el diligenciamiento obligatorio del campo **Observaciones**.  
3.2 El sistema no debe permitir completar el rechazo si las observaciones no han sido registradas.

### 4. Cambio de estado de la acción
4.1 Al confirmar el rechazo, el sistema debe cambiar el estado de la acción a **Rechazada**.  
4.2 El cambio de estado debe reflejarse inmediatamente en:
- El listado de acciones.
- El historial de la acción.

### 5. Retroalimentación al registrador
5.1 El sistema debe garantizar que las observaciones registradas:
- Sean visibles para el usuario registrador.
- Se muestren al momento de editar la acción.

5.2 Las observaciones deben orientar claramente los ajustes requeridos.

### 6. Confirmación del rechazo
6.1 Antes de completar el rechazo, el sistema debe solicitar confirmación explícita al usuario.  
6.2 El mensaje de confirmación debe advertir que la acción quedará en estado **Rechazada**.

### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar automáticamente:
- Usuario que realizó el rechazo.
- Fecha y hora del evento.
- Observaciones registradas.
- Estado anterior y nuevo estado.

7.2 Esta información debe quedar disponible para fines de auditoría y control institucional.

### 8. Control de acceso y seguridad
8.1 El sistema debe garantizar que solo usuarios autorizados puedan rechazar acciones.  
8.2 El acceso a la funcionalidad por navegación directa debe estar bloqueado para usuarios no autorizados.

### 9. Usabilidad y experiencia de usuario
9.1 El proceso de rechazo debe ser claro y guiado.  
9.2 El sistema debe mostrar mensajes de confirmación y error claros.  
9.3 El usuario debe poder identificar fácilmente el resultado del rechazo.

---

## Resultado esperado

El usuario validador puede **rechazar una acción del PIGCCT**, registrando observaciones obligatorias que retroalimentan al usuario registrador, cambiando el estado de la acción y garantizando la trazabilidad y control del proceso de revisión institucional.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-184.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-184.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-184.png)
