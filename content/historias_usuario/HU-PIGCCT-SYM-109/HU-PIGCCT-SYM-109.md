## HU-pigcct-sym-109

> **Identificador Historia de Usuario:** hu-pigcct-sym-109 \
> **Nombre Historia de Usuario:** Módulo de restauración - Creación de Indicador de Monitoreo (Campos Generales).

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** agregar indicadores de monitoreo asociados a un proyecto guardado.   \
> **Para:** documentar la estrategia de seguimiento y medición de progreso.

## CRITERIOS DE ACEPTACIÓN

1. **Creación de Indicador (Generales)**  
   1.1 Dado que el usuario accede al formulario de gestión de proyectos, cuando el proyecto ya existe y posee un **`id_proyecto`** válido, entonces el sistema debe habilitar la pestaña **“Indicadores de monitoreo”**. \
   1.2 Dado que el usuario visualiza la pestaña “Indicadores de monitoreo”, cuando crea o edita un registro, entonces el sistema debe mostrar los siguientes **campos obligatorios**: `nombre_indicador`, `tipo_indicador`, `frecuencia_medicion`, `metodo_calculo`, y `responsable`. \
   1.3 Dado que el usuario ingresa el campo **nombre_indicador**, cuando intenta guardar la información, entonces el sistema debe validar que el valor sea **obligatorio**, tenga entre **5 y 200 caracteres**, y no contenga únicamente espacios. \
   1.4 Dado que el usuario selecciona el campo **tipo_indicador**, cuando completa el formulario, entonces el sistema debe exigir una opción obligatoria de tipo **enum**, con los valores posibles: `CUANTITATIVO` o `CUALITATIVO`. \
   1.5 Dado que el usuario selecciona el campo **frecuencia_medicion**, cuando llena el formulario, entonces el sistema debe exigir una opción obligatoria de tipo **enum**, con los valores posibles: `MENSUAL`, `TRIMESTRAL`, `SEMESTRAL`, o `ANUAL`. \
   1.6 Dado que el usuario completa el campo **metodo_calculo**, cuando guarda la información, entonces el sistema debe validar que el campo tipo **textarea** sea **obligatorio** y contenga información antes de aceptar el registro. \
   1.7 Dado que el usuario completa el campo **responsable**, cuando guarda el formulario, entonces el sistema debe validar que el valor corresponda a un **usuario válido en el directorio del sistema**, o un texto libre con un mínimo de **3 caracteres**, y debe ser **obligatorio** en todos los casos. \
   1.8 Dado que el usuario crea o actualiza un indicador, cuando intenta guardar uno con el mismo **nombre_indicador** existente en el mismo proyecto, entonces el sistema debe **impedir duplicados exactos**, mostrando una advertencia que solicite **confirmación explícita** antes de permitir el guardado. \

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-109.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-109.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-109.png)

## ANEXOS

-	[HU-pigcct-sym-101](/content/historias_usuario/HU-pigcct-sym-101/HU-pigcct-sym-101.md)
-  Mapeo de errores de validación a mensajes específicos.