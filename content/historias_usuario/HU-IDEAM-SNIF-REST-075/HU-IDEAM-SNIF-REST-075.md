## HU-pigcct-sym-075

> **Identificador Historia de Usuario:** hu-pigcct-sym-075 \
> **Nombre Historia de Usuario:** Módulo de restauración - Desactivación Dinámica de Campos y Autocompletado

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  \
> **Quiero:**  que los campos solo se activen cuando sean pertinentes y que el sistema me ayude a llenar datos predecibles.  \
> **Para:** evitar errores de entrada en campos inoportunos y agilizar el llenado de formularios.

## CRITERIOS DE ACEPTACIÓN

1.	**Desactivación Dinámica**  
    1.1. Los campos dependientes deben estar desactivados o en modo readonly hasta que se cumplan las condiciones previas (Ej: seleccionar un valor en un dropdown maestro).    
    1.2. Los campos no editables (que son solo de visualización de datos), deben mostrarse en estado disabled o readonly con un estilo visual que indique claramente su inactividad.

2.	**Control de Autocompletado**   
    2.1. Se debe activar la función de autocompletado (autocomplete) solo en campos pertinentes donde la sugerencia del navegador mejore la usabilidad (Ej: nombre, dirección).     
    2.2. En campos de contraseñas o datos altamente sensibles, el autocomplete debe estar explícitamente deshabilitado para cumplir con la seguridad (Ver *AUTENTICACION*).



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-075.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-075.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-075.png)

## ANEXOS

- Política de seguridad sobre el uso de autocompletado en campos sensibles.

