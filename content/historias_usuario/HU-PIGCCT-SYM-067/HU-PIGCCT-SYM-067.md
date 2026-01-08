# HU-PIGCCT-SYM-067
## Épica: Gestión de acciones territoriales y seguimiento de indicadores del PIGCCT
### Seleccionar eje, medida e indicadores

DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.                  
> **Quiero:** asociar una acción territorial a uno o varios indicadores del PIGCCT.                  
> **Para:** definir a qué componentes del PIGCCT da respuesta la acción.

## CRITERIOS DE ACEPTACIÓN

### 1. Orden de selección jerárquica

1.1 El sistema debe permitir la selección de los componentes en el siguiente orden:

- Eje.
- Medida.
- Indicador.

1.2 El sistema debe garantizar que la selección respete la jerarquía del PIGCCT.

### 2. Asociación con indicadores

2.1 El sistema debe permitir asociar la acción territorial a uno o varios indicadores.                     
2.2 Solo deben poder seleccionarse indicadores existentes en el PIGCCT.

### 3. Consistencia de la selección

3.1 Los indicadores seleccionados deben corresponder a la medida y al eje previamente seleccionados.                      
3.2 El sistema debe impedir selecciones que rompan la coherencia eje–medida–indicador.

### 4. Integración con el sistema

4.1 La asociación eje–medida–indicador debe quedar registrada para la acción territorial.                    
4.2 La información debe estar disponible para los módulos de seguimiento y análisis.

### 5. Usabilidad y experiencia de usuario

5.1 La interfaz debe ser clara, intuitiva y consistente con el diseño general del sistema.
5.2 El sistema debe permitir cancelar la operación sin guardar cambios.

### Resultado esperado

El sistema permite asociar acciones territoriales a uno o varios indicadores del PIGCCT mediante una selección jerárquica coherente de eje, medida e indicador, garantizando consistencia en el seguimiento y análisis de la información.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-067.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-067.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-062-081.png)
