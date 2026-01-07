# HU-PIGCCT-SYM-071
## Épica: Gestión de acciones territoriales y seguimiento de indicadores del PIGCCT
### Crear registros automáticos de seguimiento

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.                       
> **Quiero:** que el sistema cree automáticamente los registros de seguimiento de los indicadores asociados a una acción territorial.                          
> **Para:** facilitar el control y monitoreo según la forma de evaluación y las vigencias definidas.

## CRITERIOS DE ACEPTACIÓN

### 1. Creación automática de registros de seguimiento

1.1 El sistema debe crear automáticamente los registros en la entidad indicador_accion_valor.                        
1.2 Los registros deben crearse para cada indicador asociado a la acción territorial.

### 2. Cálculo del número de registros

2.1 El sistema debe calcular el número de registros de seguimiento de la siguiente forma:

> Nro de registros = frecuencia_evaluación × vigencia_año.

2.2 El cálculo debe realizarse utilizando la periodicidad de evaluación y el número de vigencias definidos para la acción.

### 3. Estado inicial de los registros

3.1 Los campos de seguimiento deben crearse en estado inicial (null).                        
3.2 Los registros deben quedar disponibles para su posterior diligenciamiento.

### Resultado esperado

El sistema crea automáticamente los registros de seguimiento en indicador_accion_valor para cada indicador asociado a una acción territorial, de acuerdo con la forma de evaluación y las vigencias definidas, garantizando la disponibilidad de los datos para el monitoreo del PIGCCT.



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-071.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-071.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-062-081.png)

