## HU-IDEAM-SNIF-REST-132
> **Identificador Historia de Usuario:** HU-IDEAM-SNIF-REST-132 \
> **Nombre Historia de Usuario:** Módulo de restauración - Ciclo de Correcciones y Reenvío de Registros

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario creador o revisor institucional. \
> **Quiero:** recibir notificaciones y tener la capacidad de editar los registros devueltos. \
> **Para:** corregir los hallazgos y reintroducir el registro al flujo de validación.

## CRITERIOS DE ACEPTACIÓN

1. **Acciones del Ciclo de Corrección** 1.1. Habilitación de Edición: Si el registro tiene estado 'RETURNED' o 'RETURNED_IDEAM', los campos del registro deben habilitarse para la edición por parte del usuario creador (o el Validador Entidad, según corresponda). 1.2. Visualización de Hallazgos: El formulario de edición debe mostrar claramente las observaciones_entidad o observaciones_ideam (según el estado) para que el usuario sepa qué corregir. 1.3. Documentación de Correcciones: El usuario debe poder documentar las correcciones realizadas en un campo de historial (o en log_eventos).
2. **Reenvío y Transición de Estados** 2.1. Reenvío (RETURNED): Si el registro fue devuelto por la Entidad ('RETURNED'), al ser editado y guardado nuevamente, debe regresar automáticamente a estado 'UNDER_REVISION'. 2.2. Reenvío (RETURNED_IDEAM): Si el registro fue devuelto por el IDEAM ('RETURNED_IDEAM'), al ser editado y guardado por la entidad, debe regresar automáticamente a estado 'UNDER_REVISION_IDEAM'. 2.3. Trazabilidad: Se registra un log con la acción: "REENVÍO DE REGISTRO" (usuario, fecha, id_registro, estado final).


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-IDEAM-SNIF-REST-132.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-IDEAM-SNIF-REST-132.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-ideam-snif-rest-132.png)
