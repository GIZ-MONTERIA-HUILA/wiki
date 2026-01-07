# HU-PIGCCT-SYM-054  
## Épica: Administración de indicadores del PIGCCT  
### Definir función objetivo del indicador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** definir la función objetivo del indicador.  
> **Para:** orientar correctamente el análisis y la interpretación de los resultados del seguimiento del PIGCCT, identificando si el desempeño esperado es maximizar o minimizar el valor del indicador.



## CRITERIOS DE ACEPTACIÓN

### 1. Definición del campo función objetivo
1.1 El sistema debe disponer de un campo denominado **función_objetivo**.  
1.2 El campo debe ser de tipo **enumerado** o lista cerrada.  
1.3 Los únicos valores permitidos para el campo deben ser:
- **maximizar**  
- **minimizar**



### 2. Selección y validación
2.1 El usuario administrador debe seleccionar obligatoriamente uno de los valores permitidos.  
2.2 El sistema no debe permitir valores diferentes a **maximizar** o **minimizar**.  
2.3 El sistema debe mostrar un mensaje de validación si el campo no es diligenciado.



### 3. Integración con el análisis del indicador
3.1 La función objetivo debe ser utilizada como referencia en los módulos de análisis, seguimiento y visualización de resultados del indicador.  
3.2 El sistema debe considerar la función objetivo para interpretar tendencias, alertas y comparaciones respecto a la línea base o metas definidas.



### 4. Visualización y edición
4.1 La función objetivo del indicador debe ser visible en el formulario de creación y edición del indicador.  
4.2 El usuario administrador debe poder modificar la función objetivo, siempre que no se afecte la coherencia de los resultados históricos.  
4.3 Cualquier modificación debe quedar registrada en la trazabilidad del indicador.



### 5. Integridad con el indicador
5.1 La función objetivo debe quedar asociada de manera directa y permanente al indicador.  
5.2 El sistema debe asegurar consistencia entre la función objetivo y el tipo de indicador cuando aplique.



### Resultado esperado

El sistema permite definir de forma clara si un indicador busca maximizar o minimizar su valor, fortaleciendo la correcta interpretación, análisis comparativo y toma de decisiones en el seguimiento del PIGCCT.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-054.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-054.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)
