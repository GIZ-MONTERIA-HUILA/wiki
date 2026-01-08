# HU-PIGCCT-SYM-047  
## Épica: Administración de indicadores del PIGCCT  
### Definir tipo de cálculo del indicador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** definir el tipo de cálculo del indicador.  
> **Para:** indicar si el indicador es cuantitativo o cualitativo y así establecer su forma de medición, análisis y seguimiento dentro del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Selección del tipo de cálculo
1.1 El sistema debe permitir seleccionar el **tipo de cálculo del indicador** desde un catálogo predefinido.  
1.2 Los tipos de cálculo disponibles deben ser, como mínimo:
- **Cuantitativo**  
- **Cualitativo**

1.3 La selección del tipo de cálculo debe ser obligatoria para guardar el indicador.



### 2. Comportamiento según el tipo de cálculo
2.1 Si el indicador es **cuantitativo**, el sistema debe habilitar:
- Registro de fórmula de cálculo.  
- Definición de unidad de medida.  
- Registro de línea base, metas y valores numéricos.

2.2 Si el indicador es **cualitativo**, el sistema debe habilitar:
- Registro de criterios de evaluación cualitativa.  
- Escalas de valoración (por ejemplo: bajo, medio, alto).  
- Descripciones narrativas del resultado.



### 3. Validaciones de coherencia
3.1 El sistema debe validar la coherencia entre el tipo de cálculo y:
- La fórmula registrada.  
- La tipología del indicador.  

3.2 El sistema debe impedir el registro de fórmulas numéricas cuando el indicador sea cualitativo.  
3.3 El sistema debe mostrar mensajes de validación claros ante inconsistencias.



### 4. Integridad con la medida y el PIGCCT
4.1 El sistema debe mostrar como referencia la medida, el eje y el PIGCCT asociados al indicador.  
4.2 El sistema debe impedir guardar el tipo de cálculo si el indicador no está correctamente asociado a una medida válida.



### 5. Edición y trazabilidad
5.1 El sistema debe permitir modificar el tipo de cálculo del indicador.  
5.2 El sistema debe conservar el historial de cambios, registrando:
- Tipo de cálculo anterior y nuevo.  
- Fecha de modificación.  
- Usuario que realizó el cambio.

---

### Resultado esperado

El sistema permite definir claramente si un indicador del PIGCCT es cuantitativo o cualitativo, garantizando una medición adecuada, coherente y alineada con los lineamientos metodológicos del seguimiento y evaluación del plan.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-047.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-047.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)
