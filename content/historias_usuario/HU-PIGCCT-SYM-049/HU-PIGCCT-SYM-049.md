# HU-PIGCCT-SYM-049  
## Épica: Administración de indicadores del PIGCCT  
### Registrar fuente de información del indicador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** registrar la fuente de información del indicador.  
> **Para:** garantizar la trazabilidad, confiabilidad y transparencia de los datos utilizados en el seguimiento y evaluación del PIGCCT.



## CRITERIOS DE ACEPTACIÓN

### 1. Registro de la fuente de información
1.1 El sistema debe permitir registrar una o varias **fuentes de información** asociadas al indicador.  
1.2 Cada fuente debe incluir, como mínimo:
- Nombre de la fuente (entidad, sistema, documento o base de datos).  
- Tipo de fuente (primaria, secundaria, administrativa, estadística, geoespacial, etc.).  
- Descripción de la fuente.

1.3 Al menos una fuente de información debe ser obligatoria para guardar el indicador.



### 2. Detalle y documentación de la fuente
2.1 El sistema debe permitir registrar información complementaria de la fuente, como:
- Responsable de la información.  
- Periodicidad de actualización.  
- Enlace o referencia documental (URL o código interno).  

2.2 El sistema debe permitir asociar documentos de soporte (cuando aplique).



### 3. Validaciones de coherencia
3.1 El sistema debe validar que la fuente de información sea coherente con:
- El tipo de indicador.  
- El tipo de cálculo (cuantitativo o cualitativo).

3.2 El sistema debe advertir al usuario si la fuente seleccionada no es adecuada para el tipo de indicador.



### 4. Integridad con el indicador y la medida
4.1 El sistema debe mostrar como referencia el indicador, la medida, el eje y el PIGCCT asociados.  
4.2 El sistema debe impedir guardar la fuente de información si el indicador no está correctamente asociado a una medida válida.



### 5. Edición y trazabilidad
5.1 El sistema debe permitir editar, agregar o retirar fuentes de información del indicador.  
5.2 El sistema debe conservar el historial de cambios, registrando:
- Fuente adicionada, modificada o eliminada.  
- Fecha de la acción.  
- Usuario responsable.



### Resultado esperado

El sistema permite documentar y gestionar las fuentes de información de los indicadores del PIGCCT, fortaleciendo la trazabilidad, la confiabilidad de los datos y la transparencia del proceso de seguimiento y evaluación del plan.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-049.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-049.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)
