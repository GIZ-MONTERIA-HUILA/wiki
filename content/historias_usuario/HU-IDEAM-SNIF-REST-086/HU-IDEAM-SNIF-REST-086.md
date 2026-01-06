## HU-pigcct-sym-086

> **Identificador Historia de Usuario:** hu-pigcct-sym-086 \
> **Nombre Historia de Usuario:** Módulo de restauración - Diseño de la tabla única de archivos adjuntos y trazabilidad relacional

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador de bese de datos. \
> **Quiero:**  implementar la tabla de adjuntos con la estructura y las claves necesarias para la correcta persistencia de la metadata y la trazabilidad relacional.    \
> **Para:** asegurar la documentación y el fácil acceso a los archivos asociados a cualquier elemento del módulo.

## CRITERIOS DE ACEPTACIÓN

1. **Estructura de la Tabla Adjunto**  
   1.1 La tabla debe contener, como mínimo, los siguientes campos para la metadata de cada archivo: id_archivo (PK, autoincremental), nombre_original, nombre_sistema, tipo_archivo (general/geográfico), tipo_mime, ruta_almacenamiento, tamaño_bytes, tabla_referida, id_elemento_referido, usuario_creador, fecha_creacion, estado (para eliminación lógica).

2. **Funcionalidad de Trazabilidad**  
   2.1 Los campos tabla_referida e id_elemento_referido deben garantizar la relación y trazabilidad con las tablas principales.   
    2.2. Se debe poder listar todos los archivos asociados a un elemento con una sola consulta SQL, filtrando por tabla_referida y id_elemento_referido.

3. **Política de Eliminación Lógica**  
   3.1 Los archivos se deben eliminar de manera lógica (actualizando el campo estado = 'INACTIVO'), preservando su registro en la tabla para fines de auditoría y trazabilidad.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-086.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-086.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-086.png)

## ANEXOS

- Script DDL (Data Definition Language) de la tabla adjuntos
