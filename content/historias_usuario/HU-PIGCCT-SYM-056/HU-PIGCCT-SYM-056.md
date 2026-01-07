# HU-PIGCCT-SYM-056  
## Épica: Administración de indicadores del PIGCCT  
### Activar o inactivar indicador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** activar o inactivar un indicador.  
> **Para:** gestionar su vigencia dentro del PIGCCT sin eliminar información histórica, garantizando trazabilidad y consistencia en el seguimiento.



## CRITERIOS DE ACEPTACIÓN

### 1. Gestión del estado del indicador
1.1 El sistema debe disponer de un campo de estado para el indicador con los valores **activo** e **inactivo**.  
1.2 El estado por defecto del indicador debe ser **activo** al momento de su creación.  
1.3 El usuario administrador debe poder cambiar el estado del indicador en cualquier momento.



### 2. Comportamiento según el estado
2.1 Cuando un indicador esté **inactivo**, no debe estar disponible para:
- Registro de nuevos datos de seguimiento.  
- Selección en procesos operativos o de reporte vigentes.

2.2 Los indicadores inactivos deben mantenerse disponibles para:
- Consulta histórica.  
- Análisis comparativo.  
- Visualización en reportes históricos.



### 3. Restricciones y validaciones
3.1 El sistema debe impedir la eliminación física del indicador.  
3.2 El sistema debe validar que un indicador inactivo no pueda ser asociado a nuevos procesos o registros futuros.  
3.3 El sistema debe advertir al usuario si intenta inactivar un indicador que tenga información asociada activa.



### 4. Visualización
4.1 El estado del indicador debe ser visible en los listados y vistas de detalle.  
4.2 El sistema debe permitir filtrar indicadores por estado (activo / inactivo).  



### 5. Trazabilidad
5.1 El sistema debe registrar el historial de cambios de estado del indicador.  
5.2 Cada cambio de estado debe almacenar:
- Estado anterior.  
- Nuevo estado.  
- Fecha del cambio.  
- Usuario que realizó la acción.



### 6. Integridad con el modelo de datos
6.1 El estado del indicador debe mantenerse consistente con la medida, eje y PIGCCT asociados.  
6.2 El sistema debe impedir inconsistencias que afecten la integridad referencial del sistema.



### Resultado esperado

El sistema permite activar o inactivar indicadores del PIGCCT de forma controlada, preservando la información histórica y garantizando una gestión adecuada de la vigencia de los indicadores en los procesos de seguimiento y evaluación.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-056.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-056.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-056.png)
