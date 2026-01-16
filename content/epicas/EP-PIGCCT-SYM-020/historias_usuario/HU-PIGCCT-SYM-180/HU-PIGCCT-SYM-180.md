# HU-PIGCCT-SYM-180  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Enviar acción a validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado con permisos de registro.  
> **Quiero:** enviar una acción del PIGCCT a validación.  
> **Para:** iniciar el proceso formal de revisión institucional, asegurando que la información quede bloqueada y lista para evaluación.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la opción de envío a validación
1.1 El sistema debe permitir la opción **“Enviar a validación”** únicamente a usuarios con permisos de registro.  
1.2 La opción debe estar disponible desde:
- El listado de acciones.
- La vista de detalle de la acción.

1.3 El sistema no debe mostrar la opción a usuarios sin permisos.

### 2. Estados permitidos para el envío
2.1 El sistema debe permitir enviar a validación únicamente acciones que se encuentren en los siguientes estados:
- **Borrador**.
- **Rechazada**.

2.2 Las acciones en otros estados no deben poder enviarse a validación.

### 3. Validaciones previas al envío
3.1 Antes de permitir el envío, el sistema debe validar que:
- Todos los campos obligatorios estén diligenciados.
- No existan errores de validación en ninguna sección del formulario.

3.2 Si existen inconsistencias:
- El sistema debe bloquear el envío.
- Debe mostrar un mensaje indicando los campos pendientes o inválidos.

### 4. Cambio de estado de la acción
4.1 Al confirmar el envío, el sistema debe cambiar el estado de la acción a **En validación**.  
4.2 El cambio de estado debe registrarse automáticamente en el sistema.  
4.3 El nuevo estado debe reflejarse inmediatamente en el listado y vistas relacionadas.

### 5. Bloqueo de edición
5.1 Una vez la acción se encuentre en estado **En validación**:
- La edición de la información debe quedar bloqueada.
- Los campos del formulario deben mostrarse en modo solo lectura.

5.2 El sistema no debe permitir modificaciones mientras la acción esté en proceso de validación.

### 6. Confirmación del envío
6.1 Antes de completar el envío, el sistema debe solicitar confirmación explícita al usuario.  
6.2 El mensaje de confirmación debe advertir que:
- La acción no podrá ser editada durante la validación.

### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar automáticamente:
- Usuario que realizó el envío.
- Fecha y hora del envío.
- Estado anterior y nuevo estado.

7.2 Esta información debe quedar disponible para fines de auditoría y control.

### 8. Usabilidad y experiencia de usuario
8.1 El proceso de envío a validación debe ser claro y sencillo.  
8.2 El sistema debe mostrar mensajes de confirmación exitosos o de error, según corresponda.  
8.3 El usuario debe poder identificar fácilmente el estado de la acción luego del envío.

---

## Resultado esperado

El usuario puede **enviar una acción del PIGCCT a validación**, cambiando su estado a *En validación* y bloqueando la edición de la información, garantizando que la acción quede lista para el proceso formal de revisión institucional con trazabilidad y control.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-180.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-180.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-180.png)
