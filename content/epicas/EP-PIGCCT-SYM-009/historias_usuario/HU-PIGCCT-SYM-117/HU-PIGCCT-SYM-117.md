## HU-pigcct-sym-117

> **Identificador Historia de Usuario:** hu-pigcct-sym-117 \
> **Nombre Historia de Usuario:** Módulo de restauración - Edición de Atributos Sociales y de Participación.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** documentar los indicadores de participación comunitaria, etnia y escolaridad asociados al proyecto.   \
> **Para:** cumplir con los requisitos de la dimensión social y de inclusión.

## CRITERIOS DE ACEPTACIÓN
1. **Edición de atributos Sociales y Participación**  
1.1 Dado que el usuario completa el campo **Participantes totales (CA12)**, cuando intenta guardar la información, entonces el sistema debe validar que sea un **campo numérico entero obligatorio**, con un valor **mayor que 0 ( > 0 )**. \
1.2 Dado que el usuario completa el campo **Mujeres participantes (CA13)**, cuando guarda la información, entonces el sistema debe validar que sea un **campo numérico entero obligatorio**, cuyo valor sea **menor o igual ( ≤ ) al número de participantes totales**. \
1.3 Dado que el usuario selecciona el campo **Edad promedio (CA14)**, cuando completa el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo **enum**, con los valores posibles: `18-25`, `26-40`, `41-60`, y `>60`. \
1.4 Dado que el usuario selecciona el campo **Nivel de escolaridad (CA15)**, cuando completa el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo **enum**, con los valores posibles: `Básica`, `Media`, `Técnica`, y `Superior`. \
1.5 Dado que el usuario selecciona el campo **Pertenece a etnia (CA16)**, cuando llena el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo **enum**, con los valores posibles: `Sí` o `No`. \
1.6 Dado que el usuario selecciona el valor **Sí** en el campo *Pertenece a etnia (CA16)*, cuando el sistema detecta esta condición, entonces debe **habilitar el campo “Etnia específica (CA17)”**, que se muestra como una lista desplegable para seleccionar el tipo de etnia, siendo **obligatorio si aplica**. \
1.7 Dado que el usuario completa el campo **Procesos de divulgación (CA18)**, cuando guarda el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista con valores posibles: `Sí` o `No`. \
1.8 Dado que el usuario completa el campo **Capacitación viveros (CA19)**, cuando selecciona la opción **Sí**, entonces el sistema debe **habilitar el campo “descripcion_capacitacion”**, tipo **textarea**, para registrar detalles sobre la capacitación. Ambos campos son **obligatorios si aplica**. \
1.9 Dado que el usuario completa el campo **Participación en formulación (CA20)**, cuando selecciona la opción **Sí**, entonces el sistema debe **habilitar el campo “forma_participacion_formulacion”**, tipo **textarea**, para describir la forma de participación. \
1.10 Dado que el usuario completa el campo **Participación en establecimiento (CA21)**, cuando selecciona la opción **Sí**, entonces el sistema debe **habilitar el campo “forma_participacion_establecimiento”**, tipo **textarea**, para registrar la información correspondiente. \
1.11 Dado que el usuario completa el campo **Participación en mantenimiento (CA22)**, cuando selecciona la opción **Sí**, entonces el sistema debe **habilitar el campo “forma_participacion_mantenimiento”**, tipo **textarea**, para describir la participación durante la etapa de mantenimiento. \
1.12 Dado que el usuario selecciona el campo **Pagos por servicios (CA23)**, cuando llena el formulario, entonces el sistema debe exigir que sea un **campo obligatorio** de tipo lista desplegable, cargada desde la tabla **`pagos_servicios_restauracion`**. \

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-117.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-117.png)


## ANEXOS

-	[HU-pigcct-sym-115](/content/historias_usuario/HU-pigcct-sym-115/HU-pigcct-sym-115.md)
-  Mapeo de errores de validación a mensajes específicos.