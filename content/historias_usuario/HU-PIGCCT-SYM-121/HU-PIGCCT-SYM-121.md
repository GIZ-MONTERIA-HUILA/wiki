## HU-pigcct-sym-121

> **Identificador Historia de Usuario:** hu-pigcct-sym-121 \
> **Nombre Historia de Usuario:** Módulo de restauración - Política de Edición y Actualización de Registros Temáticos.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario con rol de edición.   \
> **Quiero:** modificar los datos de cualquier elemento funcional principal (proyecto, área, indicador) del sistema.    \
> **Para:** mantener actualizada la definición y el estado de la información, cumpliendo con las políticas de trazabilidad y consistencia.

## CRITERIOS DE ACEPTACIÓN

1.	**Restricción de Acceso y Datos**   
    1.1. La función de edición debe ser accesible solo para usuarios con el rol adecuado (Ver [HU-077](../HU-pigcct-sym-077/HU-pigcct-sym-077.md)).   
    1.2. **Restricción de Edición Específica**: Solo se permite editar indicadores cuyo estado sea activo = *true*. Los indicadores inactivos no son editables.
2.	**Carga y Validación del Formulario**   
    2.1. Al abrir la edición, el formulario debe llenarse con los datos actuales del registro (pre-llenado).    
    2.2. **Consistencia de Validación**: Todas las mismas validaciones que aplican en la creación (Ej: obligatoriedad, longitud, formato, unicidad, lógica condicional) deben aplicar también en la edición (Ver [HU-096](../HU-pigcct-sym-096/HU-pigcct-sym-096.md), [HU-097](../HU-pigcct-sym-097/HU-pigcct-sym-097.md), etc.).

3.	**Flujo de Guardado y Persistencia**    
    3.1. Al presionar Guardar, si todas las validaciones son exitosas, el sistema actualiza el registro en la base de datos.    
    3.2. Si ocurre un error, se muestran los mensajes correspondientes (Ver [HU-071](../HU-pigcct-sym-071/HU-pigcct-sym-071.md)).

4.	**Registro de Logs (Trazabilidad)**     
    4.1. Toda edición exitosa debe generar una entrada en el log (Ver [HU-083](../HU-pigcct-sym-083/HU-pigcct-sym-083.md)) con la acción *UPDATE_TEMA*.   
    4.2. El registro del log debe incluir el detalle del cambio: el valor anterior y el valor nuevo para los campos modificados, garantizando la trazabilidad histórica de los datos.







## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-121.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-121.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-121.png)

## ANEXOS

- Protocolo de comparación de datos para el registro de *valor anterior / valor nuevo* en el log.

