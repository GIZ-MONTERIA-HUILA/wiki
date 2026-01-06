## HU-pigcct-sym-055
> **Identificador Historia de Usuario:** HU-pigcct-sym-055 \
> **Nombre Historia de Usuario:** Módulo de restauración - Lista Desplegable (Dropdown)

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario solicitante. \
> **Quiero:** seleccionar opciones desde listas desplegables controladas. \
> **Para:** garantizar la coherencia, estandarización y la selección de un valor dentro de un conjunto de opciones predefinidas y válidas.

## CRITERIOS DE ACEPTACIÓN

1. **Gestión de Opciones y Carga** 1.1. El sistema debe permitir seleccionar un valor dentro de un conjunto de opciones predefinidas. 1.2. Las opciones deben **cargarse dinámicamente** desde catálogos del sistema o una API. 1.3. Para listas con **más de 10 elementos**, el control debe permitir **búsqueda interna** o autocompletar. 1.4. Debe mostrar el texto **"Seleccione una opción"** por defecto.
2. **Dependencias y Validación** 2.1. El sistema debe validar la **selección obligatoria** si el campo es requerido. 2.2. Si la lista desplegable depende de la selección de otro campo (Ej: municipio → departamento), debe **actualizarse automáticamente** y recargar las opciones.
3. **Uso Típico en el Módulo** 3.1. Usos típicos: selección de **unidades espaciales de referencia, variables temáticas o categorías consolidadas**.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-pigcct-sym-055.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-pigcct-sym-055.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-001.png)
