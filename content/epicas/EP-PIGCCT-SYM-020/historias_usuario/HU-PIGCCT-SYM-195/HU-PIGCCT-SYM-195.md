# HU-PIGCCT-SYM-195  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Gestionar medidas

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** administrar el catálogo de medidas del PIGCCT asociadas a los ejes estratégicos.  
> **Para:** garantizar la coherencia estructural del plan y su correcta utilización en la formulación, seguimiento y reporte de las acciones.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la gestión de medidas
1.1 El sistema debe permitir el acceso al módulo **Catálogo de medidas** únicamente a usuarios con rol **administrador**.  
1.2 El acceso debe estar disponible desde el módulo de **Catálogos**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos administrativos.

### 2. Visualización del catálogo de medidas
2.1 El sistema debe mostrar un **listado de medidas** registradas en el sistema.  
2.2 El listado debe incluir como mínimo:
- Nombre de la medida.
- Eje estratégico asociado.
- Descripción.
- Estado (activo / inactivo).

2.3 El catálogo debe cargarse correctamente al acceder al módulo.

### 3. Registro de nuevas medidas
3.1 El sistema debe permitir al administrador **crear nuevas medidas**.  
3.2 El registro debe requerir obligatoriamente la asociación a un **eje estratégico**.  
3.3 El sistema debe validar que la medida pertenezca a un eje válido y activo.

### 4. Edición de medidas
4.1 El administrador debe poder **editar la información de una medida existente**.  
4.2 Debe ser posible modificar:
- Nombre de la medida.
- Descripción.
- Eje asociado.
- Estado.

4.3 El sistema debe validar los cambios antes de guardarlos.

### 5. Gestión de estados
5.1 El sistema debe permitir activar o inactivar medidas.  
5.2 Las medidas inactivas:
- No deben estar disponibles para nuevas asociaciones.
- Deben conservar su información histórica.

### 6. Relación medida – eje
6.1 Cada medida debe estar asociada obligatoriamente a un único eje estratégico.  
6.2 El sistema debe garantizar la integridad de la relación entre eje y medida.

### 7. Uso del catálogo en el sistema
7.1 Las medidas activas deben estar disponibles en:
- Registro y edición de acciones.
- Asociación de indicadores.
- Reportes y análisis.

7.2 El sistema debe impedir la selección de medidas inactivas en procesos operativos.

### 8. Auditoría y trazabilidad
8.1 El sistema debe registrar:
- Usuario creador o modificador.
- Fecha y hora de la operación.
- Cambios realizados.

8.2 Esta información debe estar disponible para auditoría institucional.

### 9. Usabilidad y experiencia de usuario
9.1 La gestión de medidas debe ser clara, ordenada y fácil de usar.  
9.2 El sistema debe mostrar mensajes claros de confirmación o error.  
9.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El administrador puede **gestionar de forma correcta el catálogo de medidas del PIGCCT**, manteniendo su asociación con los ejes estratégicos, asegurando coherencia estructural y facilitando su uso en los procesos de planeación, seguimiento y reporte del sistema.


---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-195.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-195.png)


