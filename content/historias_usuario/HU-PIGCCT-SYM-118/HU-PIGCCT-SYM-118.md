## HU-pigcct-sym-118

> **Identificador Historia de Usuario:** hu-pigcct-sym-118 \
> **Nombre Historia de Usuario:** Módulo de restauración - Edición de Atributos Técnicos, Monitoreo y Financieros.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** editar los datos técnicos de registro, la proyección financiera y la definición del monitoreo.   \
> **Para:** finalizar los atributos temáticos requeridos del área restaurada.

## CRITERIOS DE ACEPTACIÓN
1. **Edición de atributos Técnicos, Monitoreo y Financieros**  
1.1 Dado que el usuario crea un nuevo registro de área restaurada, cuando el sistema genera la información base, entonces debe asignar automáticamente un **identificador único (CA1)** de tipo **UUID**, el cual no puede ser **editado ni modificado manualmente** por el usuario. \
1.2 Dado que el sistema importa la geometría del área restaurada, cuando se completa el proceso de carga del archivo geográfico, entonces debe generarse automáticamente el **campo geom (CA2)** asociado a la geometría del área. Este campo solo podrá **editarse mediante una nueva carga de archivo** que sustituya la geometría existente. \
1.3 Dado que el usuario completa el campo **Número de registro ICA (CA24)**, cuando guarda la información, entonces el sistema debe validar que sea un **campo de texto alfanumérico**, con una longitud máxima de **20 caracteres**. \
1.4 Dado que el usuario selecciona el campo **Fuente semillera (CA25)**, cuando llena el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista desplegable, cargada desde la tabla **`fuente_semillera`**. \
1.5 Dado que el usuario completa el campo **Año de monitoreo (CA26)**, cuando guarda la información, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo **enum**, con los valores posibles: `1er año`, `2do año`, `3er año`, y `>3 años`. \
1.6 Dado que el usuario selecciona el campo **Plazo de monitoreo (CA27)**, cuando completa el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo **enum**, con los valores posibles: `Anual`, `Semestral`, o `Trimestral`. \
1.7 Dado que el usuario completa el campo **Costo proyectado (CA28)**, cuando intenta guardar la información, entonces el sistema debe validar que sea un **campo numérico entero obligatorio**, con un valor **mayor que 0 ( > 0 )**. \
1.8 Dado que el usuario crea un nuevo registro de área restaurada, cuando el sistema almacena la información, entonces debe establecer automáticamente el **Estado del registro (CA29)** con el valor **`UNDER_REVISION`**, y dicho campo debe **reflejar siempre el estado actual** del registro durante su ciclo de vida. \

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-118.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-118.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-118.png)

## ANEXOS

-	[HU-pigcct-sym-115](/content/historias_usuario/HU-pigcct-sym-115/HU-pigcct-sym-115.md)
-  Mapeo de errores de validación a mensajes específicos.