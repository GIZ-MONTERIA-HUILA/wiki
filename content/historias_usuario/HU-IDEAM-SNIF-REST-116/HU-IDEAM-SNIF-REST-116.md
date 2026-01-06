## HU-pigcct-sym-116

> **Identificador Historia de Usuario:** hu-pigcct-sym-116 \
> **Nombre Historia de Usuario:** Módulo de restauración - Edición de Atributos Físicos y Ecológicos.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** modificar los atributos geográficos (altitud) y ecológicos (ecosistema, tensionantes) del área restaurada.   \
> **Para:** asegurar que la caracterización biofísica del área sea correcta y esté actualizada.

## CRITERIOS DE ACEPTACIÓN
1. **Edición de atributos Físicos y Ecológicos**  
1.1 Dado que el usuario completa el campo **Altitud mínima (CA3)**, cuando intenta guardar el registro, entonces el sistema debe validar que sea un **campo obligatorio** de tipo **double**, con un valor **mayor que 0 ( > 0 )**, y que cumpla con el **formato numérico válido**. \
1.2 Dado que el usuario completa el campo **Altitud máxima (CA4)**, cuando intenta guardar la información, entonces el sistema debe validar que sea un **campo obligatorio** de tipo **double**, con un valor **mayor que la altitud mínima**, garantizando la **coherencia entre ambos campos**. \
1.3 Dado que el usuario selecciona el campo **Criterio de selección (CA5)**, cuando llena el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista desplegable, cargada desde la tabla **`criterio_seleccion_area`**. \
1.4 Dado que el usuario selecciona el campo **Tipo de propiedad (CA6)**, cuando completa el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista desplegable, cargada desde la tabla **`tipo_propiedad`**. \
1.5 Dado que el usuario selecciona el campo **Escala de representación (CA7)**, cuando llena el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista desplegable, cargada desde la tabla **`escala_representacion`**. \
1.6 Dado que el usuario selecciona el campo **Ecosistema (CA8)**, cuando completa la información, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista desplegable, cargada desde la tabla **`ecosistema`**. \
1.7 Dado que el usuario completa el campo **Descripción estado ecosistema (CA9)**, cuando guarda la información, entonces el sistema debe permitir que sea un **campo de texto opcional** con una longitud máxima de **500 caracteres**. \
1.8 Dado que el usuario selecciona el campo **Tipo de tensionantes (CA10)**, cuando llena el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista desplegable, cargada desde la tabla **`tensionantes_restauracion`**. \
1.9 Dado que el usuario selecciona el campo **Modelo de intervención (CA11)**, cuando completa la información, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista desplegable, cargada desde la tabla **`modelo_intervencion`**. \

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-116.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-116.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-116.png)

## ANEXOS

-	[HU-pigcct-sym-115](/content/historias_usuario/HU-pigcct-sym-115/HU-pigcct-sym-115.md)
-  Mapeo de errores de validación a mensajes específicos.