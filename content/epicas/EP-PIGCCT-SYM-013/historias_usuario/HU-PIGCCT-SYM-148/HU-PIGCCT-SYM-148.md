# HU-PIGCCT-SYM-148  
## Épica: Asociación de indicadores y adjuntos  
### Guardar indicadores asociados en estado borrador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** guardar las relaciones acción-indicador sin enviarlas a validación.  
> **Para:** permitir ajustes y correcciones antes de la aprobación final.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Guardado de indicadores sin validación
1.1 El sistema debe permitir guardar indicadores asociados a una acción que está en estado **borrador**.  
1.2 Los indicadores se almacenan en la tabla `indicador_accion` sin requerir validación completa de datos.  
1.3 El guardado es independiente del estado de validación de la acción principal.

### 2. Estado de los indicadores
2.1 Los indicadores asociados a una acción en borrador heredan implícitamente el estado de la acción.  
2.2 Mientras la acción esté en borrador:
- Los indicadores son editables
- Pueden agregarse nuevos indicadores
- Pueden eliminarse indicadores
- Pueden modificarse valores y metas

2.3 Los indicadores no requieren un campo de estado separado, pero pueden tenerlo si es necesario.

### 3. Validaciones mínimas al guardar
3.1 El sistema debe validar solo campos críticos al guardar indicadores en borrador:
- El `accion_id` debe ser válido y existir
- El nombre o referencia del indicador no debe estar vacío
- Si es un indicador cuantitativo, debe tener unidad de medida

3.2 Otros campos pueden quedar pendientes o incompletos.

### 4. Almacenamiento en tabla indicador_accion
4.1 Cada indicador asociado debe guardarse como un registro en la tabla `indicador_accion`.  
4.2 Los campos mínimos a almacenar:
- `id`: Identificador único de la relación
- `accion_id`: Referencia a la acción
- `indicador_id`: Referencia al indicador del catálogo (si aplica)
- `nombre`: Nombre del indicador
- `descripcion`: Descripción del indicador
- `meta`: Valor meta esperado
- `unidad_medida`: Unidad de medida
- `valor_actual`: Valor actual del indicador (puede iniciar en null)
- `creado_por`: Usuario que asoció el indicador
- `fch_creacion`: Fecha de creación

4.3 Campos adicionales según necesidades del proyecto.

### 5. Relación con eventos
5.1 Al guardar un nuevo indicador asociado, el sistema debe generar un evento de tipo **create** en la tabla evento (ver HU-150).  
5.2 El evento debe referenciar:
- `tabla`: 'indicador_accion'
- `tabla_id`: ID del registro en indicador_accion
- `accion_id_principal`: ID de la acción a la que pertenece
- `afectacion`: 'create'
- `valor_nuevo`: JSON con los datos del indicador

5.3 El evento permanece sin fecha de envío mientras la acción esté en borrador.

### 6. Edición de indicadores en borrador
6.1 El usuario debe poder modificar indicadores asociados mientras la acción esté en borrador.  
6.2 Al modificar un indicador, se genera un evento de tipo **update**.  
6.3 El evento update debe capturar:
- `valor_anterior`: Estado previo del indicador
- `valor_nuevo`: Estado modificado
- Usuario y fecha de modificación

### 7. Eliminación de indicadores en borrador
7.1 El usuario debe poder eliminar indicadores asociados mientras la acción esté en borrador.  
7.2 Al eliminar, puede:
- Eliminarse físicamente el registro de `indicador_accion`
- O marcarse como eliminado (borrado lógico)

7.3 Debe generarse un evento que registre la eliminación para auditoría.

### 8. Múltiples indicadores por acción
8.1 Una acción puede tener múltiples indicadores asociados.  
8.2 El sistema debe permitir agregar tantos indicadores como sean necesarios.  
8.3 Debe mostrar claramente la lista de todos los indicadores asociados.

### 9. Guardado individual vs. guardado global
9.1 Cada indicador se guarda individualmente al crearlo o modificarlo.  
9.2 No es necesario un botón "Guardar todos los indicadores"; el guardado es automático al confirmar cada indicador.  
9.3 Esto permite guardar progresivamente sin perder información.

### 10. Feedback al usuario
10.1 Al guardar un indicador exitosamente, mostrar mensaje:
```
"Indicador asociado guardado correctamente"
```

10.2 Si falla el guardado, mostrar error específico:
```
"Error al guardar indicador: [causa del error]"
```

10.3 Los mensajes deben desaparecer automáticamente o ser descartables.

### 11. Visualización en la pestaña de indicadores
11.1 La pestaña "Indicadores asociados" debe mostrar:
- Lista de indicadores guardados
- Estado de completitud de cada indicador
- Opciones para editar o eliminar cada uno
- Botón para agregar nuevos indicadores

11.2 Debe indicar cuántos indicadores hay asociados (ej: "Indicadores (5)").

### 12. Indicadores obligatorios vs opcionales
12.1 El sistema puede tener indicadores obligatorios que deben asociarse antes de enviar a validación.  
12.2 Mientras esté en borrador, estos indicadores pueden faltar sin bloquear el guardado.  
12.3 Al intentar enviar a validación, el sistema debe verificar que los indicadores obligatorios estén presentes.

### 13. Consistencia de datos
13.1 El sistema debe validar que los valores ingresados sean coherentes:
- Valores numéricos cuando corresponda
- Unidades de medida válidas
- Metas alcanzables o lógicas

13.2 Puede mostrar advertencias si detecta inconsistencias, pero no bloquear el guardado en borrador.

### 14. Transición a estado validación
14.1 Cuando la acción se envía a validación, los indicadores asociados también pasan al flujo de validación.  
14.2 Los eventos de los indicadores reciben fecha de envío junto con el evento de la acción.  
14.3 Después de esto, los indicadores dejan de ser editables por el registrador (hasta que se apruebe o rechace).

### 15. Auditoría de cambios
15.1 Todos los cambios en indicadores deben quedar registrados en eventos para auditoría.  
15.2 Esto permite rastrear:
- Cuándo se agregó cada indicador
- Quién lo agregó
- Qué modificaciones se hicieron
- Cuándo se envió a validación

---

### Resultado esperado

**Indicadores asociados a una acción guardados en estado borrador** en la tabla indicador_accion, con eventos correspondientes sin fecha de envío, que permanecen editables para ajustes y correcciones hasta que la acción completa se envíe a validación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-148.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-148.png)

