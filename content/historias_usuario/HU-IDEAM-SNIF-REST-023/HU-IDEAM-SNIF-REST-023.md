## HU-pigcct-sym-023
> **Identificador Historia de Usuario:** HU-pigcct-sym-023 \
> **Nombre Historia de Usuario:** Módulo de restauración - Pestaña Consultas

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario.
> 
> **Quiero:** al ingresar a esta pestaña 'Consultas' se mostrarán los menús de consulta:
> 
>  - **Consulta atributiva**    :
>>   - **Selección de elemento o capa:**
>     - El usuario debe seleccionar el elemento o capa geográfica sobre la que se ejecutará la consulta.
>     - Solo deben mostrarse capas habilitadas para consulta pública o según el rol del usuario.
>     - La lista de capas debe cargarse dinámicamente desde el catálogo del sistema.
>   
>>  - **Filtros de búsqueda atributiva:**
>     - El sistema debe permitir definir uno o varios filtros de búsqueda combinables.
>     - Cada filtro debe:
>       - Cargar dinámicamente con los valores válidos (listas desplegables o campos autocompletables).
>       - Validar que al menos un campo tenga valor antes de ejecutar la búsqueda.
>       - Si ningún filtro es ingresado, mostrar mensaje "Debe seleccionar al menos un criterio de búsqueda".
>   
>>   - **Ejecución de la consulta:**
>     - El sistema debe construir internamente una consulta SQL parametrizada o un request REST contra la base de datos espacial.
>     - La consulta debe optimizar el uso de índices espaciales y atributivos.
>     - Debe incluir una paginación o límite máximo de resultados (por ejemplo, 500 registros por solicitud).
>   
>>   - **Visualización de resultados:**
>     - Los resultados deben mostrarse en el mapa y en una tabla de atributos, debajo o al costado.
>     - Cada resultado debe incluir atributos básicos, y una opción que permita centrar el mapa en ese elemento.
>     - Debe permitir seleccionar un resultado individual para ver su detalle.
>     - Debe permitir descargar el listado de coincidencias en formatos geográficos y en Excel (ver numeral DESCARGAR CAPAS).
>     - Se permite limpiar los resultados con un botón "Reiniciar".
> 

> - **Consulta espacial**, el sistema debe permitir al usuario dibujar una geometría (punto, línea o polígono) sobre el mapa y buscar aquellos elementos geográficos almacenados en la base de datos que intersecten, contengan o estén contenidos dentro de dicha geometría:
>   - **Activación del modo de consulta espacial:**
>     - El sistema debe contar con una opción de menú que active el modo de dibujo sobre el mapa.
>     - Una vez activado, se despliega una barra de herramientas para seleccionar el tipo de geometría a usar: punto, línea, polígono, rectángulo o círculo.
>   
>   - **Captura y validación de la geometría:**
>     - El sistema debe permitir al usuario dibujar directamente sobre el mapa, y visualizar la geometría resultante con estilo destacado.
>     - Una vez finalizado el dibujo, la geometría debe:
>       - Validarse para asegurar que no esté vacía ni sea inválida.
>   
>   - **Tipos de relación espacial:**
>     - El sistema debe ofrecer al usuario la posibilidad de elegir el tipo de relación espacial que se aplicará en la búsqueda: Intersecta (por defecto), Contiene, Está contenido en, Cercano a (usando un buffer configurable).
>   
>   - **Ejecución de la consulta:**
>     - Al confirmar la búsqueda, el sistema debe construir una consulta espacial sobre la base de datos, ejecutando una petición asíncrona (REST) al servicio geoespacial.
>     - La consulta debe optimizar el uso de índices espaciales y atributivos.
>     - Debe incluir una paginación o límite máximo de resultados (por ejemplo, 500 registros por solicitud).
>   
>   - **Visualización de resultados:**
>     - Los resultados deben representarse en el mapa con un color o borde diferenciado.
>     - Los resultados deben mostrarse en el mapa y en una tabla de atributos, debajo o al costado.
>     - Cada resultado debe incluir atributos básicos, y una opción que permita centrar el mapa en ese elemento.
>     - Debe permitir seleccionar un resultado individual para ver su detalle.
>     - Debe permitir descargar el listado de coincidencias en formatos geográficos y en Excel (ver numeral DESCARGAR CAPAS).
> 

