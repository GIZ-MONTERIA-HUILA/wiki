# HU-PIGCCT-SYM-006  
## Épica: Administración de la tabla maestra de PIGCCT  
### Editar información del PIGCCT

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** editar la información administrativa de un PIGCCT registrado.  
> **Para:** corregir, actualizar o ajustar el nombre y/o la descripción del plan, manteniendo la consistencia y trazabilidad de la información.



## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la edición del PIGCCT
1.1 El sistema debe permitir la opción **“Editar PIGCCT”** únicamente a usuarios con rol de **administrador**.  
1.2 La opción de edición debe estar disponible desde:
- El listado de PIGCCT (acción por registro).
- La vista de detalle del PIGCCT.



### 2. Campos editables
2.1 El sistema debe permitir editar únicamente los siguientes campos:
- Denominación (nombre) del PIGCCT.
- Descripción del PIGCCT.

2.2 Los siguientes campos **no deben ser editables**:
- Departamento.
- Año del PIGCCT.
- Identificador único del PIGCCT.



### 3. Validaciones previas al guardado
3.1 El sistema debe validar que los campos editables no estén vacíos.  
3.2 El sistema debe validar la longitud y formato del texto conforme a las reglas definidas.  
3.3 La edición no debe permitir generar conflictos con la regla de unicidad (departamento + año).



### 4. Guardado de cambios
4.1 Al confirmar la edición, el sistema debe actualizar la información en la tabla maestra de PIGCCT.  
4.2 El sistema debe mostrar un mensaje de confirmación indicando que la información fue actualizada correctamente.  
4.3 El sistema debe reflejar los cambios inmediatamente en el listado y en la vista de detalle.



### 5. Auditoría y trazabilidad
5.1 El sistema debe registrar automáticamente:
- Usuario que realizó la modificación.
- Fecha y hora de la edición.
- Valores anteriores y nuevos de los campos modificados.

5.2 La información de auditoría debe conservarse para fines de control y seguimiento institucional.



### 6. Restricciones por estado del PIGCCT
6.1 El sistema debe permitir la edición tanto de PIGCCT activos como inactivos.  
6.2 La edición de información administrativa no debe afectar la información operativa ni histórica asociada al PIGCCT.



### 7. Usabilidad y experiencia de usuario
7.1 El formulario de edición debe ser claro y consistente con el formulario de registro.  
7.2 El sistema debe permitir cancelar la edición sin guardar cambios.  
7.3 El sistema debe prevenir la pérdida de información mediante confirmaciones o advertencias previas al cierre.



### Resultado esperado

El administrador puede **editar correctamente el nombre y/o la descripción de un PIGCCT**, asegurando la actualización de la información administrativa sin afectar la integridad, unicidad ni trazabilidad del plan.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-006.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-006.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-001-011.png)

