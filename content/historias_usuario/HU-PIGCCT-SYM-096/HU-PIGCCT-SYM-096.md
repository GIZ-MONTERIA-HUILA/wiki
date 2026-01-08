# HU-PIGCCT-SYM-096
## Épica: Alineación estratégica de las medidas del PIGCCT
### Asociar líneas instrumentales del PNCC a la medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                 
> **Quiero:** asociar una o varias líneas instrumentales del Plan Nacional de Cambio Climático (PNCC) a una medida del PIGCCT.                   
> **Para:** identificar de manera clara los instrumentos normativos, técnicos, financieros y de gestión que soportan la implementación de la medida, fortaleciendo su coherencia y viabilidad.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad

1.1 El sistema debe permitir el acceso a la opción “Líneas instrumentales del PNCC” únicamente a usuarios con rol de administrador del sistema.                      
1.2 La funcionalidad debe estar disponible desde el módulo de Gestión de medidas del PIGCCT.                       
1.3 El usuario debe seleccionar previamente un PIGCCT en estado Activo y una medida registrada.

### 2. Catálogo de líneas instrumentales del PNCC

2.1 El sistema debe mostrar el catálogo maestro de líneas instrumentales del PNCC, cargado automáticamente desde las tablas maestras del sistema.                       
2.2 La selección de líneas instrumentales debe ser múltiple.                          
2.3 Cada línea instrumental debe presentarse con su denominación oficial.

### 3. Asociación de líneas instrumentales

3.1 El sistema debe permitir:

- Asociar una o varias líneas instrumentales del PNCC a la medida.
- Visualizar las líneas instrumentales ya asociadas.
- Eliminar asociaciones previamente registradas.

3.2 La relación entre medida y línea instrumental del PNCC debe ser de tipo N:M.                          
3.3 El sistema no debe permitir la duplicación de una misma línea instrumental para la misma medida.

### 4. Validaciones

4.1 El sistema debe validar que:

- La medida pertenezca a un PIGCCT en estado **Activo**.
- Las líneas instrumentales seleccionadas se encuentren **Activos** en el catálogo maestro.

4.2 Si alguna validación falla, el sistema debe:

- Bloquear el guardado de la información.    
- Mostrar un mensaje claro indicando la causa del error.

### 5. Almacenamiento de la información

5.1 Al confirmar la operación, el sistema debe almacenar las asociaciones en la tabla relacional correspondiente.                      
5.2 Las asociaciones deben quedar disponibles para:

- Análisis de soporte instrumental de la medida.
- Seguimiento y monitoreo del PIGCCT.
- Reportes estratégicos y operativos.

### 6. Mensajes y retroalimentación al usuario

6.1 El sistema debe mostrar un mensaje de confirmación cuando las líneas instrumentales se asocien exitosamente.                           
6.2 En caso de error, el sistema debe informar la causa y permitir la corrección sin pérdida de información.

### 7. Auditoría y trazabilidad

7.1 El sistema debe registrar automáticamente:

- Usuario que realiza la asociación.
- Fecha y hora de creación o modificación.
- Medida asociada y líneas instrumentales vinculadas.

7.2 Esta información debe estar disponible para fines de auditoría, control y seguimiento institucional.

### 8. Usabilidad y experiencia de usuario

8.1 La interfaz debe ser clara, intuitiva y consistente con el diseño general del sistema.                  
8.2 El sistema debe permitir cancelar la operación sin guardar cambios.                     
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas.

### Resultado esperado

Una medida del PIGCCT correctamente asociada a una o varias líneas instrumentales del PNCC, permitiendo identificar los instrumentos que la soportan y fortaleciendo su análisis, seguimiento y evaluación dentro del sistema.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-096.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-096.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-093-104.png)
