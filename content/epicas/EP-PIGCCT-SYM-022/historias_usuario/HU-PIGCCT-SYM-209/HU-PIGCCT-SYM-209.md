# HU-PIGCCT-SYM-209
## Épica: Visor geográfico del PIGCCT 
### Filtrar acciones por departamento
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** filtrar las acciones del PIGCCT por departamento en el visor geográfico.  
> **Para:** focalizar el análisis territorial y facilitar la toma de decisiones.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Disponibilidad del filtro
1.1 El sistema ofrece un filtro por departamento visible dentro del visor geográfico.

1.2 El filtro está disponible únicamente para los usuarios con permisos de consulta.

1.3 El listado de departamentos corresponde al catálogo oficial vigente.

### 2. Funcionamiento del filtro
2.1 Al seleccionar un departamento, el visor muestra únicamente las acciones asociadas a dicho departamento.

2.2 Las acciones con cobertura departamental se muestran cuando corresponden al departamento seleccionado.

2.3 El filtro se aplica sin necesidad de recargar la página o reiniciar el visor.

### 3. Comportamiento del mapa
3.1 El mapa ajusta automáticamente la extensión geográfica al departamento seleccionado.

3.2 Los elementos fuera del departamento filtrado no se visualizan o quedan atenuados.

3.3 El nivel de zoom se ajusta de forma adecuada para facilitar la visualización de las acciones.

### 4. Integración con otros filtros
4.1 El filtro por departamento es compatible con otros filtros disponibles en el visor (estado, tipo de acción, periodo, etc.).

4.2 Los filtros aplicados se combinan de forma coherente sin generar inconsistencias en la información mostrada.

4.3 El usuario puede aplicar y retirar filtros en cualquier orden.

### 5. Gestión y restablecimiento del filtro
5.1 El sistema permite limpiar el filtro y volver a la visualización completa del territorio.

5.2 El estado del filtro se refleja visualmente en la interfaz del visor.

5.3 Al limpiar el filtro, el mapa retorna a su extensión inicial.

### 6. Usabilidad y desempeño
6.1 El tiempo de respuesta del filtro es adecuado incluso con grandes volúmenes de datos.

6.2 La interacción con el filtro es intuitiva y comprensible para el usuario.

6.3 El comportamiento del filtro es consistente en distintos navegadores y dispositivos.

---

## Resultado esperado

El usuario puede enfocar el análisis territorial del PIGCCT seleccionando un departamento específico, visualizando de manera clara y eficiente únicamente las acciones relevantes, lo que mejora la interpretación de la información y apoya la toma de decisiones informadas.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-209.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-209.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-209.png)
