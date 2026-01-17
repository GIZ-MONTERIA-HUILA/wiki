# HU-PIGCCT-SYM-153  
## Épica: Envío a validación  
### Marcar eventos como enviados

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión de eventos.  
> **Quiero:** actualizar la fecha y usuario de envío en los eventos.  
> **Para:** indicar formalmente que entraron en proceso de validación y mantener trazabilidad precisa.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Campos a actualizar en eventos
1.1 Al enviar eventos a validación, el sistema debe actualizar los siguientes campos en la tabla `evento`:
- `fch_envio_validacion`: Fecha y hora del envío
- `usuario_envio`: ID del usuario que envía
- `estado_registro`: Estado del evento en el flujo de validación

1.2 Estos campos marcan formalmente el inicio del proceso de validación.

### 2. Campo fch_envio_validacion
2.1 El campo `fch_envio_validacion` debe establecerse con la **fecha y hora exacta** del momento del envío.  
2.2 Debe incluir precisión de segundos o milisegundos para trazabilidad exacta.  
2.3 Todos los eventos de una misma acción deben recibir la **misma fecha de envío** para indicar que se enviaron juntos.

2.4 Formato recomendado: `YYYY-MM-DD HH:MM:SS` o timestamp.

### 3. Campo usuario_envio
3.1 El campo `usuario_envio` debe almacenar el ID del usuario registrador que envió la acción a validación.  
3.2 Este campo permite identificar quién fue responsable del envío.  
3.3 Se obtiene del usuario autenticado en el momento del envío.

### 4. Campo estado_registro
4.1 El campo `estado_registro` debe actualizarse para reflejar que el evento está en validación.  
4.2 Valores posibles según el flujo:
- **'borrador'** o **'pendiente_envio'**: Estado inicial (antes de enviar)
- **'en_validacion_entidad'**: Después del envío (esperando validación de entidad)
- **'validado_entidad'**: Después de validación por entidad
- **'en_validacion_car'**: Esperando validación de CAR
- **'validado_car'**: Completamente validado
- **'rechazado'**: Si fue rechazado

4.3 Al enviar, cambiar de estado inicial a **'en_validacion_entidad'**.

### 5. Actualización masiva de eventos
5.1 El sistema debe actualizar todos los eventos relacionados con la acción en una sola operación SQL:
```sql
UPDATE evento
SET fch_envio_validacion = [FECHA_ACTUAL],
    usuario_envio = [ID_USUARIO],
    estado_registro = 'en_validacion_entidad'
WHERE accion_id_principal = [ID_ACCION]
  AND fch_envio_validacion IS NULL;
```

5.2 Esto garantiza consistencia en el marcado.

### 6. Validación de eventos ya enviados
6.1 El sistema debe verificar que los eventos no hayan sido enviados previamente.  
6.2 La condición `fch_envio_validacion IS NULL` asegura que solo se actualizan eventos sin fecha de envío.  
6.3 Eventos con fecha de envío existente no deben modificarse.

### 7. Registro de timestamp preciso
7.1 El sistema debe capturar el timestamp con la mayor precisión disponible.  
7.2 Esto permite:
- Ordenar eventos cronológicamente con exactitud
- Identificar cuándo se envió cada lote
- Rastrear tiempos de respuesta en validación

7.3 La precisión ayuda en auditorías y análisis de tiempos.

### 8. Consistencia en actualización
8.1 Todos los eventos de una acción deben marcarse en la misma transacción.  
8.2 Si falla la actualización de algún evento, debe revertirse toda la operación.  
8.3 Esto garantiza que no queden eventos en estados inconsistentes.

### 9. Indicadores en interfaz de usuario
9.1 Después de marcar los eventos, la interfaz debe reflejar el cambio:
- Badge "En validación" en la acción
- Indicador visual del estado en listados
- Fecha de envío visible en detalles

9.2 El usuario debe ver claramente que la acción fue enviada.

### 10. Diferenciación de eventos enviados vs pendientes
10.1 El sistema debe poder filtrar eventos fácilmente:
- **Enviados**: `fch_envio_validacion IS NOT NULL`
- **Pendientes**: `fch_envio_validacion IS NULL`

10.2 Esto facilita consultas y reportes.

### 11. Trazabilidad de múltiples envíos
11.1 Si una acción puede reenviarse después de un rechazo, cada envío debe registrarse.  
11.2 Puede usarse un historial de envíos o mantener registro del último envío.  
11.3 El sistema debe distinguir entre primer envío y reenvíos.

### 12. Auditoría de marcado de eventos
12.1 El sistema debe registrar en logs cada operación de marcado con:
- Cantidad de eventos marcados
- ID de la acción
- Usuario que envió
- Fecha y hora de la operación
- Resultado (éxito/fallo)

12.2 Esta información es útil para troubleshooting y auditoría.

### 13. Notificaciones basadas en marcado
13.1 El marcado de eventos puede desencadenar notificaciones automáticas:
- Notificar a validadores de entidad
- Actualizar dashboard de eventos pendientes
- Generar alertas en el sistema

13.2 El marcado es el evento que inicia estas acciones.

### 14. Reversión de marcado (si aplica)
14.1 Si se permite cancelar un envío, el sistema debe poder revertir el marcado:
- Establecer `fch_envio_validacion = NULL`
- Cambiar `estado_registro` de vuelta a 'borrador'
- Registrar la reversión en auditoría

14.2 Esto devuelve los eventos a estado editable.

### 15. Consulta de eventos por fecha de envío
15.1 El sistema debe permitir consultar eventos por rangos de fecha de envío.  
15.2 Esto facilita reportes como:
- "Eventos enviados esta semana"
- "Eventos pendientes de validación por más de X días"
- "Acciones enviadas por usuario"

15.3 El campo `fch_envio_validacion` es clave para estas consultas.

### 16. Integridad referencial
16.1 El campo `usuario_envio` debe ser una clave foránea válida hacia la tabla de usuarios.  
16.2 El sistema debe validar que el usuario exista antes de actualizar.  
16.3 Esto garantiza integridad de datos.

### 17. Performance de actualización
17.1 La actualización masiva de eventos debe ser eficiente.  
17.2 Usar índices apropiados en:
- `accion_id_principal`
- `fch_envio_validacion`
- `estado_registro`

17.3 Esto asegura que la operación de marcado sea rápida incluso con muchos eventos.

---

### Resultado esperado

**Eventos correctamente marcados como enviados** con fecha de envío, usuario responsable y estado actualizado a "en validación por entidad", permitiendo diferenciar claramente eventos pendientes de edición de eventos en proceso de validación, y proporcionando trazabilidad completa del flujo de aprobación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-153.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-153.png)
