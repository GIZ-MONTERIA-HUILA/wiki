# HU-PIGCCT-SYM-099
## Épica: Alineación estratégica de las medidas del PIGCCT
### Asociar Objetivos de Desarrollo Sostenible (ODS) a la medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                       
> **Quiero:** asociar uno o varios Objetivos de Desarrollo Sostenible (ODS) a una medida del PIGCCT.                                  
> **Para:** alinear la medida con la Agenda 2030, garantizando coherencia con los compromisos internacionales de desarrollo sostenible y facilitando el análisis de contribución del PIGCCT a los ODS.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad

1.1 El sistema debe permitir el acceso a la opción “Objetivos de Desarrollo Disponible - ODS” únicamente a usuarios con rol de administrador del sistema.                        
1.2 La funcionalidad debe estar disponible desde el módulo de Gestión de medidas del PIGCCT.                      
1.3 El usuario debe seleccionar previamente un PIGCCT en estado Activo y una medida registrada.

### 2. Catálogo de Objetivos de Desarrollo Sostenible

2.1 El sistema debe mostrar el catálogo maestro de Objetivos de Desarrollo Sostenible (ODS), cargado automáticamente desde las tablas maestras del sistema.                     
2.2 La selección de ODS debe ser múltiple.                  
2.3 Cada ODS debe presentarse con su número y denominación oficial.

### 3. Asociación de ODS

3.1 El sistema debe permitir:

- Asociar uno o varios ODS a la medida.
- Visualizar los ODS ya asociados.
- Eliminar asociaciones previamente registradas.

3.2 La relación entre medida y ODS debe ser de tipo N:M.
3.3 El sistema no debe permitir la duplicación de un mismo ODS para la misma medida.

### 4. Validaciones

4.1 El sistema debe validar que:

- La medida pertenezca a un PIGCCT en estado **Activo**.
- Los ODS seleccionados se encuentren **Activos** en el catálogo maestro.

4.2 En caso de incumplimiento de alguna validación, el sistema debe:

- Bloquear el guardado de la información.
- Mostrar un mensaje claro indicando la causa del error.

### 5. Almacenamiento de la información

5.1 Al confirmar la operación, el sistema debe almacenar las asociaciones en la tabla relacional correspondiente.
5.2 Las asociaciones deben quedar disponibles para:

- Análisis de contribución del PIGCCT a la Agenda 2030.
- Seguimiento y monitoreo de medidas.
- Reportes institucionales, nacionales e internacionales.

### 6. Mensajes y retroalimentación al usuario

6.1 El sistema debe mostrar un mensaje de confirmación cuando los ODS se asocien exitosamente.
6.2 En caso de error, el sistema debe informar la causa y permitir la corrección sin pérdida de información.

### 7. Auditoría y trazabilidad

7.1 El sistema debe registrar automáticamente:

- Usuario que realiza la asociación.
- Fecha y hora de creación o modificación.
- Medida asociada y ODS vinculados.

7.2 Esta información debe estar disponible para fines de auditoría, control y seguimiento institucional.

### 8. Usabilidad y experiencia de usuario

8.1 La interfaz debe ser clara, intuitiva y consistente con el diseño general del sistema.
8.2 El sistema debe permitir cancelar la operación sin guardar cambios.
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas.

---

### Resultado esperado

Una medida del PIGCCT correctamente alineada con uno o varios Objetivos de Desarrollo Sostenible (ODS), evidenciando su contribución a la Agenda 2030 y quedando disponible para su análisis, seguimiento y evaluación dentro del sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-099.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-099.png)
