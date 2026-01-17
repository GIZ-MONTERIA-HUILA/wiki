# HU-PIGCCT-SYM-156  
## Épica: Bloqueo y control de edición  
### Generar nuevo evento al corregir una acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión de eventos.  
> **Quiero:** generar un evento cuando una acción corregida es guardada.  
> **Para:** reiniciar el ciclo de validación y mantener trazabilidad de las correcciones realizadas.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Momento de generación del evento
1.1 El sistema debe generar un nuevo evento cuando:
- Una acción en estado 'RECHAZADO' es modificada y guardada, o
- Una acción corregida es reenviada a validación

1.2 El evento documenta las correcciones realizadas después del rechazo.

### 2. Tipo de evento generado
2.1 El evento generado debe ser de tipo **"update"** (actualización).  
2.2 Indica que la acción existente fue modificada después de un rechazo.  
2.3 No es un "create" porque la acción ya existía, sino una corrección.

### 3. Contenido del evento
3.1 El evento debe registrar en la tabla `evento`:
- `tipo_evento`: "update"
- `tabla_evento`: "accion"
- `id_registro_evento`: ID de la acción corregida
- `accion_id_principal`: ID de la acción (para agrupar con otros eventos)
- `usuario_evento`: Usuario registrador que realizó las correcciones
- `fecha_evento`: Fecha y hora de la corrección/reenvío
- `datos_evento`: JSON con los datos actualizados de la acción

3.2 Este evento se suma al historial de eventos de la acción.

### 4. Campo fch_envio_validacion
4.1 Al reenviar la acción corregida, se debe actualizar:
- `fch_envio_validacion`: Nueva fecha de envío (reenvío)
- `usuario_envio`: Usuario que reenvía (debería ser el mismo registrador)

4.2 Esto marca el nuevo inicio del proceso de validación.

### 5. Campo estado_registro del evento
5.1 El nuevo evento debe tener:
- `estado_registro`: "en_validacion_entidad"
- Indica que el evento está nuevamente en proceso de validación

5.2 Reemplaza el estado anterior del evento.

### 6. Cambio de estado de la acción
6.1 Al reenviar después de corregir, la acción debe cambiar:
- `estado_accion`: De 'RECHAZADO' a 'EN_VALIDACION'
- `fch_envio_validacion`: Nueva fecha de reenvío
- `fch_actualizacion`: Fecha de la última modificación

6.2 La acción vuelve a entrar en el ciclo de validación.

### 7. Limpieza de datos de rechazo
7.1 Al reenviar, opcionalmente se puede:
- Mantener `fch_rechazo` para historial
- Agregar `fch_ultimo_rechazo` si hubo rechazos anteriores
- Mantener observaciones de validación para referencia

7.2 O limpiar estos campos si se prefiere un estado limpio.

### 8. Generación de eventos para elementos relacionados
8.1 Si el usuario corrigió elementos relacionados (indicadores, adjuntos), también deben generarse eventos:
- Eventos "update" para indicadores modificados
- Eventos "create" para nuevos indicadores agregados
- Eventos "delete" para indicadores eliminados
- Eventos para adjuntos agregados o eliminados

8.2 Todos con el mismo `accion_id_principal` y la nueva fecha de envío.

### 9. Datos del evento - campo datos_evento
9.1 El campo `datos_evento` debe contener un JSON con:
```json
{
  "accion_id": 123,
  "nombre_accion": "...",
  "estado_anterior": "RECHAZADO",
  "estado_nuevo": "EN_VALIDACION",
  "motivo_reenvio": "Corrección después de rechazo",
  "observaciones_previas": "...",
  "correcciones_realizadas": "...",
  "campos_modificados": ["descripcion", "presupuesto", "fecha_inicio"],
  "fecha_rechazo_anterior": "2026-01-10",
  "validador_que_rechazo": "Juan Pérez"
}
```

9.2 Esto proporciona contexto completo sobre la corrección.

### 10. Referencia al evento de rechazo
10.1 El nuevo evento puede referenciar al evento de rechazo anterior:
- `evento_relacionado_id`: ID del evento de rechazo
- Esto permite trazar la secuencia: envío → rechazo → corrección → reenvío

10.2 Facilita la auditoría del proceso completo.

### 11. Contador de intentos
11.1 El sistema puede llevar un contador de cuántas veces se ha reenviado:
- `numero_envio`: 1 (primer envío), 2 (primer reenvío), etc.
- Ayuda a identificar acciones con múltiples rechazos

11.2 Útil para detectar problemas recurrentes o necesidad de capacitación.

### 12. Notificación a validadores
12.1 Al generar el evento de reenvío, notificar a los validadores:
- "Acción [Nombre] ha sido corregida y reenviada"
- "Validador anterior: [nombre]"
- "Observaciones previas: [texto]"
- "Revisar las correcciones realizadas"

12.2 Los validadores deben saber que es un reenvío, no una nueva acción.

### 13. Diferenciación en interfaz de validador
13.1 En la interfaz de validación, las acciones reenviadas deben distinguirse:
- Badge: "Reenvío" o "Corrección"
- Mostrar historial de rechazos anteriores
- Resaltar qué campos fueron modificados desde el rechazo

13.2 Esto facilita la revisión para los validadores.

### 14. Transacción atómica
14.1 La generación del evento y actualización de la acción debe ser atómica:
- Si falla la creación del evento, revertir cambio de estado
- Si falla la actualización de la acción, revertir creación del evento

14.2 Garantiza consistencia de datos.

### 15. Validaciones antes de generar evento
15.1 Antes de permitir el reenvío y generar el evento, validar:
- Campos obligatorios completos
- Al menos un indicador asociado
- Valores proyectados diligenciados
- Cambios realizados respecto a la versión rechazada

15.2 No permitir reenviar sin hacer correcciones.

### 16. Comentarios del registrador
16.1 Al reenviar, permitir al usuario agregar comentarios:
```
"Comentarios sobre las correcciones realizadas:"
[Campo de texto]
```

16.2 Estos comentarios se incluyen en el evento y ayudan a los validadores a entender qué se corrigió.

### 17. Auditoría del reenvío
17.1 Registrar en logs cada reenvío con:
- ID de la acción
- Usuario que reenvía
- Fecha y hora
- Número de intento
- Campos modificados
- Observaciones anteriores
- Comentarios del registrador

17.2 Esta información es valiosa para auditoría y mejora de procesos.

### 18. Métricas de corrección
18.1 El sistema puede calcular métricas:
- Tiempo promedio entre rechazo y reenvío
- Porcentaje de acciones rechazadas que se corrigen exitosamente
- Motivos más comunes de rechazo
- Validadores con más/menos rechazos

18.2 Estas métricas ayudan a mejorar la calidad del proceso.

---

### Resultado esperado

Un **evento de actualización generado correctamente** al corregir y reenviar una acción rechazada, con toda la información de las correcciones realizadas, fecha de reenvío actualizada, estado cambiado de RECHAZADO a EN_VALIDACION, notificaciones enviadas a validadores, y trazabilidad completa del ciclo de corrección para auditoría y análisis del proceso de validación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-156.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-156.png)

