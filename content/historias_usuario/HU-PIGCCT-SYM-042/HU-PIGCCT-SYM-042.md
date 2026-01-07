# HU-PIGCCT-SYM-042  
## Épica: Administración de indicadores del PIGCCT  
### Registrar indicador asociado a medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** registrar un indicador asociado a una medida del PIGCCT.  
> **Para:** realizar el seguimiento, monitoreo y evaluación del avance e impacto del PIGCCT.



## CRITERIOS DE ACEPTACIÓN

### 1. Asociación obligatoria a una medida
1.1 El sistema debe permitir crear un indicador únicamente si está asociado a una **medida válida** del PIGCCT.  
1.2 El usuario debe seleccionar la medida desde un listado que muestre solo medidas **activas**.  
1.3 La relación indicador → medida debe quedar almacenada de forma persistente.



### 2. Información básica del indicador
2.1 El sistema debe permitir registrar como mínimo la siguiente información del indicador:
- Nombre del indicador.  
- Descripción.  
- Tipo de indicador (gestión, resultado, impacto u otro definido por el sistema).  
- Unidad de medida.  
- Periodicidad de medición.

2.2 Los campos obligatorios deben ser validados antes de permitir el registro.



### 3. Coherencia con la medida
3.1 El indicador debe heredar el contexto de la medida asociada:
- Eje del PIGCCT.  
- Alcance (línea estratégica, línea de acción o medida).  
- Objetivo de la medida.

3.2 El sistema debe mostrar esta información como referencia al momento del registro.



### 4. Metas y valores de referencia
4.1 El sistema debe permitir definir:
- Línea base del indicador.  
- Meta esperada (valor objetivo).  
- Año o periodo de cumplimiento.

4.2 Los valores deben ser numéricos o categóricos según el tipo de indicador definido.



### 5. Responsable y fuente de información
5.1 El sistema debe permitir registrar:
- Entidad o actor responsable del reporte del indicador.  
- Fuente de información (sistema, encuesta, reporte administrativo, etc.).



### 6. Validaciones y unicidad
6.1 El sistema debe validar que no existan indicadores duplicados con el mismo nombre asociados a la misma medida.  
6.2 El sistema debe generar un identificador único para cada indicador.



### 7. Estado del indicador
7.1 Al crear el indicador, el sistema debe asignarlo por defecto en estado **activo**.  
7.2 El estado debe poder ser gestionado posteriormente sin eliminar información histórica.



### 8. Integridad referencial
8.1 El sistema debe garantizar la integridad referencial entre indicadores y medidas.  
8.2 No debe permitirse eliminar una medida si tiene indicadores asociados.



### Resultado esperado

El sistema permite registrar indicadores claramente asociados a una medida del PIGCCT, garantizando coherencia técnica, trazabilidad y una base sólida para el seguimiento y evaluación del plan.



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-042.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-042.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)


