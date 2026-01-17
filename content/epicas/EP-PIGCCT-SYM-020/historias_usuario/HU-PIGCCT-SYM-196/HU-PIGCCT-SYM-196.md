# HU-PIGCCT-SYM-196  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Gestionar indicadores

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** administrar el catálogo de indicadores del PIGCCT.  
> **Para:** definir, estructurar y mantener los indicadores necesarios para el seguimiento, evaluación y reporte del avance del plan.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la gestión de indicadores
1.1 El sistema debe permitir el acceso al módulo **Catálogo de indicadores** únicamente a usuarios con rol **administrador**.  
1.2 El acceso debe estar disponible desde el módulo de **Catálogos**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos administrativos.

### 2. Visualización del catálogo de indicadores
2.1 El sistema debe mostrar un **listado de indicadores** registrados.  
2.2 El listado debe incluir como mínimo:
- Nombre del indicador.
- Medida y eje asociados.
- Unidad de medida.
- Periodicidad.
- Estado (activo / inactivo).

2.3 El catálogo debe cargarse correctamente al acceder al módulo.

### 3. Registro de nuevos indicadores
3.1 El sistema debe permitir al administrador **crear nuevos indicadores**.  
3.2 El registro debe incluir como mínimo:
- Nombre del indicador.
- Descripción.
- Eje estratégico asociado.
- Medida asociada.
- Fórmula del indicador.
- Unidad de medida.
- Periodicidad de medición.
- Estado inicial.

3.3 El sistema debe validar la coherencia entre eje, medida e indicador.

### 4. Definición de fórmula
4.1 El sistema debe permitir definir la **fórmula del indicador** mediante un campo estructurado o descriptivo.  
4.2 La fórmula debe quedar documentada para su interpretación y uso en el seguimiento.

### 5. Unidad de medida
5.1 El sistema debe permitir seleccionar o definir la **unidad de medida** del indicador.  
5.2 Las unidades deben provenir de un catálogo parametrizable del sistema.

### 6. Periodicidad
6.1 El sistema debe permitir definir la **periodicidad de medición** del indicador (mensual, trimestral, anual, entre otros).  
6.2 La periodicidad debe utilizarse para la generación automática de seguimientos.

### 7. Gestión de estados
7.1 El sistema debe permitir activar o inactivar indicadores.  
7.2 Los indicadores inactivos:
- No deben estar disponibles para nuevas asociaciones.
- Deben conservar su información histórica.

### 8. Uso del catálogo en el sistema
8.1 Los indicadores activos deben estar disponibles en:
- Asociación de acciones.
- Programación y seguimiento.
- Reportes y análisis.

8.2 El sistema debe impedir la selección de indicadores inactivos en procesos operativos.

### 9. Auditoría y trazabilidad
9.1 El sistema debe registrar:
- Usuario creador o modificador.
- Fecha y hora de la operación.
- Cambios realizados.

9.2 Esta información debe estar disponible para fines de auditoría institucional.

### 10. Usabilidad y experiencia de usuario
10.1 La gestión de indicadores debe ser clara, ordenada y fácil de usar.  
10.2 El sistema debe mostrar mensajes claros de confirmación o error.  
10.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El administrador puede **gestionar correctamente el catálogo de indicadores del PIGCCT**, definiendo su fórmula, periodicidad y unidad de medida, asegurando coherencia técnica y facilitando el seguimiento, evaluación y reporte del avance del plan.


---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-196.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-196.png)


