## HU-pigcct-sym-059
> **Identificador Historia de Usuario:** HU-pigcct-sym-059 \
> **Nombre Historia de Usuario:** Módulo de restauración - Subida de Archivos (File Upload)

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** permitir adjuntar archivos geográficos o documentos desde mi equipo (File Upload). \
> **Para:** complementar la información registrada en el sistema y facilitar la ingesta de nuevas capas o material de soporte.

## CRITERIOS DE ACEPTACIÓN

1. **Funcionalidad de Carga** 1.1. El sistema debe permitir adjuntar archivos mediante un botón de selección de archivo. 1.2. Se debe permitir la subida de múltiples archivos si el contexto lo requiere. 1.3. El sistema debe mostrar el nombre del archivo cargado y permitir eliminarlo antes de enviar.
2. **Validación y Control** 2.1. El sistema debe validar el tipo de archivo permitido (Ej: .zip, .geojson, .pdf) y el tamaño máximo (Ej: 10 MB). 2.2. Si el archivo es una capa geográfica, se debe realizar una validación inicial de su estructura, tipo de geometría y Sistema de Referencia de Coordenadas (CRS). 2.3. Se debe mostrar una barra de progreso de carga (opcional).


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-pigcct-sym-059.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-pigcct-sym-059.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-059.png)
