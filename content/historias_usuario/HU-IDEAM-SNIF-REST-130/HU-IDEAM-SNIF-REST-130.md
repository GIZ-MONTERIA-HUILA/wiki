## HU-pigcct-sym-130
> **Identificador Historia de Usuario:** HU-pigcct-sym-130 \
> **Nombre Historia de Usuario:** Módulo de restauración - Flujo de Validación por Entidad (Nivel I)

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** Validador Entidad. \
> **Quiero:** acceder a un formulario que liste los registros de mi entidad en estado de revisión y poder aprobarlos o devolverlos con observaciones. \
> **Para:** realizar la validación interna de calidad y pasar el registro a la revisión del IDEAM.

## CRITERIOS DE ACEPTACIÓN

1. **Interfaz y Acceso del Revisor Institucional** 1.1. Acceso Restringido: Solo usuarios con el perfil "Validador Entidad" pueden acceder al formulario de validación interna. 1.2. El formulario debe listar todos los registros pertenecientes a su propia entidad que se encuentren en estado 'UNDER_REVISION'. 1.3. El revisor debe poder revisar información general (metadatos, geometría, adjuntos, dominios asociados) desde la interfaz de validación. 1.4. El validador no puede modificar los campos del registro, solo realizar acciones de flujo y añadir observaciones.
2. **Reglas y Transición de Estados (Entidad)** 2.1. Regla de Aprobación: No se puede aprobar un registro con campos obligatorios vacíos o datos inconsistentes (Validación de completitud). 2.2. Aprobación (Transición Exitosa): Al seleccionar la acción "Aprobado por Entidad", el campo estado debe cambiar automáticamente a 'UNDER_REVISION_IDEAM' y se registran fecha_validacion_entidad y usuario_validador_entidad. 2.3. Devolución (Transición de Error): Al seleccionar la acción "Devuelto al usuario", el campo estado debe cambiar a 'RETURNED'. 2.4. Registro de Observaciones: Las observaciones deben ser obligatorias si el registro se devuelve a estado 'RETURNED'.
3. **Trazabilidad** 3.1. Se genera un registro en el log_eventos del registro con la acción: "Validación Entidad" (usuario, fecha, id_registro, resultado: APROBADO / DEVUELTO).


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-pigcct-sym-130.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-pigcct-sym-130.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-130.png)
