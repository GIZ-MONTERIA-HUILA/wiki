## HU-pigcct-sym-092

> **Identificador Historia de Usuario:** hu-pigcct-sym-092 \
> **Nombre Historia de Usuario:** Módulo de restauración - Proceso de carga y estandarización de archivos geográficos

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario técnico con rol de editor o superior. \
> **Quiero:**  poder subir archivos geoespaciales (Shapefile, GeoJSON, KML) al sistema.   \
> **Para:** asociar información de límites, predios o zonas de manejo georreferenciadas a un registro específico.

## CRITERIOS DE ACEPTACIÓN

1. **Validación Geoespacial**  
   1.1 El sistema debe validar el formato y la estructura de los archivos (.geojson, .kml, .zip con Shapefile) antes de iniciar el procesamiento (Ver (Ver [HU-pigcct-sym-093](/content/historias_usuario/HU-pigcct-sym-093/HU-pigcct-sym-093.md))).    
   1.2. Se debe verificar la presencia del Sistema de Referencia Espacial (EPSG) en los Shapefiles.

2. **Procesamiento y Estandarización**  
   2.1 El sistema debe estandarizar todos los archivos cargados al formato interno GeoJSON (utilizando librerías como GDAL o similar).    
   2.2. Solo los usuarios con rol editor o superior pueden realizar esta carga (Ver [HU-pigcct-sym-094](/content/historias_usuario/HU-pigcct-sym-094/HU-pigcct-sym-094.md)).

3. **Retroalimentación y Persistencia**  
   3.1 Tras el procesamiento, se debe mostrar una vista previa en el mapa y notificaciones claras sobre el resultado (éxito/error) (Ver [HU-pigcct-sym-094](/content/historias_usuario/HU-pigcct-sym-094/HU-pigcct-sym-094.md)).     
   3.2. Los metadatos deben registrarse en la tabla ADJUNTOS con campos específicos geográficos.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-092.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-092.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-092.png)

## ANEXOS

- Requerimientos de software (Ej: GDAL, PostGIS) para el procesamiento geoespacial.
