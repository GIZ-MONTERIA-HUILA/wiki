# HU-PIGGCT-SYM-001  
## Épica: Administración de la tabla maestra de PIGCCT  
### Necesidad: Registrar PIGCCT

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** registrar un nuevo Plan Integral de Gestión del Cambio Climático Territorial (PIGCCT) en la tabla maestra del sistema.  
> **Para:** almacenar, administrar y gestionar la información base del plan asociado a un departamento de Colombia, garantizando su unicidad y disponibilidad para la estructuración, seguimiento y monitoreo del PIGCCT.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de registro
1.1 El sistema debe permitir el acceso a la opción **“Registrar PIGCCT”** únicamente a usuarios con rol de **administrador del sistema**.  
1.2 La opción debe estar disponible desde el módulo de **Administración** o **Configuración general** del sistema.  
1.3 Al seleccionar la opción, el sistema debe mostrar un formulario de registro del PIGCCT.


### 2. Formulario de registro del PIGCCT
2.1 El formulario debe permitir ingresar como mínimo los siguientes campos obligatorios:
- Departamento (seleccionado desde un catálogo oficial de departamentos de Colombia).
- Año de formulación del PIGCCT.
- Denominación oficial del plan.
- Estado del plan (Activo / Inactivo).
- Descripción general (opcional).

2.2 El sistema debe validar que todos los campos obligatorios estén diligenciados antes de permitir el registro.  
2.3 Los catálogos (departamento y estado) deben cargarse automáticamente desde tablas maestras del sistema.

### 3. Validación de unicidad
3.1 El sistema debe validar que **no exista previamente un PIGCCT registrado para el mismo departamento y el mismo año**.  
3.2 Si ya existe un registro con la misma combinación departamento–año, el sistema debe:
- Bloquear el guardado del registro.
- Mostrar un mensaje claro indicando que el PIGCCT ya se encuentra registrado.

### 4. Registro y almacenamiento de la información
4.1 Al confirmar el registro, el sistema debe almacenar la información en la **tabla maestra de PIGCCT**.  
4.2 El sistema debe asignar automáticamente un identificador único al nuevo PIGCCT.  
4.3 El registro debe quedar disponible para ser utilizado en los módulos de:
- Estructuración del PIGCCT (ejes, medidas, indicadores).
- Registro de acciones.
- Seguimiento, monitoreo y evaluación.

### 5. Gestión de estados
5.1 El sistema debe permitir definir el estado inicial del PIGCCT (Activo o Inactivo).  
5.2 Solo los PIGCCT en estado **Activo** deben estar disponibles para la creación y gestión de información asociada.  
5.3 Los PIGCCT en estado **Inactivo** deben conservar su información histórica, pero no permitir nuevas asociaciones operativas.

### 6. Mensajes y retroalimentación al usuario
6.1 Al registrar exitosamente el PIGCCT, el sistema debe mostrar un mensaje de confirmación.  
6.2 En caso de error de validación o falla en el proceso, el sistema debe informar claramente la causa y permitir la corrección de los datos.

### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar automáticamente:
- Usuario creador.
- Fecha y hora de creación.
- Estado inicial del registro.

7.2 Esta información debe ser utilizada para fines de auditoría y control institucional.

### 8. Usabilidad y experiencia de usuario
8.1 El formulario debe ser claro, guiado y consistente con el diseño general del sistema.  
8.2 El sistema debe permitir cancelar el registro sin guardar cambios.  
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas al cierre del formulario.

### Resultado esperado

Un **PIGCCT registrado correctamente** en la tabla maestra del sistema, asociado a un departamento y año específicos, listo para ser estructurado, monitoreado y utilizado como base para la gestión integral del cambio climático territorial.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-001.png)



## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-001.png)



## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-001.png)

