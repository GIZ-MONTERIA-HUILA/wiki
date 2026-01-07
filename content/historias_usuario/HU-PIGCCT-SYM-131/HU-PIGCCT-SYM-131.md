## HU-pigcct-sym-131
> **Identificador Historia de Usuario:** HU-pigcct-sym-131 \
> **Nombre Historia de Usuario:** Módulo de restauración - Flujo de Validación por IDEAM (Nivel II)

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** Validador IDEAM. \
> **Quiero:** acceder a un formulario de revisión final que muestre los registros aprobados por la entidad. \
> **Para:** revisar la consistencia técnica y calidad espacial, y aprobar o devolver el registro para correcciones.

## CRITERIOS DE ACEPTACIÓN

1. **Interfaz y Acceso del Revisor Nacional** 1.1. Acceso Restringido: Solo usuarios con el perfil "Validador IDEAM" pueden acceder a la interfaz de revisión nacional. 1.2. El formulario debe listar todos los registros que se encuentren en estado 'UNDER_REVISION_IDEAM'. 1.3. El Validador IDEAM no puede modificar campos del registro, solo revisar y agregar observaciones_ideam. 1.4. Criterios de Consistencia Temática (Validación): El sistema (o el validador) debe verificar:
   - Geometrías válidas y sin topología errónea.
   - Comprobar relaciones con dominios.
   - Revisar adjuntos obligatorios.
2. **Reglas y Transición de Estados (IDEAM)** 2.1. Aprobación Final (Transición Exitosa): Al seleccionar "Aprobado por IDEAM", el campo estado cambia a 'VALIDATED'. Se registran fecha_validacion_ideam y usuario_validador_ideam. 2.2. Devolución a Entidad (Transición de Error): Al seleccionar "Devuelto a Entidad", el campo estado cambia a 'RETURNED_IDEAM'.
3. **Trazabilidad** 3.1. Se genera un registro en el log_eventos del registro con la acción: "Validación IDEAM completada" (usuario, fecha, id_registro, resultado: APROBADO / DEVUELTO). 3.2. Al pasar a estado 'VALIDATED', el registro debe estar disponible para consulta pública y reportes.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-131.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-131.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-131.png)
