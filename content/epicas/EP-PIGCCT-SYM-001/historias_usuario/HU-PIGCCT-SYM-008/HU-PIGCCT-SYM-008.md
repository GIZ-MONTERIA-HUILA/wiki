# HU-PIGCCT-SYM-008  
## Épica: Administración de la tabla maestra de PIGCCT  
### Inactivar PIGCCT

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** marcar un PIGCCT como **Inactivo**.  
> **Para:** evitar su uso en procesos futuros, conservando la información histórica y la trazabilidad del plan.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la opción de inactivación
1.1 El sistema debe permitir la opción **“Inactivar PIGCCT”** únicamente a usuarios con rol de **administrador**.  
1.2 La opción debe estar disponible desde:
- El listado de PIGCCT.
- La vista de detalle del PIGCCT.



### 2. Confirmación de la acción
2.1 Antes de inactivar el PIGCCT, el sistema debe mostrar un mensaje de confirmación que indique claramente:
- El nombre del PIGCCT.
- El departamento y año asociados.
- Las implicaciones de la inactivación.

2.2 El administrador debe confirmar explícitamente la acción para continuar.



### 3. Efectos de la inactivación
3.1 Un PIGCCT marcado como **Inactivo**:
- No debe estar disponible para la creación de nueva información asociada (ejes, medidas, indicadores, acciones, seguimientos).
- Debe conservar toda la información histórica registrada.
- Debe permanecer visible en los listados y consultas del sistema.

3.2 La inactivación no debe eliminar ni modificar registros asociados al PIGCCT.



### 4. Persistencia del estado
4.1 El sistema debe actualizar el estado del PIGCCT a **Inactivo** en la tabla maestra.  
4.2 El nuevo estado debe reflejarse inmediatamente en todas las vistas y módulos relacionados.



### 5. Relación con filtros y consultas
5.1 Los PIGCCT inactivos:
- No deben aparecer en consultas filtradas por “PIGCCT activos”.
- Deben poder consultarse cuando el usuario seleccione incluir registros inactivos.



### 6. Auditoría y trazabilidad
6.1 El sistema debe registrar automáticamente:
- Usuario que realizó la inactivación.
- Fecha y hora de la acción.
- Estado anterior y estado nuevo.

6.2 La información de auditoría debe conservarse para control y seguimiento institucional.



### 7. Mensajes y retroalimentación
7.1 El sistema debe mostrar un mensaje confirmando que el PIGCCT fue inactivado exitosamente.  
7.2 En caso de error, el sistema debe informar la causa y permitir reintentar la operación.



### 8. Usabilidad y experiencia de usuario
8.1 El sistema debe diferenciar visualmente los PIGCCT inactivos en los listados.  
8.2 El sistema debe prevenir inactivaciones accidentales mediante confirmaciones claras.  
8.3 El administrador debe poder cancelar la acción antes de confirmar.

---

### Resultado esperado

El administrador puede **inactivar un PIGCCT de manera segura y controlada**, evitando su uso futuro sin afectar la información histórica ni la trazabilidad del plan dentro del sistema.

---  

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-008.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-008.png)

