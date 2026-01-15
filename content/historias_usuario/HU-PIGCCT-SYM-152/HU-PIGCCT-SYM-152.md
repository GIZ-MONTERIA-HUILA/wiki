# HU-PIGCCT-SYM-152  
## Épica: Envío a validación  
### Enviar a validación todos los eventos asociados

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de validación.  
> **Quiero:** enviar a validación todos los elementos relacionados con una acción.  
> **Para:** garantizar revisión integral del registro incluyendo la acción principal y todas sus dependencias.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación de eventos relacionados
1.1 Al enviar una acción a validación, el sistema debe identificar todos los eventos relacionados mediante el campo `accion_id_principal`.  
1.2 Esto incluye eventos de diferentes tablas:
- `accion`: La acción principal
- `indicador_accion`: Indicadores asociados
- `indicador_accion_valor`: Valores de seguimiento de indicadores
- `adjuntos`: Archivos adjuntos

1.3 Todos estos eventos comparten el mismo `accion_id_principal`.

### 2. Consulta de eventos a enviar
2.1 El sistema debe ejecutar una consulta que obtenga todos los eventos donde:
```sql
WHERE accion_id_principal = [ID_de_la_accion]
  AND fch_envio_validacion IS NULL
  AND estado_registro IN ('borrador', 'pendiente_envio')
```

2.2 Esto asegura que solo se envían eventos que no han sido enviados previamente.

### 3. Inclusión de evento de la acción principal
3.1 El evento principal de la tabla `accion` debe ser incluido en el envío.  
3.2 Este evento puede ser de tipo:
- **create**: Si es la primera vez que se envía la acción
- **update**: Si la acción fue editada después de un rechazo y se reenvía

3.3 El evento principal contiene toda la información de la acción.

### 4. Inclusión de eventos de indicadores asociados
4.1 Todos los eventos de la tabla `indicador_accion` asociados a la acción deben incluirse.  
4.2 Estos eventos documentan:
- Creación de asociaciones de indicadores
- Modificaciones en las metas o descripciones
- Eliminaciones de indicadores (si las hubo)

4.3 Los validadores deben poder ver qué indicadores se agregaron y cuándo.

### 5. Inclusión de eventos de valores de seguimiento
5.1 Si la acción tiene valores de seguimiento registrados en `indicador_accion_valor`, sus eventos también deben incluirse.  
5.2 Estos eventos documentan:
- Avances reportados en indicadores
- Fechas de medición
- Observaciones sobre el progreso

5.3 Esto proporciona contexto completo a los validadores.

### 6. Inclusión de eventos de adjuntos
6.1 Todos los eventos de la tabla `adjuntos` relacionados con la acción deben incluirse.  
6.2 Estos eventos documentan:
- Archivos cargados como evidencia
- Descripciones de documentos
- Fechas de carga

6.3 Los validadores pueden revisar qué documentación se adjuntó y cuándo.

### 7. Agrupación de eventos por tipo
7.1 El sistema puede organizar los eventos por tipo de tabla para facilitar procesamiento:
- Eventos de acción: [lista]
- Eventos de indicadores: [lista]
- Eventos de valores: [lista]
- Eventos de adjuntos: [lista]

7.2 Esto permite aplicar lógica específica si es necesario.

### 8. Validación de completitud
8.1 Antes de enviar, el sistema debe verificar que no falten eventos críticos.  
8.2 Si la acción tiene indicadores asociados pero no hay eventos correspondientes, puede indicar inconsistencia en los datos.  
8.3 El sistema debe garantizar integridad en el envío.

### 9. Transacción atómica
9.1 El envío de todos los eventos debe realizarse en una **transacción atómica**.  
9.2 Si falla el marcado de algún evento, debe revertirse toda la operación.  
9.3 Esto garantiza consistencia: o se envían todos o ninguno.

### 10. Actualización masiva de eventos
10.1 El sistema debe actualizar todos los eventos identificados simultáneamente (ver HU-153).  
10.2 Los campos a actualizar en todos los eventos:
- `fch_envio_validacion`: Misma fecha/hora para todos
- `usuario_envio`: Usuario que envió la acción
- `estado_registro`: Cambiar a "en_validacion_entidad"

10.3 Esto marca formalmente el inicio del proceso de validación.

### 11. Conteo de eventos enviados
11.1 El sistema debe contabilizar cuántos eventos se envían:
- Total de eventos enviados
- Eventos por tipo de tabla
- Eventos create vs update vs delete

11.2 Esta información puede mostrarse al usuario o registrarse en logs.

### 12. Notificación del paquete completo
12.1 Al notificar a los validadores, el sistema puede informar sobre el alcance completo:
```
"Nueva acción enviada a validación: [Nombre]"
"Incluye:"
- 1 acción principal
- 5 indicadores asociados
- 12 valores de seguimiento
- 8 archivos adjuntos
```

12.2 Esto da contexto completo a los validadores sobre qué revisar.

### 13. Orden de procesamiento
13.1 Los validadores deben poder revisar los eventos en orden cronológico.  
13.2 El sistema debe preservar el orden mediante timestamps.  
13.3 Esto permite entender la evolución de la acción desde su creación.

### 14. Relación padre-hijo en eventos
14.1 El sistema debe mantener la relación jerárquica:
```
accion (principal)
├── indicador_accion (hijo)
│   └── indicador_accion_valor (nieto)
└── adjuntos (hijo)
```

14.2 Esta estructura facilita la navegación y revisión por parte de los validadores.

### 15. Manejo de eventos sin cambios
15.1 Si desde el último envío (en caso de reenvío) no hubo cambios en algún componente, sus eventos ya tienen fecha de envío.  
15.2 El sistema debe incluir solo eventos nuevos o modificados.  
15.3 Los eventos anteriormente validados no se reenvían (depende de lógica de negocio).

### 16. Visualización en módulo de validación
16.1 El módulo de validación debe mostrar todos los elementos enviados de forma integrada:
- Vista de la acción completa
- Lista de indicadores con sus eventos
- Historial de cambios
- Documentos adjuntos

16.2 Los validadores deben ver el paquete completo en una sola interfaz.

### 17. Auditoría del envío completo
17.1 El sistema debe registrar en logs el envío completo con:
- ID de la acción
- Lista de IDs de todos los eventos enviados
- Usuario que envió
- Fecha y hora
- Resultado del envío (éxito/fallo)

17.2 Esto permite trazabilidad completa del proceso.

---

### Resultado esperado

Un **envío integral a validación** que incluye no solo la acción principal sino todos sus eventos relacionados (indicadores, valores de seguimiento, adjuntos), marcados simultáneamente con fecha de envío, permitiendo a los validadores revisar el registro completo de forma coherente y cronológica.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-152.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-152.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-152.png)
