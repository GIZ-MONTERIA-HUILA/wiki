# HU-PIGCCT-SYM-106  
## Épica: Gestión de adjuntos del PIGCCT  
### Asociar adjunto a una acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  
> **Quiero:** asociar uno o varios archivos adjuntos a una acción específica del PIGCCT.  
> **Para:** documentar adecuadamente su formulación, ejecución o cierre, respaldando la gestión y seguimiento de las acciones climáticas territoriales.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de asociación de adjuntos
1.1 El sistema debe permitir asociar adjuntos desde el módulo de **Gestión de Acciones** del PIGCCT.  
1.2 La opción de **"Asociar adjunto"** debe estar visible en la interfaz de detalle de cada acción.  
1.3 Los usuarios con permisos de edición sobre la acción deben poder asociar adjuntos.

### 2. Selección de la acción objetivo
2.1 El sistema debe identificar claramente la acción a la que se asociarán los adjuntos.  
2.2 El identificador único de la acción (`id_accion`) debe capturarse automáticamente del contexto.  
2.3 El sistema debe mostrar información básica de la acción (nombre, código, estado) para confirmar la asociación correcta.

### 3. Registro de la relación con la acción
3.1 El sistema debe registrar automáticamente la referencia del adjunto con la acción mediante los siguientes campos:
- **relatedtable**: Debe establecerse con el valor `'accion'`.
- **relatedid**: Debe establecerse con el `id_accion` de la acción seleccionada.
- **relatedschema**: Debe establecerse según el esquema de base de datos correspondiente.

3.2 Esta relación debe quedar almacenada en la tabla `adjuntos`.

### 4. Carga múltiple de adjuntos
4.1 El sistema debe permitir asociar uno o varios archivos adjuntos en una misma operación.  
4.2 Cada archivo debe procesarse individualmente y crear un registro independiente en la tabla `adjuntos`.  
4.3 El sistema debe mostrar el progreso de carga cuando se procesan múltiples archivos.

### 5. Validación de permisos
5.1 El sistema debe validar que el usuario tenga permisos de edición sobre la acción antes de permitir la asociación.  
5.2 Si el usuario no tiene permisos, el sistema debe:
- Bloquear la operación.
- Mostrar un mensaje indicando la falta de permisos.

### 6. Validación de existencia de la acción
6.1 El sistema debe validar que la acción exista y esté activa antes de permitir la asociación.  
6.2 Si la acción no existe o está inactiva, el sistema debe:
- Bloquear la asociación.
- Mostrar un mensaje claro explicando la situación.

### 7. Organización por etapa o fase
7.1 El sistema debe permitir, opcionalmente, categorizar el adjunto según la etapa de la acción:
- Formulación.
- Ejecución.
- Cierre o evaluación.

7.2 Esta categorización debe facilitarse mediante un campo o etiqueta en el formulario de carga.

### 8. Mensajes y retroalimentación al usuario
8.1 Al asociar exitosamente los adjuntos, el sistema debe mostrar un mensaje de confirmación.  
8.2 El mensaje debe indicar la cantidad de archivos asociados correctamente.  
8.3 En caso de error en algún archivo, el sistema debe informar cuáles se asociaron y cuáles fallaron.

### 9. Auditoría y trazabilidad
9.1 El sistema debe registrar automáticamente:
- Usuario que realizó la asociación.
- Fecha y hora de la asociación.
- Acción a la que se asociaron los adjuntos.

9.2 Esta información debe estar disponible para auditorías y control institucional.

### 10. Integridad referencial
10.1 El sistema debe garantizar la integridad referencial entre la tabla `adjuntos` y la tabla `accion`.  
10.2 No debe ser posible eliminar una acción si tiene adjuntos asociados activos sin gestionar previamente dichos adjuntos.

### 11. Usabilidad y experiencia de usuario
11.1 La interfaz de asociación debe ser intuitiva y accesible desde el detalle de la acción.  
11.2 El sistema debe permitir arrastrar y soltar archivos para facilitar la carga.  
11.3 El sistema debe prevenir duplicados informando si un archivo con el mismo nombre ya está asociado a la acción.

---

### Resultado esperado

Uno o varios **archivos adjuntos correctamente asociados** a una acción específica del PIGCCT, con la relación documentada en la tabla `adjuntos` (`relatedtable='accion'`, `relatedid=id_accion`), disponibles para consulta y auditoría dentro del contexto de gestión de acciones climáticas territoriales.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-106.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-106.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-106.png)
