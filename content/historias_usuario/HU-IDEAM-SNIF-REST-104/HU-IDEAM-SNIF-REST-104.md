## HU-pigcct-sym-104

> **Identificador Historia de Usuario:** hu-pigcct-sym-104 \
> **Nombre Historia de Usuario:** Módulo de restauración - Validaciones Geométricas y Topológicas.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** realizar validaciones geométricas y topológicas exhaustivas al archivo cargado.   \
> **Para:** asegurar la integridad espacial de los datos antes de su almacenamiento.

## CRITERIOS DE ACEPTACIÓN

1. **Validaciones Geométricas**  
   1.1 El sistema debe validar que la geometría sea de tipo Polígono o MultiPolígono. Si contiene Puntos o Líneas, se debe rechazar automáticamente. \
   1.2 Se debe validar que el archivo contenga al menos un polígono con un Área mínima de 0.01 hectareas. \
   1.3 El sistema debe validar que no existan polígonos autointersectados o con errores topológicos y que las coordenadas sean válidas (no nulas ni fuera del país). \
   1.4 El sistema debe validar que no existan polígonos idénticos (misma geometría y atributos) ya registrados para el mismo proyecto. \
   1.5 Si la validación falla, se debe mostrar un mensaje detallado: “El archivo cargado no cumple las siguientes X condiciones. Verifique que sea un polígono o multipolígono válido.”


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-104.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-104.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-104.png)

## ANEXOS

-	[HU-pigcct-sym-101](/content/historias_usuario/HU-pigcct-sym-101/HU-pigcct-sym-101.md)
-  Mapeo de errores de validación a mensajes específicos.