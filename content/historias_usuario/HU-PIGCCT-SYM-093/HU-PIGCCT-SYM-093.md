# HU-PIGCCT-SYM-093
## Épica: Alineación estratégica de las medidas del PIGCCT
### Asociar catálogos estratégicos a la medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                   
> **Quiero:** asociar una medida del PIGCCT con uno o varios elementos de los catálogos estratégicos definidos.                
> **Para:** garantizar la alineación estratégica de las medidas con los lineamientos nacionales, enfoques transversales, dimensiones de gestión y compromisos de desarrollo sostenible, permitiendo una correcta estructuración, seguimiento y análisis del PIGCCT.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de asociación

1.1 El sistema debe permitir el acceso a la opción “Catálogos asociados a la medida” únicamente a usuarios con rol de administrador del sistema.                         
1.2 La opción debe estar disponible desde el módulo de Gestión de medidas del PIGCCT.                     
1.3 El usuario debe seleccionar previamente un PIGCCT activo y una medida registrada para habilitar la funcionalidad.

### 2. Catálogos estratégicos disponibles

2.1 El sistema debe permitir asociar una medida bajo una relación N:M con los siguientes catálogos maestros:

- Medio de implementación.
- Línea estratégica del PNCC.
- Línea instrumental del PNCC.
- Enfoque.
- Dimensión.
- Objetivo de Desarrollo Sostenible (ODS).

2.2 Los valores de cada catálogo deben cargarse automáticamente desde las tablas maestras del sistema.                         
2.3 Cada catálogo debe permitir la selección de uno o varios registros, según aplique.

### 3. Gestión de asociaciones

3.1 El sistema debe permitir:

- Agregar nuevas asociaciones entre la medida y los catálogos.
- Visualizar las asociaciones existentes.
- Eliminar asociaciones previamente registradas.

3.2 Las asociaciones deben ser independientes por cada catálogo, permitiendo combinaciones múltiples.                       
3.3 El sistema no debe permitir duplicar una misma asociación catálogo–medida.

### 4. Validaciones

4.1 El sistema debe validar que:

- La medida seleccionada pertenezca a un PIGCCT en estado Activo.
- Los elementos seleccionados correspondan a catálogos vigentes.

4.2 En caso de inconsistencias, el sistema debe bloquear el guardado y mostrar un mensaje claro indicando el error.

### 5. Almacenamiento de la información

5.1 Al confirmar la operación, el sistema debe almacenar las asociaciones en las tablas relacionales correspondientes.                      
5.2 Las asociaciones deben quedar disponibles para:

- Análisis estratégico del PIGCCT.
- Seguimiento y monitoreo de medidas.
- Reportes institucionales y nacionales.

### 6. Mensajes y retroalimentación al usuario

6.1 El sistema debe mostrar un mensaje de confirmación cuando las asociaciones se registren exitosamente.                         
6.2 En caso de error, el sistema debe informar la causa y permitir la corrección sin pérdida de información.

### 7. Auditoría y trazabilidad

7.1 El sistema debe registrar automáticamente:

- Usuario que realiza la asociación.
- Fecha y hora de creación o modificación.
- Medida asociada y catálogo correspondiente.

7.2 Esta información debe estar disponible para fines de auditoría y control.

### 8. Usabilidad y experiencia de usuario

8.1 El formulario debe ser claro, organizado por tipo de catálogo y consistente con el diseño general del sistema.                      
8.2 El sistema debe permitir cancelar la operación sin guardar cambios.                     
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas.

### Resultado esperado

Una medida del PIGCCT correctamente alineada estratégicamente, asociada de forma N:M con los catálogos de medio de implementación, lineamientos PNCC, enfoques, dimensiones y ODS, lista para su análisis, seguimiento y evaluación dentro del sistema.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-093.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-093.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-093-104.png)