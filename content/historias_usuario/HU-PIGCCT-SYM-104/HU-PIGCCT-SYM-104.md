# HU-PIGCCT-SYM-104
## Épica: Alineación estratégica de las medidas del PIGCCT
### Administrar catálogos maestros

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                     
> **Quiero:** crear, editar, activar o inactivar los registros de los catálogos maestros.                     
> **Para:** mantener la información actualizada, confiable y disponible para la asociación con las medidas del PIGCCT, garantizando consistencia y trazabilidad estratégica.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad

1.1 La funcionalidad de administración de catálogos debe estar disponible únicamente para usuarios con rol de administrador del sistema.                           
1.2 Los catálogos maestros que se pueden gestionar incluyen, pero no se limitan a:

- Medios de implementación.
- Líneas estratégicas del PNCC.
- Líneas instrumentales del PNCC.
- Enfoques.
- Dimensiones.
- Objetivos de Desarrollo Sostenible (ODS).

1.3 El acceso debe realizarse desde el módulo de Administración de catálogos del sistema.

### 2. Crear registros

2.1 El sistema debe permitir ingresar nuevos registros en cualquier catálogo maestro.                   
2.2 Los campos obligatorios deben incluir como mínimo:

- Denominación oficial del registro.
- Estado inicial (Activo / Inactivo).

2.3 El sistema debe validar que no exista un registro duplicado antes de permitir su creación.

### 3. Editar registros

3.1 El sistema debe permitir modificar los datos de los registros existentes.                       
3.2 Los cambios deben actualizar la información en la tabla maestra correspondiente, manteniendo la integridad referencial con las asociaciones existentes en medidas.                         
3.3 No se debe permitir modificar identificadores únicos que comprometan la trazabilidad histórica.

### 4. Activar o inactivar registros

4.1 El sistema debe permitir cambiar el estado de un registro (Activo=true / Inactivos=false).               
4.2 Los registros Activos deben estar disponibles para ser asociados a las medidas del PIGCCT.                       
4.3 Los registros Inactivos deben conservar su historial y asociaciones existentes, pero no permitir nuevas asociaciones.

### 5. Validaciones

5.1 El sistema debe validar:

- La unicidad de la denominación de cada registro.
- La vigencia (**Activos / Inactivos**) de los registros asociados al cambiar su estado.

5.2 En caso de error, el sistema debe mostrar un mensaje claro indicando la causa y permitir la corrección.

### 6. Mensajes y retroalimentación al usuario

6.1 El sistema debe mostrar mensajes de confirmación al:

- Crear un registro.
- Editar un registro.
- Activar o inactivar un registro.

6.2 En caso de error, el sistema debe informar la causa de manera clara y detallada.

### 7. Auditoría y trazabilidad

7.1 El sistema debe registrar automáticamente:

- Usuario que realiza la acción.
- Fecha y hora de creación o modificación.
- Tipo de acción realizada (creación, edición, activación, inactivación).

7.2 Esta información debe estar disponible para auditoría y control institucional.

### 8. Usabilidad y experiencia de usuario

8.1 La interfaz debe ser clara, intuitiva y consistente con el diseño general del sistema.                    
8.2 El sistema debe permitir cancelar cualquier acción sin guardar cambios.                        
8.3 El sistema debe prevenir la pérdida de información mediante validaciones y confirmaciones previas a guardar cambios.

### Resultado esperado

Los catálogos maestros del sistema administrados correctamente, con registros actualizados, activos o inactivos según corresponda, asegurando la disponibilidad, consistencia y trazabilidad de la información para la asociación con las medidas del PIGCCT.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-104.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-104.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-093-104.png)

