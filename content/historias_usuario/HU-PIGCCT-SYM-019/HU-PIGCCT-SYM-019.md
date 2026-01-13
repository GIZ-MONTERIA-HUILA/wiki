# HU-PIGCCT-SYM-019  
## Épica: Administración de ejes del PIGCCT  
### Cambiar el estado del eje

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** activar o inactivar un eje del PIGCCT.  
> **Para:** gestionar su vigencia operativa sin eliminar información histórica ni afectar la trazabilidad del plan.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y control de acceso
1.1 El sistema debe permitir el cambio de estado de un eje **únicamente** a usuarios con rol de **administrador**.  
1.2 Los usuarios con rol de consulta deben visualizar el estado del eje solo en modo lectura.



### 2. Acceso a la funcionalidad
2.1 El sistema debe permitir cambiar el estado del eje desde:
- La vista de detalle del eje.
- El listado de ejes del PIGCCT.

2.2 La opción debe estar claramente identificada (switch, botón o menú contextual).



### 3. Estados permitidos
3.1 El eje debe contar con al menos los siguientes estados:
- Activo.
- Inactivo.

3.2 El cambio de estado no debe eliminar ni modificar:
- La información histórica del eje.
- Las relaciones existentes con otros componentes del plan.



### 4. Reglas de negocio
4.1 Un eje inactivo:
- No debe estar disponible para selección en procesos operativos o de reporte.
- Sí debe estar disponible para consulta histórica.

4.2 Un eje activo:
- Debe estar disponible para su uso en los módulos que dependan de él.



### 5. Confirmación de la acción
5.1 Antes de inactivar un eje, el sistema debe solicitar confirmación al usuario administrador.  
5.2 El mensaje de confirmación debe advertir claramente el impacto de la acción, por ejemplo:
> “Al inactivar este eje, no podrá ser utilizado en nuevos registros, pero su información histórica se conservará”.



### 6. Persistencia y auditoría
6.1 El sistema debe registrar el cambio de estado en la base de datos.  
6.2 El sistema debe almacenar, cuando aplique:
- Usuario que realizó el cambio.
- Fecha y hora.
- Estado anterior y nuevo.



### 7. Actualización de la interfaz
7.1 Una vez realizado el cambio, el sistema debe reflejar inmediatamente el nuevo estado del eje en la interfaz.  
7.2 El sistema debe actualizar las vistas que dependan del estado del eje (filtros, selecciones, listados).



### 8. Mensajes al usuario
8.1 El sistema debe mostrar un mensaje de éxito al completar la operación, por ejemplo:
> “El estado del eje ha sido actualizado correctamente”.

8.2 En caso de error, el sistema debe mostrar mensajes claros que permitan identificar y corregir el problema.

---

### Resultado esperado

El usuario administrador puede **activar o inactivar ejes del PIGCCT de forma controlada**, asegurando la vigencia operativa del plan, la integridad de la información y la conservación del histórico.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-019.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-019.png)


