# HU-PIGCCT-SYM-109  
## Épica: Gestión de adjuntos y evidencias del PIGCCT  
### Editar descripción del adjunto

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  
> **Quiero:** editar la descripción de un archivo adjunto previamente cargado.  
> **Para:** aclarar, actualizar o mejorar la información sobre su contenido o propósito, facilitando la comprensión y búsqueda de evidencias documentales dentro del contexto del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de edición
1.1 El sistema debe permitir editar la descripción de un adjunto desde la lista de archivos asociados a un registro.  
1.2 La opción **"Editar descripción"** debe estar disponible mediante un ícono o botón en cada adjunto listado.  
1.3 Los usuarios con permisos de edición sobre el registro deben poder editar las descripciones de sus adjuntos.

### 2. Identificación del adjunto a editar
2.1 El sistema debe identificar claramente el adjunto cuya descripción será editada.  
2.2 Debe mostrar información básica del archivo: nombre original, tipo, fecha de carga, para confirmar la selección correcta.  
2.3 El identificador único del adjunto debe manejarse internamente por el sistema.

### 3. Formulario de edición de descripción
3.1 Al seleccionar la opción de editar, el sistema debe mostrar un formulario con:
- Campo de texto para la descripción actual (editable).
- Botón **"Guardar"** para confirmar cambios.
- Botón **"Cancelar"** para descartar cambios.

3.2 El campo de descripción debe permitir texto largo (ej: hasta 500 o 1000 caracteres).  
3.3 El formulario puede mostrarse como modal, panel lateral o en línea según el diseño del sistema.

### 4. Validación de la descripción
4.1 El sistema debe validar que la descripción no exceda el límite de caracteres permitido.  
4.2 Debe mostrar un contador de caracteres para orientar al usuario.  
4.3 La descripción puede ser opcional (campo puede quedar vacío).  
4.4 El sistema debe sanitizar el texto para prevenir inyección de código.

### 5. Actualización en la base de datos
5.1 Al confirmar la edición, el sistema debe actualizar el campo `descripcion` en la tabla `adjuntos`.  
5.2 La actualización debe realizarse solo para el registro específico identificado.  
5.3 El resto de la información del adjunto (archivo, nombre, tamaño, etc.) no debe modificarse.

### 6. Actualización de fecha de modificación
6.1 El sistema debe actualizar automáticamente el campo `updatedat` con la fecha y hora actual.  
6.2 Esta actualización debe ocurrir al guardar la nueva descripción.  
6.3 El campo `createdat` debe permanecer sin cambios (fecha de carga original).

### 7. Registro de auditoría
7.1 El sistema debe registrar la modificación para trazabilidad:
- Usuario que realizó la edición.
- Fecha y hora de la modificación.
- Descripción anterior (opcional, para historial de cambios).
- Descripción nueva.

7.2 Esta información debe estar disponible en logs o tabla de auditoría.

---

### Resultado esperado

La **descripción del adjunto actualizada correctamente** en la tabla `adjuntos`, con el campo `updatedat` reflejando la fecha de modificación, y registro de auditoría completo del cambio, permitiendo una mejor documentación y comprensión del propósito de cada archivo en el contexto del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-109.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-109.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-109.png)
