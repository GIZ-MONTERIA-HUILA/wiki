# HU-PIGCCT-SYM-057  
## Épica: Administración de indicadores del PIGCCT  
### Consultar indicadores por medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  
> **Quiero:** consultar los indicadores asociados a una medida específica.  
> **Para:** realizar un seguimiento estructurado y organizado del avance del PIGCCT conforme a su jerarquía (PIGCCT → Eje → Medida → Indicador).



## CRITERIOS DE ACEPTACIÓN

### 1. Navegación jerárquica
1.1 El sistema debe permitir navegar desde un PIGCCT hasta una medida específica.  
1.2 Al seleccionar una medida, el sistema debe mostrar automáticamente los **indicadores asociados**.  
1.3 La relación medida–indicador debe respetar la integridad referencial del modelo de datos.



### 2. Visualización del listado de indicadores
2.1 El sistema debe mostrar un listado de los indicadores asociados a la medida seleccionada.  
2.2 Cada indicador debe visualizar al menos la siguiente información:
- Nombre del indicador.  
- Tipo de indicador (producto, gestión, impacto).  
- Estado (activo / inactivo).  
- Unidad de medida.  

2.3 El sistema debe indicar claramente a qué medida pertenece cada indicador.



### 3. Filtros y ordenamiento
3.1 El sistema debe permitir filtrar los indicadores por:
- Estado (activo / inactivo).  
- Tipo de indicador.  
- Función objetivo (maximizar / minimizar).

3.2 El sistema debe permitir ordenar el listado por nombre, estado o tipo.



### 4. Acciones disponibles
4.1 El usuario debe poder seleccionar un indicador para:
- Ver su detalle.  
- Consultar su información histórica.  

4.2 Las acciones disponibles deben ajustarse al rol del usuario (consulta o administración).



### 5. Visualización integrada
5.1 El sistema debe permitir visualizar los indicadores desde:
- El módulo de administración de medidas.  
- Los módulos de seguimiento, análisis y reporte.

5.2 El sistema debe mantener consistencia en la visualización de los indicadores en todos los módulos.



### 6. Rendimiento y usabilidad
6.1 La consulta de indicadores debe realizarse de forma eficiente, incluso cuando una medida tenga múltiples indicadores asociados.  
6.2 El sistema debe mostrar un mensaje informativo cuando una medida no tenga indicadores registrados.



### Resultado esperado

El sistema permite consultar de forma clara y estructurada los indicadores asociados a una medida, facilitando el seguimiento, análisis y evaluación del PIGCCT conforme a su estructura jerárquica.



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-057.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-057.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)
