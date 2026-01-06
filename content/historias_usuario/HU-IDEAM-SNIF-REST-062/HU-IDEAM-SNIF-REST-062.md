## HU-pigcct-sym-062
> **Identificador Historia de Usuario:** HU-pigcct-sym-062 \
> **Nombre Historia de Usuario:** Módulo de restauración - Validación de Campos de Texto (Longitud y Caracteres)

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** que los campos de texto alfanumérico validen la longitud, obligatoriedad y el tipo de caracteres ingresados. \
> **Para:** asegurar la calidad y consistencia de los datos textuales ingresados.

## CRITERIOS DE ACEPTACIÓN

1. **Validación de Obligatoriedad y Vacío** 1.1. Si el campo es requerido (obligatorio), no se debe permitir que quede vacío.
2. **Validación de Longitud** 2.1. El sistema debe validar la longitud máxima de caracteres permitida para el campo. 2.2. Si la entrada excede la longitud permitida, se debe mostrar el mensaje: "Máximo X caracteres". 2.3. Se debe validar también la longitud mínima si está configurada.
3. **Validación de Caracteres Especiales** 3.1. El sistema debe evitar caracteres especiales si el campo no los admite. 3.2. Si contiene caracteres inválidos, se debe mostrar el mensaje: "Carácter no permitido".
4. **Referencia a la Política General ([HU-061](../HU-pigcct-sym-061/HU-pigcct-sym-061.md))** 4.1. Esta validación debe cumplir con los principios de mensajería amigable y validación en tiempo real.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-pigcct-sym-062.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-pigcct-sym-062.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-062.png)
