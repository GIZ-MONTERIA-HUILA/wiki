# HU-PIGCCT-SYM-046  
## Épica: Administración de indicadores del PIGCCT  
### Definir tipología especificada del indicador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** definir y seleccionar la tipología especificada del indicador.  
> **Para:** ajustar el indicador a las clasificaciones metodológicas definidas por la entidad y garantizar estandarización en el sistema de seguimiento del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Selección de la tipología del indicador
1.1 El sistema debe permitir seleccionar la **tipología especificada del indicador** desde un catálogo configurable.  
1.2 La tipología debe depender del tipo de indicador previamente definido (producto, gestión o impacto).  
1.3 La selección de la tipología debe ser obligatoria para guardar el indicador.



### 2. Catálogo de tipologías
2.1 El sistema debe contar con un catálogo administrable de tipologías, definido por la entidad.  
2.2 El catálogo debe permitir asociar una o varias tipologías a cada tipo de indicador.  
2.3 Cada tipología debe contar con:
- Nombre  
- Descripción metodológica  



### 3. Validaciones metodológicas
3.1 El sistema debe validar que la tipología seleccionada sea coherente con el tipo de indicador.  
3.2 El sistema debe impedir la selección de tipologías no habilitadas para el tipo de indicador.  
3.3 El sistema debe mostrar mensajes de validación claros cuando exista inconsistencia.



### 4. Integridad con la medida y el PIGCCT
4.1 El sistema debe mostrar como referencia la medida, el eje y el PIGCCT al que pertenece el indicador.  
4.2 El sistema debe impedir guardar la tipología si el indicador no está asociado a una medida válida.



### 5. Edición y trazabilidad
5.1 El sistema debe permitir modificar la tipología del indicador.  
5.2 El sistema debe conservar el historial de cambios, registrando:
- Tipología anterior y nueva.  
- Fecha de modificación.  
- Usuario que realizó el cambio.

---

### Resultado esperado

El sistema permite clasificar los indicadores del PIGCCT mediante tipologías metodológicas estandarizadas, fortaleciendo la coherencia técnica, la comparabilidad y la calidad del seguimiento y evaluación del plan.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-046.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-046.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)

