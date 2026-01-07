## HU-pigcct-sym-110

> **Identificador Historia de Usuario:** hu-pigcct-sym-110 \
> **Nombre Historia de Usuario:** Módulo de restauración - Creación de Indicador de Monitoreo (Reglas Condicionales y Guardado).

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** ingresar la línea base y la unidad de medida según el tipo de indicador.   \
> **Para:** asegurar la coherencia de los datos de monitoreo.

## CRITERIOS DE ACEPTACIÓN

1. **Creación de Indicador (Condicionales y Flujo)**  
1.1 Dado que el usuario define el campo **tipo_indicador**, cuando selecciona la opción `CUANTITATIVO`, entonces los campos **unidad_medida** y **linea_base numérica** deben ser **obligatorios**. \
1.2 Dado que el indicador es de tipo **CUANTITATIVO**, cuando el usuario completa el campo **linea_base**, entonces el sistema debe validar que el valor sea **numérico** y **mayor o igual a 0 (≥ 0)**. \
1.3 Dado que el indicador es de tipo **CUALITATIVO**, cuando el usuario completa el campo **linea_base**, entonces el sistema debe validar que el valor sea **texto**, con una longitud mínima de **5 caracteres** y máxima de **500 caracteres**. \
1.4 Dado que el usuario intenta guardar un indicador, cuando falta algún **campo obligatorio**, entonces el sistema debe mostrar un **mensaje de error específico bajo el campo correspondiente** y **no debe permitir guardar** el registro. \
1.5 Dado que el usuario completa correctamente todos los campos requeridos, cuando guarda el indicador, entonces el sistema debe **crear el registro en la base de datos** y asociarlo al **`id_proyecto`** correspondiente. \
1.6 Dado que el indicador fue creado exitosamente, cuando se confirma el guardado, entonces el sistema debe mostrar el mensaje: **“Indicador creado correctamente.”** y registrar el evento en los **logs del sistema** con los datos: `usuario`, `acción`, `id_proyecto` e `id_indicador`. \

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-110.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-110.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-110.png)

## ANEXOS

-	[HU-pigcct-sym-101](/content/historias_usuario/HU-pigcct-sym-101/HU-pigcct-sym-101.md)
-  Mapeo de errores de validación a mensajes específicos.