## HU-pigcct-sym-089

> **Identificador Historia de Usuario:** hu-pigcct-sym-089 \
> **Nombre Historia de Usuario:** Módulo de restauración - Proceso de carga y validación de archivos no geográficos

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:**  poder subir archivos documentales (PDF, imágenes, hojas de cálculo) y asociarlos a un registro específico.   \
> **Para:** adjuntar evidencia, reportes o información de soporte a los datos ingresados en el módulo.

## CRITERIOS DE ACEPTACIÓN

1. **Validación de Archivos**  
   1.1 El sistema debe validar el formato (extensión), el tipo MIME y el tamaño máximo del archivo antes de iniciar la subida al servidor (Ver [HU-pigcct-sym-090](/content/historias_usuario/HU-pigcct-sym-090/HU-pigcct-sym-090.md)).   
   1.2. Se debe limitar el tamaño a 10 MB y aceptar solo las extensiones permitidas.

2. **Proceso de Subida (Retroalimentación)**  
   2.1 Durante el proceso de subida, se debe mostrar un indicador de progreso o spinner al usuario (Ver [HU-pigcct-sym-090](/content/historias_usuario/HU-pigcct-sym-090/HU-pigcct-sym-090.md)).         
   2.2. Al finalizar, se debe mostrar una notificación de éxito o error (Ver [HU-pigcct-sym-091](/content/historias_usuario/HU-pigcct-sym-091/HU-pigcct-sym-091.md)).

3. **Almacenamiento y Seguridad**  
   3.1 La metadata del archivo debe registrarse en la tabla ADJUNTOS (Ver HU-086).   
   3.2. Los archivos físicos deben almacenarse en un directorio protegido, y el acceso debe ser mediante endpoints autenticados (Ver [HU-pigcct-sym-091](/content/historias_usuario/HU-pigcct-sym-091/HU-pigcct-sym-091.md)).

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-089.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-089.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-089.png)

## ANEXOS

- Especificación de los mensajes de error para la carga de archivos.
