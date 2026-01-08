# HU-PIGCCT-SYM-095
## Épica: Alineación estratégica de las medidas del PIGCCT
### Asociar líneas estratégicas del PNCC a la medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                                  
> **Quiero:** asociar una o varias líneas estratégicas del Plan Nacional de Cambio Climático (PNCC) a una medida del PIGCCT.                                      
> **Para:** garantizar la alineación de la medida con la política nacional de cambio climático, facilitando su coherencia, trazabilidad y análisis estratégico a nivel territorial y nacional.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad

1.1 El sistema debe permitir el acceso a la opción “Líneas estratégicas del PNCC” únicamente a usuarios con rol de administrador del sistema.                               
1.2 La funcionalidad debe estar disponible desde el módulo de Gestión de medidas del PIGCCT.                          
1.3 El usuario debe seleccionar previamente un PIGCCT en estado Activo y una medida registrada.

### 2. Catálogo de líneas estratégicas del PNCC

2.1 El sistema debe mostrar el catálogo maestro de líneas estratégicas del PNCC, cargado automáticamente desde las tablas maestras del sistema.                            
2.2 La selección de líneas estratégicas debe ser múltiple.                             
2.3 Cada línea estratégica debe presentarse con su denominación oficial.

### 3. Asociación de líneas estratégicas

3.1 El sistema debe permitir:

- Asociar una o varias líneas estratégicas del PNCC a la medida.
- Visualizar las líneas estratégicas ya asociadas.
- Eliminar asociaciones previamente registradas.

3.2 La relación entre medida y línea estratégica del PNCC debe ser de tipo N:M.
3.3 El sistema no debe permitir la duplicación de una misma línea estratégica para la misma medida.

### 4. Validaciones

4.1 El sistema debe validar que:

- La medida pertenezca a un PIGCCT en estado **Activo**.
- Las líneas estratégicas seleccionadas se encuentren **Activos** en el catálogo maestro.

4.2 Si alguna validación falla, el sistema debe:

- Bloquear el guardado de la información.
- Mostrar un mensaje claro indicando la causa del error.

### 5. Almacenamiento de la información

5.1 Al confirmar la operación, el sistema debe almacenar las asociaciones en la tabla relacional correspondiente.                       
5.2 Las asociaciones deben quedar disponibles para:

- Análisis de alineación con la política nacional.
- Seguimiento y monitoreo de medidas del PIGCCT.
- Reportes institucionales y nacionales.

### 6. Mensajes y retroalimentación al usuario

6.1 El sistema debe mostrar un mensaje de confirmación cuando las líneas estratégicas se asocien exitosamente.                           
6.2 En caso de error, el sistema debe informar la causa y permitir la corrección sin pérdida de información.

### 7. Auditoría y trazabilidad

7.1 El sistema debe registrar automáticamente:

- Usuario que realiza la asociación.
- Fecha y hora de creación o modificación.
- Medida asociada y líneas estratégicas vinculadas.

7.2 Esta información debe estar disponible para fines de auditoría, control y seguimiento institucional.

### 8. Usabilidad y experiencia de usuario

8.1 La interfaz debe ser clara, intuitiva y consistente con el diseño general del sistema.                  
8.2 El sistema debe permitir cancelar la operación sin guardar cambios.                        
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas.

### Resultado esperado

Una medida del PIGCCT correctamente alineada con una o varias líneas estratégicas del PNCC, asegurando coherencia con la política nacional de cambio climático y quedando disponible para su análisis, seguimiento y evaluación dentro del sistema.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-095.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-095.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-095.png)

## ANEXOS

- Especificación del algoritmo de generación de consecutivo (<número consecutivo>).
