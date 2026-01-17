# HU-PIGCCT-SYM-194  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Gestionar ejes estratégicos

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** administrar el catálogo de ejes estratégicos del PIGCCT.  
> **Para:** mantener la consistencia semántica y estructural del plan y garantizar su correcta utilización en la gestión de acciones, medidas e indicadores.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la gestión de ejes estratégicos
1.1 El sistema debe permitir el acceso al módulo **Catálogo de ejes estratégicos** únicamente a usuarios con rol **administrador**.  
1.2 El acceso debe estar disponible desde el módulo de **Catálogos**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos administrativos.

### 2. Visualización del catálogo de ejes
2.1 El sistema debe mostrar un **listado de ejes estratégicos** registrados.  
2.2 El listado debe incluir como mínimo:
- Nombre del eje.
- Descripción.
- Estado (activo / inactivo).

2.3 El catálogo debe cargarse correctamente al acceder al módulo.

### 3. Registro de nuevos ejes
3.1 El sistema debe permitir al administrador **crear nuevos ejes estratégicos**.  
3.2 El registro debe incluir como mínimo:
- Nombre del eje.
- Descripción.
- Estado inicial.

3.3 El sistema debe validar la unicidad del nombre del eje según las reglas definidas.

### 4. Edición de ejes estratégicos
4.1 El administrador debe poder **editar la información de un eje estratégico existente**.  
4.2 Debe ser posible modificar:
- Nombre.
- Descripción.
- Estado.

4.3 El sistema debe validar los cambios antes de guardarlos.

### 5. Gestión de estados
5.1 El sistema debe permitir activar o inactivar ejes estratégicos.  
5.2 Los ejes inactivos:
- No deben estar disponibles para nuevas asociaciones.
- Deben conservar su información histórica.

### 6. Uso del catálogo en el sistema
6.1 Los ejes estratégicos activos deben estar disponibles en:
- Registro de acciones.
- Asociación de medidas.
- Reportes y análisis.

6.2 El sistema debe impedir la selección de ejes inactivos en procesos operativos.

### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar:
- Usuario creador o modificador.
- Fecha y hora de la operación.
- Cambios realizados.

7.2 Esta información debe estar disponible para fines de auditoría.

### 8. Usabilidad y experiencia de usuario
8.1 La gestión del catálogo debe ser clara y ordenada.  
8.2 El sistema debe mostrar mensajes claros de confirmación o error.  
8.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El administrador puede **gestionar correctamente el catálogo de ejes estratégicos del PIGCCT**, asegurando la coherencia conceptual del plan y su correcta utilización en los procesos de registro, validación, seguimiento y reporte.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-194.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-194.png)


