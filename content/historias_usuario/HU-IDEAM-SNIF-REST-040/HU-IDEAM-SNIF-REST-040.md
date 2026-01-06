## HU-pigcct-sym-040

> **Identificador Historia de Usuario:** hu-pigcct-sym-040 \
> **Nombre Historia de Usuario:** Módulo de restauración - Consulta por Capa Geográfica

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario solicitante. \
> **Quiero:** realizar una consulta espacial importando una capa vectorial en formato polígono. \
> **Para:** usarla como delimitador geográfico y obtener los elementos que intersecten su área.

## CRITERIOS DE ACEPTACIÓN

1.  Incluir la opción 'Consulta por capa geográfica' en la pestaña Consultas.
2.  Permitir cargar archivos en formatos GeoJSON, Shapefile (ZIP) o KML.
3.  Validar que contengan geometrías tipo polígono o multipolígono.
4.  Permitir ejecutar, visualizar y descargar los resultados (ver [HU-pigcct-sym-037](/content/historias_usuario/HU-pigcct-sym-037/HU-pigcct-sym-037.md), [HU-pigcct-sym-038](/content/historias_usuario/HU-pigcct-sym-038/HU-pigcct-sym-038.md) y [HU-pigcct-sym-039](/content/historias_usuario/HU-pigcct-sym-039/HU-pigcct-sym-039.md)).
5.  Cumplir lineamientos de diseño y seguridad institucional IDEAM.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-040.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-040.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-040A.png)
![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-040B.png)

## ANEXOS

- Ejemplo de consulta espacial mediante API REST.
- Ejemplo de respuesta en formato GeoJSON.
- Referencia a numeral **Consulta por Capa Geográfica** del visor geográfico.
