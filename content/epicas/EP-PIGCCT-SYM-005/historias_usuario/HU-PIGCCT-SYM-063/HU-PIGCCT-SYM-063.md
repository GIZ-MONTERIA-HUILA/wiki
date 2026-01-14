# HU-PIGCCT-SYM-063
## Épica: Gestión de acciones territoriales y seguimiento de indicadores del PIGCCT
### Validar fechas de la acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.                
> **Quiero:** que el sistema valide las fechas de una acción territorial.                    
> **Para:** garantizar la coherencia temporal de la acción.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Validación de fechas

1.1 El sistema debe exigir el registro de una fecha inicial y una fecha final para la acción territorial.                    
1.2 El sistema debe validar que la fecha final sea posterior a la fecha inicial.             
1.3 El sistema no debe permitir guardar la acción cuando la fecha final sea igual o anterior a la fecha inicial.

### 2. Consistencia de la información

2.1 El sistema debe aplicar la validación de fechas al crear o editar una acción territorial.                     
2.2 La validación debe garantizar coherencia temporal en los módulos de seguimiento y análisis.

---

### Resultado esperado

El sistema garantiza que las acciones territoriales cuenten con fechas coherentes, asegurando la consistencia temporal de la información utilizada para el seguimiento de los indicadores del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-063.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-063.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-062-081.png)
