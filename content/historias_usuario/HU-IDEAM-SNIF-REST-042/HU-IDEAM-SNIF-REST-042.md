## HU-IDEAM-SNIF-REST-042

> **Identificador Historia de Usuario:** hu-ideam-snif-rest-042 \
> **Nombre Historia de Usuario:** Módulo de restauración - Validaciones topológicas y estructurales

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario solicitante. \
> **Quiero:**  validar la estructura y topología de la capa cargada. \
> **Para:** evitar errores o sobrecargas durante la ejecución de la consulta.

## CRITERIOS DE ACEPTACIÓN

   1. Detectar automáticamente el tipo de geometría antes de procesar.  
   2. Validar topología (geometrías válidas, no autointersectadas). 
   3. Rechazar geometrías vacías o corruptas. 
   4. Controlar la cantidad máxima de vértices por geometría.
   5. Mostrar mensajes de error claros cuando la capa no cumpla los requisitos. 


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-ideam-snif-rest-042.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-ideam-snif-rest-042.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-ideam-snif-rest-042.png)

## ANEXOS

- Ejemplo de consulta espacial mediante API REST.
- Ejemplo de respuesta en formato GeoJSON.
- Referencia a numeral **Consulta por Capa Geográfica** del visor geográfico.
