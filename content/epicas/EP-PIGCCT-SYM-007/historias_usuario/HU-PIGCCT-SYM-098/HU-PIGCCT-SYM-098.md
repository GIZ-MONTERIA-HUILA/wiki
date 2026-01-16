# HU-PIGCCT-SYM-098
## Épica: Alineación estratégica de las medidas del PIGCCT
### Asociar dimensiones a la medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                   
> **Quiero:** asociar una o varias dimensiones a una medida del PIGCCT.                      
> **Para:** clasificar la medida dentro del marco analítico del plan, facilitando su análisis integral, organización estratégica y evaluación en los procesos de planificación, seguimiento y monitoreo del PIGCCT.         

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad

1.1 El sistema debe permitir el acceso a la opción “Dimensiones” únicamente a usuarios con rol de administrador del sistema.                
1.2 La funcionalidad debe estar disponible desde el módulo de Gestión de medidas del PIGCCT.                   
1.3 El usuario debe seleccionar previamente un PIGCCT en estado Activo y una medida registrada.          

### 2. Catálogo de dimensiones

2.1 El sistema debe mostrar el catálogo maestro de dimensiones, cargado automáticamente desde las tablas maestras del sistema.                 
2.2 La selección de dimensiones debe ser múltiple.                  
2.3 Cada dimensión debe presentarse con su denominación oficial.

### 3. Asociación de dimensiones

3.1 El sistema debe permitir:

- Asociar una o varias dimensiones a la medida.
- Visualizar las dimensiones ya asociadas.
- Eliminar asociaciones previamente registradas.

3.2 La relación entre medida y dimensión debe ser de tipo N:M.                   
3.3 El sistema no debe permitir la duplicación de una misma dimensión para la misma medida.

### 4. Validaciones

4.1 El sistema debe validar que:

- La medida pertenezca a un PIGCCT en estado**Activo**.
- Las dimensiones seleccionadas se encuentren **Activos** en el catálogo maestro.

4.2 En caso de incumplimiento de alguna validación, el sistema debe:

- Bloquear el guardado de la información.
- Mostrar un mensaje claro indicando la causa del error.

### 5. Almacenamiento de la información

5.1 Al confirmar la operación, el sistema debe almacenar las asociaciones en la tabla relacional correspondiente.               
5.2 Las asociaciones deben quedar disponibles para:

- Clasificación analítica y estratégica de la medida.
- Seguimiento y monitoreo del PIGCCT.
- Reportes institucionales y técnicos.

### 6. Mensajes y retroalimentación al usuario

6.1 El sistema debe mostrar un mensaje de confirmación cuando las dimensiones se asocien exitosamente.                    
6.2 En caso de error, el sistema debe informar la causa y permitir la corrección sin pérdida de información.

### 7. Auditoría y trazabilidad

7.1 El sistema debe registrar automáticamente:

- Usuario que realiza la asociación.
- Fecha y hora de creación o modificación.
- Medida asociada y dimensiones vinculadas.

7.2 Esta información debe estar disponible para fines de auditoría, control y seguimiento institucional.

### 8. Usabilidad y experiencia de usuario

8.1 La interfaz debe ser clara, intuitiva y consistente con el diseño general del sistema.                
8.2 El sistema debe permitir cancelar la operación sin guardar cambios.                
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas.

---

### Resultado esperado

Una medida del PIGCCT correctamente clasificada en una o varias dimensiones, permitiendo su análisis integral dentro del marco analítico del plan y fortaleciendo los procesos de planificación, seguimiento y evaluación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-098.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-098.png)
