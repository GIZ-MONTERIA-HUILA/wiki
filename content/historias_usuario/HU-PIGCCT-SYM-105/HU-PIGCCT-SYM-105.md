## HU-pigcct-sym-105

> **Identificador Historia de Usuario:** hu-pigcct-sym-105 \
> **Nombre Historia de Usuario:** Módulo de restauración - Procesamiento Post-Carga y Gestión.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema. \
> **Quiero:** visualizar, modificar (reemplazar) o inactivar las áreas de restauración cargadas.   \
> **Para:** mantener la información actualizada y corregir errores.

## CRITERIOS DE ACEPTACIÓN

1. **Post-Proceso y Gestión**  
   1.1 Si la proyección de la información cargada es diferente a EPSG:9377 o EPSG:4326, se debe mostrar una advertencia: “Advertencia: el sistema reproyectará automáticamente al EPSG:9377.” \
   1.2 Cada proyecto debe contar con una pestaña adicional con las áreas de restauración asociadas, y se deben mostrar botones con las acciones (Ver / Editar / Eliminar). \
   1.3 Al hacer clic en el botón “Ver”, el mapa debe hacer acercamiento al polígono y mostrar su ficha atributiva. \
   1.4 Al hacer clic en el botón “Editar” se debe permitir reemplazar el archivo cargado lo que sígnifica cargar una nueva geometría o ajustar metadatos. \
   1.5 Al hacer clic en "Eliminar" el sistema debe mostrar una ventana modal de confirmación solicitando la validación del usuario antes de continuar. \
   1.6 Dado que el área seleccionada está referenciada o utilizada por otros módulos del sistema, cuando el usuario confirma la eliminación, entonces el sistema no debe eliminar físicamente el registro, y debe mostrar un mensaje informativo indicando que la acción no es posible por dependencia de datos. \
   1.7 Dado que el área no tiene dependencias en otros módulos, cuando el usuario confirma la eliminación, entonces el sistema debe inactivar el registro (estableciendo el atributo activo = false) y retirarlo de la vista principal, conservando su trazabilidad histórica. \
   1.8 Al eliminar/inactivar, el sistema debe mostrar el siguiente mensaje: “Área inactivada correctamente.”. \
   1.9 Dado que un usuario realiza una acción sobre el formulario de gestión de áreas de restauración, cuando ejecuta una operación de carga, edición o eliminación, entonces el sistema debe registrar automáticamente un log en la tabla log_sistema con la siguiente información: \
    usuario: identificador del usuario autenticado que realiza la acción \
    acción: tipo de operación realizada (carga, edición o eliminación) \
    tabla: nombre de la tabla afectada \
    id_proyecto: identificador del proyecto asociado \
    id_area_restaurada: identificador del área afectada \
    timestamp: fecha y hora exacta del evento.  \
   1.10 Dado que el registro debe servir para trazabilidad, cuando se almacena en log_sistema, entonces debe quedar disponible para futuras consultas o auditorías del sistema sin posibilidad de modificación manual.



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-105.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-105.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-105.png)

## ANEXOS

-	[HU-pigcct-sym-101](/content/historias_usuario/HU-pigcct-sym-101/HU-pigcct-sym-101.md)
-  Mapeo de errores de validación a mensajes específicos.