> - **Consulta por coordenadas**, permite al usuario realizar una búsqueda espacial puntual o por proximidad (buffer) a partir de coordenadas digitadas manualmente:
>   - **Ingreso de coordenadas:**
>     - El sistema debe permitir ingresar coordenadas en diferentes sistemas de referencia (por defecto MAGNA SIRGAS 2018 / Origen Nacional (EPSG:9377), y opcionalmente WGS84- EPSG:4326).
>     - El usuario podrá definir:
>       - Tipo de consulta: puntual o con buffer.
>       - Radio del buffer (en metros), con validación de rango (por ejemplo, entre 10m y 10.000m).
>   
>   - **Ejecución de intersección espacial:**
>     - El sistema debe ejecutar una intersección espacial entre el punto/buffer y las capas disponibles en la base de datos geográfica.
>     - Los resultados deben listar todos los elementos que intersecten el área consultada, con sus atributos principales.
>   
>   - **Validaciones:**
>     - Verificación del formato de coordenadas (decimal o grados-minutos-segundos).
>     - Validación de los rangos permitidos de latitud y longitud.
>     - Manejo de errores en caso de que las coordenadas estén fuera del dominio del país o del sistema de referencia.
>   
>   - **Ejecución de la consulta:**
>     - Al confirmar la búsqueda, el sistema debe construir una consulta espacial sobre la base de datos, ejecutando una petición asíncrona (REST) al servicio geoespacial.
>     - La consulta debe optimizar el uso de índices espaciales y atributivos.
>     - Debe incluir una paginación o límite máximo de resultados (por ejemplo, 500 registros por solicitud).
>   
>   - **Visualización de resultados:**
>     - Los resultados deben representarse en el mapa con un color o borde diferenciado.
>     - Los resultados deben mostrarse en el mapa y en una tabla de atributos, debajo o al costado.
>     - Cada resultado debe incluir atributos básicos, y una opción que permita centrar el mapa en ese elemento.
>     - Debe permitir seleccionar un resultado individual para ver su detalle.
>     - Debe permitir descargar el listado de coincidencias en formatos geográficos y en Excel (ver numeral DESCARGAR CAPAS).
> 

> - **Consulta de capa geográfica**, permite importar una capa vectorial en formato polígono para usarla como delimitador espacial en una consulta de intersección:
>   - **Carga de archivo:**
>     - El usuario podrá cargar una capa en los siguientes formatos: GeoJSON, Shapefile (ZIP) o KML.
>     - El sistema debe validar que el archivo cargado contiene geometrías de tipo polígono o multipolígono.
>     - El tamaño del archivo no excede un límite predefinido (por ejemplo, 10 MB).
>     - La capa tenga un sistema de referencia definido.
>   
>   - **Procesamiento de la capa:**
>     - Una vez validada, la capa servirá como máscara espacial para consultar las entidades dentro o que intersecten el polígono.
>     - El sistema debe permitir la visualización inmediata de la capa cargada y resaltar el área de consulta.
>   
>   - **Validaciones:**
>     - Detección del tipo de geometría antes de procesar.
>     - Validación de topología (geometrías válidas, no autointersectadas).
>     - Rechazo de geometrías vacías o corruptas.
>     - Control de cantidad máxima de vértices por geometría para evitar sobrecargas.
> 

