## HU-pigcct-sym-114

> **Identificador Historia de Usuario:** hu-pigcct-sym-114 \
> **Nombre Historia de Usuario:** Módulo de restauración - Gestión de Adjuntos.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** subir documentos y archivos relacionados con el área restaurada.   \
> **Para:** mantener evidencia documental del proceso.

## CRITERIOS DE ACEPTACIÓN
1. **Enfoque / Estrategia de Restauración**  
1.1 Dado que el usuario ha creado o actualizado un área restaurada, cuando el sistema guarda correctamente la información del área, entonces la pestaña **“Adjuntos”** debe habilitarse automáticamente dentro del formulario. \
1.2 Dado que el usuario carga un archivo adjunto asociado a un área restaurada, cuando el sistema almacena la información, entonces debe guardar el registro en la tabla **`adjuntos`**, asignando los valores: `tabla_referida = 'área_restaurada'` e `id_area_restaurada` correspondiente. \
1.3 Dado que el usuario accede a la pestaña de adjuntos, cuando desea subir archivos, entonces el sistema debe permitir la **carga de múltiples tipos de archivos** no geográficos, tales como **PDF, Word, imágenes o ZIP**, según lo definido en las reglas de **CARGA DE ARCHIVOS NO GEOGRÁFICOS**. \
1.4 Dado que el usuario intenta cargar un archivo, cuando el sistema valida su tamaño, entonces debe **rechazar cualquier archivo que supere el límite máximo permitido** (por ejemplo, **50 MB**) y mostrar un mensaje de advertencia. \
1.5 Dado que el usuario carga un archivo con un nombre existente dentro del mismo proyecto, cuando ocurre la validación, entonces el sistema debe **impedir la carga de archivos duplicados** por nombre y mostrar un mensaje de error informativo. \
1.6 Dado que el usuario carga un archivo de tipo **geográfico** (por ejemplo, `GeoJSON`, `KML` o `Shapefile ZIP`), cuando el sistema procesa la carga, entonces debe **validar el formato y el tamaño** del archivo conforme a las especificaciones de las historias [HU-pigcct-sym-103](/content/historias_usuario/HU-pigcct-sym-103/HU-pigcct-sym-103.md) y [HU-pigcct-sym-104](/content/historias_usuario/HU-pigcct-sym-104/HU-pigcct-sym-104.md). \
1.7 Dado que existen archivos adjuntos registrados, cuando el usuario visualiza la pestaña “Adjuntos”, entonces el sistema debe mostrar una **tabla resumen** con los archivos cargados y ofrecer las opciones de **Descargar** y **Eliminar** para cada uno. \
1.8 Dado que se produce un error durante la validación o carga de un archivo, cuando el sistema detecta la falla, entonces debe mostrar un **mensaje informativo de error** al usuario y registrar el evento en los **registros del sistema** según las políticas definidas. \

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-114.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-114.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-114.png)

## ANEXOS

-	[HU-pigcct-sym-101](/content/historias_usuario/HU-pigcct-sym-101/HU-pigcct-sym-101.md)
-  Mapeo de errores de validación a mensajes específicos.