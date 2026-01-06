## HU-pigcct-sym-122

> **Identificador Historia de Usuario:** hu-pigcct-sym-122 \
> **Nombre Historia de Usuario:** Módulo de restauración - Política de Desactivación Lógica y Control de Dependencias.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador de datos.    \
> **Quiero:** desactivar registros temáticos que ya no son relevantes (proyectos, indicadores, etc.) en lugar de eliminarlos permanentemente.    \
> **Para:** mantener la trazabilidad histórica de los datos y asegurar que la eliminación física no rompa la integridad referencial.

## CRITERIOS DE ACEPTACIÓN


1.	**Método de Eliminación Lógica**    
    1.1. La eliminación de registros temáticos debe ser siempre lógica. Esto se logra actualizando el campo de estado a activo = *false*.   
    1.2. El registro físico del dato debe conservarse en la base de datos.

2.	**Control de Integridad Referencial**   
    2.1. **Restricción de Eliminación Física**: Cuando existan elementos relacionales dependientes (Ej: Si un proyecto tiene áreas asociadas), el sistema no debe permitir la eliminación física del registro.  
    2.2. En casos de dependencias, la única opción permitida es la desactivación lógica.
3.	**Experiencia de Usuario (Modal de Confirmación)**
    3.1. Antes de realizar la desactivación, el sistema debe mostrar una modal de confirmación (Ver [HU-070](../HU-pigcct-sym-070/HU-pigcct-sym-070.md)) con el siguiente texto: > *“¿Desea inactivar este dato? Se perderá la posibilidad de medirlo en nuevas observaciones, pero los datos históricos se conservan.”*

4.	**Registro de Logs**    
    4.1. Toda desactivación (cambio de activo = *true* a activo = *false)* debe registrarse como un evento en los logs del sistema (Ver [HU-083](../HU-pigcct-sym-083/HU-pigcct-sym-083.md)) con la acción *DEACTIVATE* o *DELETE_LOGIC*.







## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-122.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-122.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-122.png)

## ANEXOS

- *Query* de verificación de integridad referencial antes de la desactivación lógica.