> 
> - **Descargar capas**, el sistema debe permitir la descarga de elementos geográficos seleccionados desde diversas partes del módulo de restauración del SNIF, incluyendo resultados de consultas atributivas, consultas espaciales y opciones directas de descarga desde el catálogo de capas o la interfaz de detalle de capas:
>   - **Origen de las descargas:**
>     - El usuario podrá descargar datos:
>       - Desde la pestaña Catálogo, en el detalle de una capa.
>       - Desde resultados de consultas atributivas (ver numeral CONSULTAS).
>       - Desde resultados de consultas espaciales (ver numeral CONSULTAS).
>       - Desde widgets u opciones directas de descarga habilitadas en el visor.
>   
>   - **Formatos de descarga soportados:**
>     - El sistema deberá ofrecer la posibilidad de exportar los datos en los siguientes formatos:
>       - **GeoJSON (.geojson):** Formato ligero para intercambio web. Compatible con la mayoría de visores SIG y aplicaciones web. Debe garantizarse que la codificación sea UTF-8 y el sistema de referencia sea EPSG:4326.
>       - **Shapefile (.shp):** Formato estándar ESRI. Se entregará comprimido en un único archivo .zip que contenga todos los archivos requeridos (.shp, .shx, .dbf, .prj). El sistema debe verificar que no se superen los 10 MB por descarga y que los nombres de campo no excedan 10 caracteres.
>       - **KML (.kml):** Formato de intercambio geoespacial usado por Google Earth y aplicaciones 3D. Solo se exportarán atributos esenciales y se asegurará la proyección EPSG:4326 (WGS84).
>   
>   - **Sistema de Referencia Espacial (CRS):**
>     - Todos los datos exportados deberán reproyectarse automáticamente al sistema de coordenadas EPSG:4326 (WGS84), garantizando compatibilidad universal con visores web y aplicaciones SIG.
>     - En caso de que el dataset original esté en otro sistema, se realizará la transformación mediante funcionales geoespaciales, como ST_Transform en PostgreSQL / PostGIS.
>     - En cada archivo exportado deberá incluirse el archivo de definición de proyección (.prj) o el atributo CRS correspondiente.
>   
>   - **Parámetros y Condiciones de descarga:**
>     - En la descarga de shapefiles, los nombres de los campos deben truncarse a un máximo de 10 caracteres para cumplir con el estándar DBF/dbase.
>     - Toda exportación debe mostrar de forma clara, el número de registros, la fecha de descarga, y los metadatos principales en el nombre del archivo, o en un archivo adicional de metadatos.
>   
>   - **Validaciones:**
>     - Verificar que el conjunto de datos seleccionados contenga geometría válida.
>     - Omitir registros con geometrías vacías o nulas.
>     - Verificar que los nombres de campo sean válidos según el formato destino:
>       - Shapefile: máximo 10 caracteres.
>       - GeoJSON / KML: sin restricciones, pero sin caracteres especiales.
>     - Validar que el formato seleccionado sea compatible con el tipo de geometría.
>     - Mostrar mensajes de error y logs en caso de fallos durante la exportación (ver numeral REGISTROS DEL SISTEMA).
>     - Las descargas deben estar limitadas en volumen o extensión geográfica para evitar sobrecarga del sistema (por ejemplo, máximo 10.000 registros por petición o 10 MB por archivo).
>     - Si la selección supera el límite, el sistema debe mostrar un mensaje informando (ver numeral REGISTROS DEL SISTEMA), el motivo.
>   
>   - **Interfaz y funcionalidad:**
>     - El usuario podrá elegir el formato de salida desde un menú desplegable o modal de selección.
>     - El proceso de descarga debe realizarse mediante una interfaz clara y botón único "Descargar datos", visible en los elementos funcionales requeridos para esta acción.
>     - Los archivos generados deben poder abrirse en QGIS, ArcGIS, Google Earth y visores web.
>     - El sistema validará los permisos del usuario antes de permitir la descarga, conforme el rol o nivel de acceso.
>     - Toda descarga deberá registrarse en una tabla de logs (REGISTROS DEL SISTEMA) con: usuario, fecha, capa descargada, tipo de consulta, y formato seleccionado.
> 
> **Para:** lograr consultas más especializadas y por diferentes frentes.

