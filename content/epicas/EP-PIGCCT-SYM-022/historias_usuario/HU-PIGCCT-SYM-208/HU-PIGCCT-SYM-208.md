# HU-PIGCCT-SYM-208
## Épica: Visor geográfico del PIGCCT 
### Representación diferenciada de cobertura
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** que el sistema diferencie visualmente en el mapa las acciones con cobertura departamental y las acciones asociadas a municipios específicos.  
> **Para:** interpretar correctamente su alcance territorial.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Diferenciación por tipo de cobertura
1.1 El sistema identifica si una acción corresponde a cobertura departamental o a municipios específicos.

1.2 Las acciones departamentales y municipales se gestionan como tipos de cobertura distintos en el modelo de datos.

1.3 El tipo de cobertura se mantiene consistente en todas las visualizaciones del sistema.

### 2. Simbología diferenciada
2.1 Las acciones con cobertura departamental se representan con una simbología distinta a las municipales (color, patrón, borde o transparencia).

2.2 Las acciones municipales se representan de forma clara y diferenciable entre sí.

2.3 La simbología utilizada permite identificar el tipo de cobertura sin ambigüedad.

### 3. Capas y control de visualización
3.1 El mapa permite activar o desactivar capas separadas para acciones departamentales y municipales.

3.2 El estado de visibilidad de las capas se conserva durante la sesión del usuario.

3.3 El usuario puede visualizar ambas capas simultáneamente sin pérdida de claridad.

### 4. Leyenda y contextualización
4.1 La leyenda del mapa indica claramente la diferencia entre acciones departamentales y municipales.

4.2 La leyenda se actualiza dinámicamente según las capas visibles.

4.3 La información presentada en la leyenda es coherente con la simbología aplicada.

### 5. Interacción y consulta
5.1 Al seleccionar una acción, el sistema muestra su tipo de cobertura territorial.

5.2 El panel contextual indica si la acción es departamental o municipal.

5.3 La interacción con las acciones no genera confusión entre los dos tipos de cobertura.

### 6. Usabilidad y rendimiento
6.1 La diferenciación visual es clara incluso en niveles altos de zoom o con múltiples acciones visibles.

6.2 El rendimiento del mapa no se ve afectado por la visualización simultánea de ambas coberturas.

6.3 La experiencia de usuario se mantiene consistente entre dispositivos y resoluciones.

---

## Resultado esperado

El usuario puede identificar de forma inmediata y precisa si una acción del PIGCCT tiene cobertura departamental o municipal, gracias a una diferenciación visual clara en el mapa, lo que facilita el análisis territorial y evita interpretaciones erróneas del alcance de cada acción.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-208.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-208.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-208.png)
