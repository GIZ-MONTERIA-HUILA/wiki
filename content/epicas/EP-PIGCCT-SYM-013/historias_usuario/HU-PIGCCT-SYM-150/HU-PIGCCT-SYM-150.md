# HU-PIGCCT-SYM-150  
## Épica: Asociación de indicadores y adjuntos  
### Registrar eventos en tablas relacionales

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de auditoría y validación.  
> **Quiero:** generar eventos de creación o actualización para indicadores, seguimientos y adjuntos.  
> **Para:** incluirlos posteriormente en el proceso de validación y mantener trazabilidad completa de los cambios.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Principio de eventos para tablas relacionales
1.1 El sistema debe generar eventos no solo para la tabla principal `accion`, sino también para sus tablas relacionales:
- `indicador_accion`: Indicadores asociados a acciones
- `indicador_accion_valor`: Valores de seguimiento de indicadores
- `adjuntos`: Archivos adjuntos a acciones
- Otras tablas dependientes según el modelo

1.2 Estos eventos permiten rastrear todos los cambios en la información relacionada con una acción.

### 2. Eventos para indicadores asociados
2.1 Al crear un registro en `indicador_accion`, el sistema debe generar un evento con:
- `tabla`: 'indicador_accion'
- `tabla_id`: ID del indicador asociado
- `tabla_id_principal`: ID de la acción (para navegación)
- `accion_id_principal`: ID de la acción a la que pertenece
- `afectacion`: 'create'
- `valor_nuevo`: JSON con todos los campos del indicador
- `valor_anterior`: null (porque es creación)
- `creado_por`: Usuario que creó la asociación
- `fch_creacion`: Timestamp

2.2 El evento debe almacenarse en la tabla `evento`.

### 3. Eventos de actualización de indicadores
3.1 Al modificar un registro en `indicador_accion`, el sistema debe generar evento tipo **update**.  
3.2 El evento debe capturar:
- `valor_anterior`: Estado previo del indicador (JSON)
- `valor_nuevo`: Estado modificado del indicador (JSON)
- Diferencias específicas para facilitar revisión

3.3 Esto permite rastrear cómo evolucionó la definición del indicador.

### 4. Eventos para valores de seguimiento
4.1 Al registrar un valor de seguimiento en `indicador_accion_valor`, generar evento con:
- `tabla`: 'indicador_accion_valor'
- `tabla_id`: ID del valor registrado
- `tabla_id_principal`: ID del indicador_accion al que pertenece
- `accion_id_principal`: ID de la acción raíz
- `afectacion`: 'create' (normalmente los valores no se actualizan, se crean nuevos)
- `valor_nuevo`: JSON con fecha, valor alcanzado, observaciones, etc.

4.2 Esto documenta el progreso del indicador en el tiempo.

### 5. Eventos para adjuntos
5.1 Al cargar un archivo en `adjuntos`, generar evento con:
- `tabla`: 'adjuntos'
- `tabla_id`: ID del adjunto
- `tabla_id_principal`: ID de la acción
- `accion_id_principal`: ID de la acción
- `afectacion`: 'create'
- `valor_nuevo`: JSON con metadata del archivo (nombre, tipo, tamaño, descripción, ruta)

5.2 No se almacena el archivo en el evento, solo su metadata.

### 6. Estructura común de eventos relacionales
6.1 Todos los eventos de tablas relacionales deben incluir:
- `accion_id_principal`: Referencia a la acción raíz (para agrupación)
- `tabla`: Nombre de la tabla afectada
- `tabla_id`: ID del registro en esa tabla
- `tabla_id_principal`: ID del registro padre directo (si aplica jerarquía)

6.2 Esta estructura permite reconstruir la relación completa de cambios.

### 7. Estado de eventos en borrador
7.1 Mientras la acción está en estado borrador, todos los eventos relacionales deben tener:
- `fch_envio_validacion`: null (no enviados a validación)
- `estado_registro`: 'borrador' o 'pendiente_envio'
- `validado_por_entidad`: null o false
- `validado_por_car`: null o false

