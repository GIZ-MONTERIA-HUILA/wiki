## HU-pigcct-sym-087

> **Identificador Historia de Usuario:** hu-pigcct-sym-087 \
> **Nombre Historia de Usuario:** Módulo de restauración - Registro de eventos para carga y gestión de archivos

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema. \
> **Quiero:**  que todos los eventos de gestión de archivos (carga, reemplazo y eliminación) queden registrados en el log de auditoría.  \
> **Para:** asegurar la trazabilidad de la gestión de la documentación y los archivos geográfico.

## CRITERIOS DE ACEPTACIÓN

1. **Integración con el Log de Auditoría (HU-083)**  
   1.1 Los eventos de carga, reemplazo o eliminación lógica se deben registrar en el log de auditoría del sistema (Ver [HU-pigcct-sym-083](/content/historias_usuario/HU-pigcct-sym-083/HU-pigcct-sym-083.md)).   
   1.2 El registro en el log debe cumplir con el Formato de Log estándar definido en la [HU-pigcct-sym-083](/content/historias_usuario/HU-pigcct-sym-083/HU-pigcct-sym-083.md).

2. **Detalle Específico del Registro**  
   2.1 El log debe incluir información específica que relacione el evento con el archivo, tales como: tipo de archivo (GENERAL o GEOGRÁFICO), ID del archivo (PK de la tabla adjuntos) y tabla referida. 

3. **Detalle Específico del Registro**  
   3.1 Se debe registrar explícitamente cuando: un archivo se sube (Carga), un archivo se marca con estado 'INACTIVO' (Eliminación lógica) y cuando se sube una nueva versión de un archivo existente. 

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-087.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-087.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-087.png)

## ANEXOS

- Plantilla de mensaje de log para el evento de "Gestión de Archivo".
