# HU-PIGCCT-SYM-167  
## Épica: Formulario de Registro y Gestión de Acciones del PIGCCT  
### Registrar valores proyectados

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** registrar los valores proyectados de los indicadores asociados a una acción.  
> **Para:** planificar el cumplimiento de los indicadores del PIGCCT y establecer metas de seguimiento para la ejecución de la acción.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la sección “Programación y seguimiento” / “Valores proyectados”
1.1 El sistema debe permitir el acceso a la vista de **valores proyectados** a usuarios con rol de **registrador** y **administrador**.  
1.2 Esta funcionalidad debe estar disponible dentro del flujo del formulario de registro y gestión de acciones del PIGCCT.  
1.3 El sistema debe mostrar una **tabla generada automáticamente** con los registros de seguimiento asociados a la acción.


### 2. Estructura de la vista en tabla
2.1 El sistema debe mostrar una tabla con las siguientes columnas:

- **Indicador**.  
- **Vigencia**.  
- **Nro. de seguimiento**.  
- **Valor proyectado** (campo editable).  
- **Valor ejecutado** (campo deshabilitado).  
- **Estado**.

2.2 La tabla debe generarse automáticamente con base en:
- La programación definida para la acción.
- La vigencia y forma de evaluación configuradas previamente.
- Los indicadores asociados a la acción.


### 3. Edición de valores proyectados
3.1 El sistema debe permitir editar **únicamente** el campo **Valor proyectado**.  
3.2 Los campos **Valor ejecutado** deben mostrarse siempre en estado **deshabilitado** para el usuario registrador.  
3.3 El sistema debe validar que los valores ingresados en **Valor proyectado**:
- Sean numéricos.
- Cumplan con los formatos y rangos definidos por el sistema.


### 4. Guardado parcial
4.1 El sistema debe permitir el **guardado parcial** de la información:
- El usuario no está obligado a completar todos los valores proyectados en una sola sesión.
- La información registrada debe persistirse correctamente por cada fila editada.

4.2 Al guardar parcialmente:
- Debe mostrarse una confirmación visual de guardado exitoso.
- La información previamente registrada debe mantenerse disponible para edición posterior.


### 5. Indicador visual de completitud
5.1 El sistema debe mostrar un **indicador visual de completitud** por:
- Fila (seguimiento individual).
- Sección (conjunto de valores proyectados).

5.2 El indicador debe permitir identificar:
- Registros completos (con valor proyectado definido).
- Registros pendientes (sin valor proyectado).


### 6. Estado del seguimiento
6.1 El campo **Estado** debe reflejar automáticamente la condición del registro, por ejemplo:
- **Pendiente**: cuando no se ha definido valor proyectado.
- **Proyectado**: cuando existe valor proyectado registrado.
- **Ejecutado** u otro estado definido por el sistema cuando se registren valores ejecutados.

6.2 El usuario no debe poder modificar manualmente el estado desde esta vista.


### 7. Validaciones y control de errores
7.1 El sistema debe validar que:
- Los valores proyectados ingresados sean válidos.
- No se registren valores inconsistentes con la estructura del indicador.

7.2 En caso de error:
- El sistema debe mostrar mensajes claros por fila o campo.
- No debe perderse la información ya ingresada.


### 8. Persistencia e integridad de la información
8.1 El sistema debe almacenar los valores proyectados asociados a:
- La acción.
- El indicador.
- La vigencia.
- El número de seguimiento.

8.2 La información debe quedar disponible para:
- Seguimiento y monitoreo.
- Registro posterior de valores ejecutados.
- Reportes de avance del PIGCCT.


### 9. Usabilidad y experiencia de usuario
9.1 La vista en tabla debe ser clara, ordenada y consistente con el diseño general del sistema.  
9.2 El sistema debe facilitar la edición directa en celdas del campo **Valor proyectado**.  
9.3 El sistema debe prevenir la pérdida de información mediante guardado parcial y mensajes de confirmación.

---

### Resultado esperado

El usuario puede **registrar y gestionar los valores proyectados de los indicadores asociados a una acción**, mediante una tabla generada automáticamente, con edición controlada, guardado parcial e indicadores visuales de completitud, permitiendo una planificación clara del cumplimiento de metas del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-167.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-167.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-167.png)