7.2 Esto indica que no han entrado al flujo de validación aún.

### 8. Envío masivo a validación
8.1 Cuando el usuario envía la acción a validación (ver HU-121), el sistema debe:
- Identificar todos los eventos relacionados con esa acción (usando `accion_id_principal`)
- Establecer `fch_envio_validacion` en todos ellos con la misma fecha/hora
- Cambiar `estado_registro` a 'en_validacion_entidad'

8.2 Esto asegura que todos los componentes de la acción se validan juntos.

### 9. Validación de eventos relacionales
9.1 Los validadores deben poder revisar no solo la acción principal, sino también:
- Indicadores asociados y sus cambios
- Valores de seguimiento registrados
- Adjuntos cargados como evidencia

9.2 El sistema de validación debe mostrar todos estos elementos de forma integrada.

### 10. Eventos de eliminación
10.1 Al eliminar un indicador, valor de seguimiento o adjunto, generar evento con:
- `afectacion`: 'delete'
- `valor_anterior`: Datos del elemento eliminado
- `valor_nuevo`: null

10.2 Esto mantiene auditoría completa incluso de elementos eliminados.

### 11. Agrupación de eventos por acción
11.1 El sistema debe poder consultar todos los eventos relacionados con una acción mediante `accion_id_principal`.  
11.2 Esto permite:
- Ver historial completo de cambios de una acción y sus componentes
- Enviar todos los eventos juntos a validación
- Generar reportes de auditoría completos

### 12. Orden cronológico de eventos
12.1 Los eventos deben conservar orden cronológico preciso mediante timestamp.  
12.2 Esto permite reconstruir la secuencia exacta de modificaciones.  
12.3 El campo `fch_creacion` debe incluir fecha y hora con precisión de segundos o milisegundos.

### 13. Usuario creador en eventos relacionales
13.1 Cada evento debe registrar quién realizó la acción (campo `creado_por`).  
13.2 Esto permite saber quién agregó cada indicador, cargó cada adjunto, o registró cada valor.  
13.3 Es fundamental para auditoría y responsabilidad.

### 14. Comparación de valores en eventos relacionales
14.1 Para eventos tipo update, el sistema debe facilitar la comparación de `valor_anterior` vs `valor_nuevo`.  
14.2 Los validadores deben poder ver claramente qué cambió en cada componente.  
14.3 Puede usarse una vista de "diff" o comparación lado a lado.

### 15. Integridad referencial de eventos
15.1 Los eventos de tablas relacionales deben mantener integridad referencial con:
- La tabla evento principal
- La tabla afectada (indicador_accion, adjuntos, etc.)
- La acción raíz

15.2 Si se elimina una acción, debe definirse qué ocurre con sus eventos (conservar para auditoría o eliminar en cascada).

### 16. Performance en generación de eventos
16.1 La generación de eventos debe ser eficiente y no degradar el performance del sistema.  
16.2 Puede implementarse de forma asíncrona cuando sea posible.  
16.3 Errores en generación de eventos no deben bloquear la operación principal (guardar indicador, cargar archivo).

### 17. Consulta de eventos relacionales
17.1 El sistema debe proporcionar vistas o consultas que muestren:
- Todos los eventos de una acción agrupados
- Eventos por tabla (ej: solo indicadores)
- Eventos por tipo de afectación (create, update, delete)
- Eventos por período de tiempo

17.2 Esto facilita auditorías y análisis.

### 18. Notificaciones sobre cambios relacionales
18.1 Opcionalmente, al validar una acción, el sistema puede notificar sobre:
- Número de indicadores asociados
- Número de adjuntos cargados
- Número de valores de seguimiento registrados

18.2 Esto da contexto completo a los validadores.

---

### Resultado esperado

Un **sistema completo de registro de eventos** que captura no solo cambios en la tabla accion, sino también en tablas relacionales (indicadores, valores de seguimiento, adjuntos), con referencia a la acción principal, permitiendo validación integral y trazabilidad completa de todos los componentes de una acción del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-150.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-150.png)
