## HU-pigcct-sym-022
> **Identificador Historia de Usuario:** HU-pigcct-sym-022 \
> **Nombre Historia de Usuario:** Módulo de restauración - Pestaña Catálogo

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario.
> 
> **Quiero:** al cargar esta pestaña 'Catálogo' se traerán los elementos temáticos disponibles y podré verlos en un listado agrupado de elementos temáticos que contienen capas de información con características o finalidades comunes, y que pueden ser de origen interno o externo. Cada grupo debe mostrar:
> 
> - El nombre del eje temático.
> - La cantidad de capas contenidas en dicho grupo.
> - Una imagen miniatura o mapa de vista previa representativa del conjunto.
> - Debe incluirse un campo de búsqueda en la parte superior de la pestaña para localizar capas fácilmente, a partir del diligenciamiento del nombre o palabras clave.
> - Al hacer clic sobre un eje temático, el sistema debe desplegar una nueva vista con el listado detallado de capas asociadas, mostrando:
>   - Nombre de la capa
>   - Institución fuente o responsable
>   - Indicador de tipo de fuente (interna o externa)
>   - Miniatura de mapa de referencia
> - Cuando el usuario selecciona una capa dentro de un grupo temático del catálogo, el sistema debe desplegar un panel de detalle que incluya la siguiente información y funcionalidad:
>   - Título o nombre completo de la capa.
>   - Miniatura del mapa o imagen representativa asociada a la capa, permitiendo identificación visual rápida.
>   - Nombre del servicio asociado a la capa, especificando claramente la temática y período de los datos.
>   - Responsable interno o el equipo responsable de la generación y mantenimiento de la capa.
>   - Entidad responsable principal, en este caso, IDEAM.
>   - Tipo de servicio, indicando si la capa es ofrecida como WMS, WFS u otro protocolo geoespacial estándar.
>   - Condiciones de uso, donde se especifique la política de uso de datos, incluyendo atribuciones, limitaciones y responsabilidades para el usuario final.
>   - Botón de agregar la capa al mapa para su visualización inmediata en el visor principal.
>   - Selector de formatos de descarga si la capa permite exportación de datos en diferentes formatos, mostrando las opciones correspondientes (ver numeral DESCARGA DE DATOS).
>   - Botón de descarga activo según las opciones seleccionadas (ver numeral DESCARGA DE DATOS).
>   - Todos estos elementos deben disponerse de forma clara y organizada, priorizando la facilidad de consulta y la interacción directa para agregar capas al mapa o descargar datos según disponibilidad.

> **Para:** que permita la búsqueda e identificación de elementos temáticos que contengan capas de información.
## CRITERIOS DE ACEPTACIÓN

1. **La búsqueda debe arrojar solo resultados con relación a la misma**
2. **Deberá cumplir las características dadas por el diseño**
3. **Podré hacer clic sobre el elemento y ver comportamiento dado por diseño**
4. **Traer elementos temáticos**
5. **La navegacion a los detalles de cada elementos y capas  debe ser consecuente a lo que se esta consultando**

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-pigcct-sym-022.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-pigcct-sym-022.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-001.png)