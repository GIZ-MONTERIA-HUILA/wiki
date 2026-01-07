## HU-pigcct-sym-129
> **Identificador Historia de Usuario:** HU-pigcct-sym-129 \
> **Nombre Historia de Usuario:** Módulo de restauración - Módulo de Validación de Registros (Doble Nivel)

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema. \
> **Quiero:** implementar un módulo de validación jerárquica de doble nivel (Entidad e IDEAM) para todos los registros operativos del sistema. \
> **Para:** garantizar la calidad, consistencia y trazabilidad de los datos, y que solo la información aprobada se publique para consulta y reportes.

## CRITERIOS DE ACEPTACIÓN

1. **Estructura y Estados del Flujo** 1.1. Alcance Transversal: El módulo aplica a todas las tablas operativas (Ej: proyecto, area_restaurada, indicador_monitoreo, etc.). 1.2. Niveles de Validación: El flujo contempla dos niveles obligatorios: Validación de Entidad y Validación IDEAM. 1.3. Estado Inicial: Todo registro inicia con el estado: 'UNDER_REVISION' (Ver HU-128). 1.4. Estado Final (Publicación): Solo tras la aprobación en ambos niveles, el registro cambia a estado 'VALIDATED'.
2. **Trazabilidad del Proceso (Campos Físicos)** 2.1. Todas las tablas afectadas deben incluir los siguientes campos para la trazabilidad:
   - estado (Control del flujo: UNDER_REVISION, UNDER_REVISION_IDEAM, RETURNED, VALIDATED, RETURNED_IDEAM).
   - fecha_creacion / entidad_creadora / usuario_creador.
   - fecha_validacion_entidad y usuario_validador_entidad.
   - observaciones_entidad (Comentarios o hallazgos del revisor).
   - fecha_validacion_ideam y usuario_validador_ideam.
   - observaciones_ideam (Observaciones técnicas).


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-129.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-129.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-129.png)
