# HU-PIGCCT-SYM-068
## Épica: Gestión de acciones territoriales y seguimiento de indicadores del PIGCCT
### Crear relación acción–indicador

--- 

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.                         
> **Quiero:** que el sistema cree automáticamente la relación entre acción e indicador.                    
> **Para:** formalizar la relación N:M entre acción e indicador del PIGCCT.

## CRITERIOS DE ACEPTACIÓN

### 1. Creación automática de la relación

1.1 El sistema debe crear automáticamente los registros en la entidad indicador_accion.                 
1.2 La creación de los registros debe realizarse al asociar uno o varios indicadores a una acción territorial.

### 2. Relación N:M acción–indicador

2.1 El sistema debe permitir que una acción territorial esté asociada a múltiples indicadores.                       
2.2 Un indicador debe poder estar asociado a múltiples acciones territoriales.

### 3. Integridad y consistencia de la relación

3.1 Cada registro en indicador_accion debe corresponder a una acción y a un indicador válidos.                      
3.2 El sistema debe impedir la creación de relaciones duplicadas entre la misma acción y el mismo indicador.

### 4. Uso de la relación en el sistema

4.1 La relación acción–indicador debe ser utilizada por los módulos de seguimiento y análisis.                     
4.2 El sistema debe garantizar la consistencia de esta relación en los diferentes módulos.

### Resultado esperado

El sistema crea y gestiona automáticamente la relación N:M entre acciones territoriales e indicadores del PIGCCT, asegurando integridad, coherencia y disponibilidad de la información para el seguimiento y análisis.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-068.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-068.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-062-081.png)
