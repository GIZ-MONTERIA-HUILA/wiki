# HU-PIGCCT-SYM-126  
## Épica: Gestión de eventos y validación de información del PIGCCT  
### Bloquear edición de registros validados

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión del PIGCCT.  
> **Quiero:** bloquear la edición directa de registros que ya han sido validados.  
> **Para:** garantizar la integridad de la información y que cualquier cambio necesario pase por el proceso de validación mediante la generación de un nuevo evento tipo update.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación de registros validados
1.1 El sistema debe identificar un registro como "validado" cuando su evento asociado cumple:
```
validado_por_entidad = true AND validado_por_car = true
```

1.2 Los registros con esta condición deben considerarse bloqueados para edición directa.

### 2. Bloqueo de edición en interfaz de usuario
2.1 Cuando un usuario intenta editar un registro validado, el sistema debe:
- Deshabilitar todos los campos de edición en el formulario
- Mostrar los campos en modo **solo lectura**
- Mostrar claramente que el registro está validado y no puede editarse directamente

2.2 Debe mostrarse un mensaje informativo como: "Este registro ha sido validado y no puede editarse directamente. Si requiere cambios, solicite una modificación que será sometida a validación."

### 3. Bloqueo a nivel de backend
3.1 El sistema debe implementar validaciones en el backend para prevenir ediciones directas de registros validados.  
3.2 Si se intenta una actualización directa mediante API o SQL, el sistema debe:
- Rechazar la operación
- Retornar un código de error apropiado (ej: HTTP 403 Forbidden)
- Registrar el intento en logs de seguridad

3.3 Esta validación debe ejecutarse antes de cualquier actualización en las tablas: acción, indicador_accion, indicador_accion_valor, adjuntos.

### 4. Excepción para administradores
4.1 Los usuarios con rol de **administrador del sistema** deben poder editar registros validados en casos excepcionales.  
4.2 Cuando un administrador edita un registro validado:
- Debe mostrarse una advertencia clara sobre las implicaciones
- Debe requerirse confirmación explícita
- La edición debe registrarse en logs de auditoría con:
  - Usuario administrador
  - Registro modificado
  - Valores anterior y nuevo
  - Justificación de la edición (campo obligatorio)

### 5. Proceso para solicitar cambios
5.1 El sistema debe proporcionar una opción clara para que usuarios autorizados soliciten cambios en registros validados.  
5.2 Al solicitar un cambio, el sistema debe:
- Generar automáticamente un **nuevo evento tipo update**
- Capturar el valor_anterior del registro validado
- Permitir al usuario editar los campos en un formulario especial
- Capturar el valor_nuevo propuesto
- Marcar el evento como "pendiente de envío"

5.3 El registro original debe permanecer sin cambios hasta que el nuevo evento sea completamente validado.

### 6. Generación automática de evento update
6.1 Cuando se solicita un cambio en un registro validado, el sistema debe:
- Crear un nuevo registro en la tabla **evento**
- Establecer **tipo_afectacion_enm = "update"**
- Copiar el estado actual del registro en **valor_anterior**
- Almacenar los cambios propuestos en **valor_nuevo**
- Establecer **estado_registro = "pendiente de envío"**

6.2 El evento debe seguir el flujo completo de validación (envío → validación entidad → validación CAR).

### 7. Indicadores visuales de bloqueo
7.1 Los registros validados deben mostrar indicadores visuales claros:
- Icono de candado o similar
- Badge "Validado" de color verde
- Tooltip explicativo al pasar el mouse sobre los campos bloqueados

7.2 Debe diferenciarse visualmente entre:
- Registros editables (pendientes de validación)
- Registros bloqueados (completamente validados)

### 8. Aplicación de cambios validados
8.1 Solo cuando el nuevo evento tipo update sea completamente validado (validado_por_entidad = true AND validado_por_car = true), el sistema debe:
- Aplicar los cambios del valor_nuevo al registro original
- Actualizar el estado de validación del registro
- Mantener el historial de eventos para trazabilidad

8.2 Hasta que el evento sea validado, el registro debe mantener sus valores originales.

### 9. Manejo de eventos update rechazados
9.1 Si un evento update es rechazado por la entidad o la CAR:
- El registro original mantiene sus valores sin cambios
- El usuario recibe notificación del rechazo con observaciones
- El usuario puede corregir y reenviar, o cancelar la solicitud de cambio

### 10. Restricciones por tabla
10.1 El bloqueo de edición debe aplicarse a todas las tablas sujetas a validación:
- **acción**: Bloquear edición de acciones validadas
- **indicador_accion**: Bloquear edición de indicadores validados
- **indicador_accion_valor**: Bloquear edición de valores validados
- **adjuntos**: Bloquear eliminación/edición de adjuntos validados

### 11. Permisos y roles
11.1 El sistema debe verificar permisos antes de permitir acciones:
- Usuario que registra: Puede solicitar cambios en sus propios registros validados
- Validadores: No pueden editar directamente, solo validar eventos
- Administradores: Pueden editar en casos excepcionales con justificación

### 12. Auditoría del bloqueo
12.1 El sistema debe registrar en logs:
- Intentos de edición directa de registros bloqueados
- Usuario que intentó la edición
- Registro que se intentó editar
- Fecha y hora del intento

12.2 Esta información debe estar disponible para auditorías de seguridad.

### 13. Mensajes de error informativos
13.1 Si un usuario intenta editar un registro bloqueado, el mensaje debe ser claro y orientador:
- Explicar por qué está bloqueado
- Indicar cómo solicitar cambios
- Proporcionar enlace o botón para iniciar solicitud de cambio

### 14. Bloqueo en operaciones masivas
14.1 Si un usuario intenta realizar operaciones masivas (actualización de múltiples registros), el sistema debe:
- Identificar cuáles registros están validados
- Excluirlos de la operación masiva
- Informar al usuario cuáles registros fueron excluidos y por qué
- Procesar solo los registros editables

### 15. Versionado implícito
15.1 El sistema de eventos funciona como control de versiones:
- Cada evento update validado representa una nueva "versión" del registro
- El historial de eventos permite reconstruir todas las versiones anteriores
- Esta información debe estar disponible para auditoría (ver HU-127)

---

### Resultado esperado

Un **sistema que bloquea efectivamente** la edición directa de registros validados, tanto en interfaz de usuario como en backend, protegiendo la integridad de la información aprobada, y proporcionando un mecanismo claro para solicitar cambios mediante la generación de nuevos eventos update que deben pasar por el proceso completo de validación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-126.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-126.png)
