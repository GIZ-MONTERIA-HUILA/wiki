# HU-PIGCCT-SYM-018  
## Épica: Administración de ejes del PIGCCT  
### Editar información del eje

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** modificar el nombre o la descripción de un eje del PIGCCT.  
> **Para:** ajustar o corregir su definición sin afectar la estructura general del plan ni su trazabilidad.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Permisos de edición
1.1 El sistema debe permitir la edición de ejes **únicamente** a usuarios con rol de **administrador**.  
1.2 Los usuarios con rol de consulta deben tener acceso solo en modo lectura.



### 2. Acceso a la edición
2.1 El sistema debe permitir acceder a la opción **Editar eje** desde:
- La vista de detalle del eje.
- El listado de ejes asociados a un PIGCCT.

2.2 La opción de edición debe estar claramente identificada y protegida por permisos.



### 3. Campos editables
3.1 El sistema debe permitir modificar exclusivamente los siguientes campos:
- Nombre del eje.
- Descripción del eje.

3.2 El alcance del eje (estratégico / transversal) y el PIGCCT asociado **no deben ser editables** desde esta funcionalidad, salvo que exista una historia de usuario específica.



### 4. Validaciones
4.1 El nombre del eje no debe estar vacío.  
4.2 El sistema debe validar que el nuevo nombre del eje:
- No duplique el nombre de otro eje dentro del mismo PIGCCT (ver HU-PIGCCT-SYM-014).
4.3 La descripción debe cumplir con las reglas de longitud y formato definidas por el sistema.



### 5. Persistencia de la información
5.1 Al guardar los cambios, el sistema debe actualizar la información del eje en la base de datos.  
5.2 El sistema debe conservar el identificador único del eje y sus relaciones con otros componentes.



### 6. Trazabilidad y auditoría
6.1 El sistema debe registrar:
- Usuario que realizó la modificación.
- Fecha y hora del cambio.
- Valores anteriores y nuevos (si el sistema cuenta con auditoría).



### 7. Confirmación y mensajes
7.1 Al finalizar la edición correctamente, el sistema debe mostrar un mensaje de confirmación, por ejemplo:
> “El eje ha sido actualizado exitosamente”.

7.2 En caso de error, el sistema debe mostrar mensajes claros y orientados a la corrección.



### 8. Usabilidad y experiencia de usuario
8.1 El formulario de edición debe:
- Precargar la información actual del eje.
- Permitir cancelar la edición sin guardar cambios.

8.2 El sistema debe redirigir al usuario a la vista de detalle o al listado de ejes después de guardar o cancelar.

---

### Resultado esperado

El usuario administrador puede **editar de forma controlada el nombre y la descripción de un eje del PIGCCT**, manteniendo la integridad, unicidad y trazabilidad de la información del plan.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-018.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-018.png)




