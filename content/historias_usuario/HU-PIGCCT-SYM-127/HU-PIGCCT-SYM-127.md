## HU-pigcct-sym-127

> **Identificador Historia de Usuario:** hu-pigcct-sym-127 \
> **Nombre Historia de Usuario:** Módulo de restauración - Configuración y gestión de dependencia jerárquica 

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** ausuario final.  \
> **Quiero:** que al seleccionar un valor en una lista desplegable (ej. Departamento), la lista siguiente (ej. Municipio) se filtre automáticamente.  \
> **Para:** facilitar la selección, reducir la posibilidad de error y evitar la carga innecesaria de miles de valores no relacionados.

## CRITERIOS DE ACEPTACIÓN

1. **Configuración de Dependencia**  
   1.1 El sistema debe permitir configurar relaciones jerárquicas entre dominios (Ej: A depende de B).    
   1.2. El sistema debe tener mecanismos de validación para evitar errores de dependencia circular.

2. **Comportamiento en Cascada (Front-End)**  
   2.1 Al seleccionar un valor en la lista padre, la lista dependiente debe actualizarse automáticamente consultando solo los valores relacionados.    
   2.2. Si el valor padre cambia, la lista dependiente debe limpiarse y recargarse.     
   2.3. UX: Se debe mostrar un mensaje de carga (“Cargando…”) o el mensaje “Seleccione primero el valor superior” si se intenta interactuar con una lista dependiente vacía.

3. **Validación de Relación**  
   3.1. En el backend, se debe validar que el valor final seleccionado en la lista dependiente pertenezca realmente al dominio relacionado y al valor padre seleccionado (Ej: el Municipio seleccionado pertenece al Departamento seleccionado).

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-127.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-127.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-127.png)

## ANEXOS

- Especificación de la API de consulta con parámetro de filtro para dependencia.
