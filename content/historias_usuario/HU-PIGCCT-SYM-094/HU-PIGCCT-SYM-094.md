# HU-PIGCCT-SYM-094
## Épica: Alineación estratégica de las medidas del PIGCCT
### Asociar medios de implementación a la medida

---
 
## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                    
> **Quiero:** asociar uno o varios medios de implementación a una medida del PIGCCT.                     
> **Para:** indicar de forma explícita cómo se ejecutará la medida, garantizando coherencia entre la planificación estratégica y los mecanismos operativos de implementación.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad

1.1 El sistema debe permitir el acceso a la opción “Medios de implementación” únicamente a usuarios con rol de administrador del sistema.                    
1.2 La funcionalidad debe estar disponible desde el módulo de Gestión de medidas del PIGCCT.                       
1.3 El usuario debe seleccionar previamente un PIGCCT en estado Activo y una medida registrada.

### 2. Catálogo de medios de implementación

2.1 El sistema debe mostrar un catálogo maestro de medios de implementación, cargado automáticamente desde las tablas maestras del sistema.                        
2.2 La selección de medios de implementación debe ser múltiple.                          
2.3 Cada medio de implementación debe mostrarse con su denominación oficial.

### 3. Asociación de medios de implementación

3.1 El sistema debe permitir:

- Asociar uno o varios medios de implementación a la medida.
- Visualizar los medios de implementación ya asociados.
- Eliminar uno o varios medios de implementación previamente asociados.

3.2 La relación entre medida y medio de implementación debe ser de tipo N:M.                       
3.3 El sistema no debe permitir la duplicación de un mismo medio de implementación para la misma medida.

### 4. Validaciones

4.1 El sistema debe validar que:

- La medida pertenezca a un PIGCCT **Activo**.
- Los medios de implementación seleccionados se encuentren **Activos** en el catálogo maestro.

4.2 En caso de incumplimiento de alguna validación, el sistema debe:

- Bloquear el guardado de la información.
- Mostrar un mensaje claro indicando la causa del error.

### 5. Almacenamiento de la información

5.1 Al confirmar la operación, el sistema debe almacenar las asociaciones en la tabla relacional correspondiente.                      
5.2 Las asociaciones deben quedar disponibles para:

- Análisis de ejecución de la medida.
- Seguimiento y monitoreo del PIGCCT.
- Reportes estratégicos y operativos.

### 6. Mensajes y retroalimentación al usuario

6.1 El sistema debe mostrar un mensaje de confirmación cuando los medios de implementación se asocien exitosamente.                     
6.2 En caso de error, el sistema debe informar la causa y permitir la corrección sin pérdida de información.

### 7. Auditoría y trazabilidad

7.1 El sistema debe registrar automáticamente:

- Usuario que realiza la asociación.
- Fecha y hora de creación o modificación.
- Medida asociada y medio de implementación vinculados.

7.2 Esta información debe estar disponible para fines de auditoría, control y seguimiento institucional.

### 8. Usabilidad y experiencia de usuario

8.1 La interfaz debe ser clara, intuitiva y consistente con el diseño general del sistema.                     
8.2 El sistema debe permitir cancelar la operación sin guardar cambios.                            
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas al cierre del formulario.

### Resultado esperado

Una medida del PIGCCT correctamente asociada a uno o varios medios de implementación, reflejando de manera clara y estructurada los mecanismos mediante los cuales se ejecutará, y quedando disponible para su seguimiento y evaluación dentro del sistema.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-094.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-094.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-093-104.png)

