## HU-pigcct-sym-085

> **Identificador Historia de Usuario:** hu-pigcct-sym-085 \
> **Nombre Historia de Usuario:** Módulo de restauración - Política de almacenamiento unificado de archivos

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema. \
> **Quiero:**  unificar el almacenamiento de todos los archivos (documentales y geográficos) en una única estructura relacional.   \
> **Para:** simplificar la administración de la base de datos, centralizar la trazabilidad y estandarizar la gestión de archivos en todo el módulo.

## CRITERIOS DE ACEPTACIÓN


1. **Estructura Unificada**  
   1.1 El sistema debe almacenar el registro de todos los archivos subidos (generales/documentales y geográficos) en una única tabla relacional (tabla adjunto).     
   1.2. La misma estructura debe servir para adjuntos documentales y geográficos.

2. **Trazabilidad y Relación**  
   2.1 La tabla de archivos debe contener campos (tabla_referida y id_elemento_referido) que garanticen la trazabilidad completa hacia el elemento principal al que está adjunto.

3. **Gestión consistente**  
   3.1 Las políticas de registro de eventos (Log) y eliminación de datos deben aplicarse de manera uniforme a todos los tipos de archivos (Ver [HU-pigcct-sym-087](/content/historias_usuario/HU-pigcct-sym-087/HU-pigcct-sym-087.md)).   
   3.2. La eliminación de archivos debe ser lógica para preservar el historial. 

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-085.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-085.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-085.png)

## ANEXOS

- Diagrama Entidad-Relación (DER) preliminar para la tabla de adjuntos.
