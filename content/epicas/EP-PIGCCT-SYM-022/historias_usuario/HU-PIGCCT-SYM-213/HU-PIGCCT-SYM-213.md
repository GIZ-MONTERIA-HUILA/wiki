# HU-PIGCCT-SYM-213
## Épica: Visor geográfico del PIGCCT 
### Visualizar información resumida en el mapa
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** visualizar un popup o panel informativo al seleccionar una acción en el mapa.  
> **Para:** consultar rápidamente su información clave y apoyar el análisis territorial del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Activación del popup o panel
1.1 Al seleccionar una acción en el visor geográfico (clic o toque), el sistema despliega un popup o panel informativo.

1.2 El popup o panel se activa únicamente cuando la acción es seleccionable según el rol y estado de validación.

1.3 El sistema asegura que solo una acción esté activa a la vez, evitando superposición de información.

### 2. Información mínima mostrada
2.1 El popup o panel muestra el nombre de la acción de forma destacada.

2.2 Se visualiza el eje al que pertenece la acción.

2.3 Se muestra la medida asociada a la acción.

2.4 Se listan los indicadores asociados a la acción.

2.5 Se visualiza el estado de validación de la acción (borrador, en validación, validado).

### 3. Presentación y claridad de la información
3.1 La información se presenta de forma clara, estructurada y legible.

3.2 Los campos están correctamente rotulados para facilitar su comprensión.

3.3 Cuando algún dato no esté disponible, el sistema lo indica de manera explícita (por ejemplo, “No disponible”).

### 4. Comportamiento del panel
4.1 El popup o panel puede cerrarse fácilmente por el usuario.

4.2 Al seleccionar otra acción en el mapa, el contenido del popup o panel se 
actualiza automáticamente.

4.3 El sistema mantiene un comportamiento consistente entre popup flotante o panel lateral, según el diseño definido.

### 5. Integración con el visor y filtros
5.1 La información mostrada respeta los filtros activos (territoriales, temáticos y de estado).

5.2 El popup o panel solo muestra acciones visibles en el mapa.

5.3 El contenido se actualiza correctamente al cambiar filtros o capas.

### 6. Usabilidad y rendimiento
6.1 El despliegue del popup o panel se realiza sin retrasos perceptibles.

6.2 La interacción no afecta el rendimiento del visor geográfico.

6.3 El diseño es compatible con diferentes resoluciones y dispositivos.

---

## Resultado esperado

Al seleccionar una acción en el mapa, el sistema muestra un popup o panel informativo con los datos clave de manera clara, rápida y contextual, mejorando la comprensión, análisis y toma de decisiones sobre las acciones del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-213.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-213.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-213.png)
