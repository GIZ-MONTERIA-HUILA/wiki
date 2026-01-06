## HU-pigcct-sym-073

> **Identificador Historia de Usuario:** hu-pigcct-sym-073 \
> **Nombre Historia de Usuario:** Módulo de restauración - Etiquetas, Placeholders y Mensajes de Error Contextuales.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  \
> **Quiero:**  ver etiquetas claras, texto guía en los campos y mensajes de error ubicados cerca del campo inválido.  \
> **Para:** saber exactamente qué dato se me solicita y dónde debo corregir un error.

## CRITERIOS DE ACEPTACIÓN

1.	**Etiquetas y Placeholders**    
    1.1. Cada campo de entrada (texto, numérico, fecha) debe tener una etiqueta visible que describa su propósito.  
    1.2. Cada campo debe mostrar un placeholder o texto guía representativo del dato solicitado (Ej: "Juan Pérez" o "DD/MM/AAAA").  
    1.3. Las etiquetas deben ser concisas y claras.

2.	**Mensajes de Error Contextuales**  
    2.1. Al fallar una validación, el sistema debe mostrar el mensaje de error (Ver REGISTROS DEL SISTEMA) directamente debajo del campo inválido.  
    2.2. El mensaje de error debe desaparecer automáticamente en cuanto el usuario comience a corregir o corrija el error.  
    2.3. El campo inválido debe tener un indicador visual claro (Ej: borde rojo).





## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-073.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-073.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-073.png)

## ANEXOS

- Estándar de formato para etiquetas y placeholders.

