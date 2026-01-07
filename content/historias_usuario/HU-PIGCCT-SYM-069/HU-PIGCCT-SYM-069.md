# HU-PIGCCT-SYM-069
## Épica: Gestión de acciones territoriales y seguimiento de indicadores del PIGCCT
### Definir forma de evaluación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.                           
> **Quiero:** definir la periodicidad de evaluación de una acción territorial.                      
> **Para:** determinar la cantidad de seguimientos por vigencia.

## CRITERIOS DE ACEPTACIÓN

### 1. Definición de la periodicidad de evaluación

1.1 El sistema debe permitir seleccionar una periodicidad de evaluación para la acción territorial.                         
1.2 La periodicidad debe definirse a partir de un conjunto de valores permitidos.

### 2. Valores permitidos

2.1 El sistema debe permitir únicamente los siguientes valores:

- Mensual (12).
- Trimestral (4).
- Cuatrimestral (3).
- Semestral (2).
- Anual (1).

2.2 El sistema no debe permitir registrar valores distintos a los definidos.

### 3. Consistencia de la información

3.1 La periodicidad de evaluación debe quedar asociada a la acción territorial.                      
3.2 La periodicidad debe ser utilizada para el cálculo de seguimientos por vigencia.

### Resultado esperado

El sistema permite definir de forma consistente la periodicidad de evaluación de las acciones territoriales, asegurando la correcta determinación de los seguimientos por vigencia para el monitoreo de los indicadores del PIGCCT.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-069.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-069.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-062-081.png)
