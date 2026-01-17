# HU-PIGCCT-SYM-210
## Épica: Visor geográfico del PIGCCT 
### Filtrar acciones por municipio
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** filtrar las acciones del PIGCCT por municipio en el visor geográfico.  
> **Para:** analizar de manera detallada las intervenciones a nivel local.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Disponibilidad del filtro
1.1 El sistema dispone de un filtro de municipios accesible desde el visor geográfico.

1.2 El filtro permite la selección múltiple de municipios.

1.3 El listado de municipios corresponde al catálogo oficial vigente y se encuentra correctamente asociado a su departamento.

### 2. Funcionamiento del filtro
2.1 Al seleccionar uno o más municipios, el visor muestra únicamente las acciones asociadas a los municipios seleccionados.

2.2 Las acciones con cobertura municipal se visualizan solo en los municipios filtrados.

2.3 Las acciones con cobertura departamental se muestran únicamente si incluyen los municipios seleccionados.

### 3. Comportamiento del mapa
3.1 El mapa ajusta automáticamente la extensión geográfica a los municipios seleccionados.

3.2 Los municipios no seleccionados no se visualizan o se muestran atenuados.

3.3 El nivel de zoom se ajusta de forma óptima para permitir la visualización simultánea de múltiples municipios.

### 4. Integración con otros filtros
4.1 El filtro por municipio es compatible con otros filtros del visor (departamento, tipo de acción, estado, periodo, etc.).

4.2 Cuando se combina con el filtro por departamento, el sistema muestra únicamente los municipios pertenecientes al departamento seleccionado.

4.3 Los filtros se aplican de forma acumulativa sin generar inconsistencias.

### 5. Gestión y restablecimiento del filtro
5.1 El sistema permite agregar o retirar municipios de la selección en cualquier momento.

5.2 El sistema ofrece una opción para limpiar el filtro y restaurar la visualización completa.

5.3 El estado del filtro se refleja claramente en la interfaz del visor.

### 6. Usabilidad y desempeño
6.1 La aplicación del filtro presenta un tiempo de respuesta adecuado, incluso con múltiples municipios seleccionados.

6.2 La interacción con el filtro es intuitiva y facilita la selección y deselección de municipios.

6.3 El funcionamiento del filtro es consistente en distintos navegadores y dispositivos.

---

## Resultado esperado

El usuario puede analizar de manera precisa las acciones del PIGCCT a nivel municipal, seleccionando uno o varios municipios, lo que permite focalizar intervenciones locales y mejorar el seguimiento territorial de las acciones.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-210.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-210.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-210.png)
