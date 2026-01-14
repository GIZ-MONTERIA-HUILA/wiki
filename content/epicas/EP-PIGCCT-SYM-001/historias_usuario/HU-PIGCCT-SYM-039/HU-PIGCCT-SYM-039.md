# HU-PIGCCT-SYM-039  
## Épica: Administración de medidas del PIGCCT  
### Activar o inactivar medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** cambiar el estado activo o inactivo de una medida del PIGCCT.  
> **Para:** gestionar su vigencia operativa sin eliminar la información histórica ni afectar la trazabilidad del plan.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y acceso
1.1 Solo los usuarios con rol **administrador** pueden activar o inactivar una medida.  
1.2 Los usuarios de consulta solo pueden visualizar el estado de la medida.



### 2. Estado de la medida
2.1 Cada medida debe contar con un campo de **estado** con valores controlados:  
- Activa  
- Inactiva  

2.2 El estado debe ser visible en los listados y en la ficha de detalle de la medida.



### 3. Cambio de estado
3.1 El sistema debe permitir al administrador cambiar el estado de una medida mediante una acción explícita (ej. botón o menú de opciones).  
3.2 El sistema debe solicitar confirmación antes de aplicar el cambio de estado.  
3.3 Al confirmar, el sistema debe actualizar el estado sin eliminar la información asociada.



### 4. Reglas de negocio
4.1 Una medida inactiva:
- No debe mostrarse por defecto en vistas operativas.  
- No debe estar disponible para nuevos procesos de registro o asociación.  

4.2 Una medida activa:
- Debe estar disponible para su uso en los módulos habilitados del sistema.



### 5. Impacto en información asociada
5.1 Al inactivar una medida, el sistema debe conservar:
- Acciones definidas.  
- Actores involucrados.  
- Barreras de implementación.  
- Fuentes de financiación.  

5.2 El sistema no debe eliminar ni alterar la información histórica asociada a la medida.



### 6. Trazabilidad e historial
6.1 El sistema debe registrar el cambio de estado en un historial, incluyendo:
- Estado anterior y nuevo estado.  
- Fecha y hora del cambio.  
- Usuario que realizó la acción.  



### 7. Visualización y filtros
7.1 El sistema debe permitir filtrar medidas por estado (activa / inactiva).  
7.2 Debe existir una opción para consultar medidas inactivas con fines históricos o de análisis.

---

### Resultado esperado

El sistema permite **gestionar la vigencia de las medidas del PIGCCT mediante su activación o inactivación**, garantizando la conservación de la información histórica, la trazabilidad de los cambios y la coherencia del plan en todos los módulos del sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-039.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-039.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-024-041.png)



