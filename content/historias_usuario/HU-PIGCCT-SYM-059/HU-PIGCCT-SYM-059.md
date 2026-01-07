# HU-PIGCCT-SYM-059  
## Épica: Administración de indicadores del PIGCCT  
### Visualizar solo indicadores activos

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  
> **Quiero:** visualizar únicamente los indicadores activos.  
> **Para:** trabajar con información vigente y evitar el uso de indicadores que ya no se encuentran en operación dentro del PIGCCT.



## CRITERIOS DE ACEPTACIÓN

### 1. Filtro por estado del indicador
1.1 El sistema debe disponer de un filtro que permita visualizar solo los indicadores con estado **activo**.  
1.2 El filtro debe poder activarse o desactivarse por el usuario.  
1.3 Al activarse, el sistema debe excluir del listado todos los indicadores con estado **inactivo**.



### 2. Comportamiento por defecto
2.1 En los módulos operativos y de seguimiento, el sistema debe mostrar por defecto únicamente los indicadores **activos**.  
2.2 En los módulos de consulta histórica, el usuario debe poder visualizar indicadores activos e inactivos.



### 3. Integración con otros filtros
3.1 El filtro de indicadores activos debe funcionar de manera combinada con:
- Filtro por tipo de indicador.  
- Filtro por medida.  
- Filtro por eje o PIGCCT.

3.2 El sistema debe mantener consistencia en los resultados al aplicar múltiples filtros simultáneamente.



### 4. Visualización de resultados
4.1 El listado de indicadores debe actualizarse de forma inmediata al aplicar el filtro.  
4.2 El sistema debe indicar visualmente que el filtro de “solo activos” está aplicado.  
4.3 Si no existen indicadores activos bajo los criterios seleccionados, el sistema debe mostrar un mensaje informativo.



### 5. Rendimiento y usabilidad
5.1 El sistema debe realizar el filtrado de forma eficiente incluso con un alto volumen de indicadores.  
5.2 El filtrado debe apoyarse en consultas optimizadas sobre el campo de estado del indicador.



### Resultado esperado

El sistema permite consultar exclusivamente los indicadores activos del PIGCCT, facilitando el trabajo con información vigente y mejorando la claridad y eficiencia en los procesos de seguimiento y análisis.



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-059.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-059.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)
