## HU-pigcct-sym-119

> **Identificador Historia de Usuario:** hu-pigcct-sym-119 \
> **Nombre Historia de Usuario:** Módulo de restauración - Consultar y Visualizar Áreas Restauradas.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  \
> **Quiero:** visualizar las áreas restauradas de un proyecto en el mapa y en una tabla, y poder filtrarlas por atributos.   \
> **Para:** revisar los atributos registrados, su localización espacial y facilitar el análisis y seguimiento.

## CRITERIOS DE ACEPTACIÓN

1. **Visualización Espacial y Tabular**     
    1.1.	**Visualización por proyecto (Zoom automático)**: Al seleccionar un proyecto, el mapa debe centrar y realizar zoom automático sobre la extensión de las áreas restauradas asociadas.    
    1.2.	El sistema debe mostrar una tabla con las áreas restauradas del proyecto seleccionado, incluyendo un subconjunto de atributos clave para la visualización inicial (Ej: ID, Ecosistema, Área Hectáreas).     
    1.3.	**Pop-up con atributos principales**: Al hacer clic sobre una geometría (polígono) en el mapa, se debe desplegar un pop-up interactivo con los atributos principales del área restaurada.

2. **Funcionalidades de Filtro**    
    2.1.	El sistema debe permitir al usuario aplicar filtros por atributos temáticos, incluyendo al menos:
    - Ecosistema
    - Modelo de intervención
    - Tipo de propiedad     
    
    2.2.	La aplicación de filtros debe actualizar dinámicamente tanto la vista tabular como la vista espacial (mapa).

3. **Exportación y Trazabilidad**   
3.1. El sistema debe permitir al usuario exportar los datos del conjunto de áreas visualizado (aplicando filtros si existen) a los formatos: *GeoJSON* (para uso espacial) o *Excel* (para análisis tabular).   
3.2.	**Registro de logs de consulta**: Toda acción de consulta, filtro o exportación debe generar un registro de log (log\_sistema) con: usuario, hora y acción (Ej: CONSULTA_AREAS, EXPORTAR_AREAS).





## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-119.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-119.png)


## ANEXOS

- Definición de los atributos clave que deben aparecer en el pop-up y en la tabla inicial.

