# HU-PIGCCT-SYM-121  
## Épica: Gestión de eventos y validación de información del PIGCCT  
### Enviar evento a validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario que registra información en el sistema.  
> **Quiero:** poder enviar el evento generado a validación.  
> **Para:** iniciar la revisión por parte del rol superior y completar el flujo de aprobación institucional.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de envío
1.1 El sistema debe permitir que un usuario que ha creado o actualizado un registro pueda enviar el evento asociado a validación.  
1.2 La opción de envío debe estar visible únicamente para eventos en estado **"pendiente de envío"**.  
1.3 El usuario debe poder identificar claramente cuáles de sus registros tienen eventos pendientes de envío.

### 2. Visualización de eventos pendientes
2.1 El sistema debe mostrar una lista o panel con todos los eventos creados por el usuario que estén pendientes de envío.  
2.2 La lista debe incluir información relevante como:
- Tabla afectada
- Tipo de afectación (create/update)
- Fecha de creación del evento
- Identificador del objeto modificado

### 3. Proceso de envío a validación
3.1 El usuario debe poder seleccionar uno o varios eventos para enviarlos a validación.  
3.2 El sistema debe solicitar confirmación antes de ejecutar el envío.  
3.3 Al confirmar el envío, el sistema debe actualizar los siguientes campos del evento:
- **enviado_por**: ID del usuario que envía el evento.
- **fch_enviado**: Fecha y hora de envío del evento.
- **estado_registro**: Debe cambiar a **"en validación por entidad"** o estado equivalente.

### 4. Validación antes del envío
4.1 El sistema debe validar que el evento cumpla con todos los requisitos necesarios antes de permitir el envío:
- El evento debe tener un valor_nuevo válido (para create).
- El evento debe tener valor_anterior y valor_nuevo válidos (para update).
- El usuario que envía debe ser el mismo que creó el evento, o tener permisos equivalentes.

4.2 Si la validación falla, el sistema debe mostrar un mensaje claro indicando el problema.

### 5. Restricciones de envío
5.1 El sistema **no debe permitir** enviar eventos que ya hayan sido enviados previamente.  
5.2 El sistema **no debe permitir** modificar el evento después de haberlo enviado a validación.  
5.3 Si se requiere un cambio, debe generarse un nuevo evento tipo update.

### 6. Notificación a validadores
6.1 Al enviar un evento a validación, el sistema debe generar una notificación para los usuarios con rol de **validador de entidad**.  
6.2 La notificación debe incluir:
- Identificador del evento
- Tipo de afectación
- Usuario que envió
- Tabla y objeto afectado

### 7. Trazabilidad del envío
7.1 El sistema debe registrar en logs la acción de envío, incluyendo:
- Usuario que envía
- Fecha y hora de envío
- Identificador del evento
- Estado anterior y nuevo

### 8. Confirmación al usuario
8.1 Después de enviar exitosamente, el sistema debe mostrar un mensaje de confirmación al usuario.  
8.2 El evento debe desaparecer de la lista de "pendientes de envío" del usuario.  
8.3 El usuario debe poder consultar el estado de sus eventos enviados en una sección de "enviados" o "en validación".

### 9. Envío masivo
9.1 El sistema debe permitir seleccionar múltiples eventos y enviarlos en una sola operación.  
9.2 Si algún evento falla en la validación, el sistema debe:
- Informar claramente cuál(es) evento(s) fallaron y por qué.
- Permitir al usuario corregir y reintentar el envío.

### 10. Reversión de envío
10.1 Opcionalmente, el sistema puede permitir que el usuario que envió un evento lo "retracte" o "cancele" **antes** de que un validador lo revise.  
10.2 Si se implementa esta opción:
- Debe estar claramente identificada.
- Debe requerir confirmación.
- Debe registrarse en logs de auditoría.

### 11. Gestión de estados
11.1 El campo **estado_registro** debe actualizarse correctamente según el flujo:
- Inicial: "pendiente de envío"
- Después de envío: "en validación por entidad"

11.2 El cambio de estado debe ser atómico con la actualización de los campos enviado_por y fch_enviado.

---

### Resultado esperado

Un **evento correctamente enviado a validación**, con los campos enviado_por, fch_enviado y estado_registro actualizados, generando notificaciones a los validadores correspondientes, y quedando bloqueado para edición, garantizando el inicio formal del proceso de revisión institucional.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-121.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-121.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-121.png)