## CRITERIOS DE ACEPTACIÓN

### **Funcionalidad General:**
1. **La pestaña 'Consultas' debe mostrar cuatro opciones principales: Consulta atributiva, Consulta espacial, Consulta por coordenadas y Consulta de capa geográfica**
2. **El sistema debe mostrar un botón "Descargar capas" visible desde resultados de consultas y catálogo**

### **Consulta Atributiva:**
3. **Debe permitir seleccionar capas geográficas habilitadas según el rol del usuario**
4. **La lista de capas debe cargarse dinámicamente desde el catálogo del sistema**
5. **Debe permitir definir múltiples filtros de búsqueda combinables con validación de campos**
6. **Si no se ingresa ningún filtro, debe mostrar el mensaje "Debe seleccionar al menos un criterio de búsqueda"**
7. **Los resultados deben mostrarse tanto en el mapa como en una tabla de atributos**
8. **Debe incluir paginación con límite máximo de 500 registros por solicitud**

### **Consulta Espacial:**
9. **Debe activar un modo de dibujo con barra de herramientas para geometrías: punto, línea, polígono, rectángulo y círculo**
10. **La geometría dibujada debe visualizarse con estilo destacado en el mapa**
11. **Debe validar que la geometría no esté vacía ni sea inválida antes de ejecutar la consulta**
12. **Debe ofrecer tipos de relación espacial: Intersecta (por defecto), Contiene, Está contenido en, Cercano a**
13. **Los resultados deben representarse en el mapa con color diferenciado**

### **Consulta por Coordenadas:**
14. **Debe permitir ingresar coordenadas en MAGNA SIRGAS 2018 (EPSG:9377) y WGS84 (EPSG:4326)**
15. **Debe ofrecer consulta puntual y con buffer, validando rango entre 10m y 10.000m**
16. **Debe validar formato de coordenadas (decimal o grados-minutos-segundos)**
17. **Debe mostrar error si las coordenadas están fuera del dominio del país**

### **Consulta de Capa Geográfica:**
18. **Debe aceptar archivos en formatos GeoJSON, Shapefile (ZIP) y KML**
19. **Debe validar que contiene geometrías de tipo polígono o multipolígono**
20. **Debe rechazar archivos que excedan 10 MB**
21. **Debe visualizar inmediatamente la capa cargada y resaltar el área de consulta**
22. **Debe rechazar geometrías vacías, corruptas o autointersectadas**

### **Descarga de Capas:**
23. **Debe ofrecer descarga en formatos GeoJSON, Shapefile y KML**
24. **Todos los archivos deben reproyectarse automáticamente a EPSG:4326 (WGS84)**
25. **Debe validar permisos del usuario antes de permitir la descarga**
26. **Los archivos generados deben abrirse correctamente en QGIS, ArcGIS y Google Earth**

### **Validaciones y Controles:**
27. **Debe limitar descargas a máximo 10.000 registros o 10 MB por archivo**
28. **Si se supera el límite, debe mostrar mensaje informativo claro**
29. **Toda descarga debe registrarse en logs con: usuario, fecha, capa, tipo de consulta y formato**
30. **Cada resultado debe incluir opción para centrar el mapa y ver detalle individual**

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA ATRIBUTIVO](assets/secuencia-atributiva-HU-pigcct-sym-023.png)

![IMAGEN DIAGRAMA DE SECUENCIA ESPACIAL](assets/secuencia-espacial-HU-pigcct-sym-023.png)

![IMAGEN DIAGRAMA DE SECUENCIA GEOGRAFICO](assets/secuencia-capa-geo-HU-pigcct-sym-023.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO ATRIBUTIVO](assets/actividades-atributiva-HU-pigcct-sym-023.png)
![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO ESPACIAL](assets/actividades-espacial-HU-pigcct-sym-023.png)
![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO GEOGRAFICO](assets/actividades-capa-geo-HU-pigcct-sym-023.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-001.png)