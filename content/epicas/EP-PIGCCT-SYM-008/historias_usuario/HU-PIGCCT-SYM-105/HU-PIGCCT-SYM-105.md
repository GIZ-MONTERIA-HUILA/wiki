# HU-PIGCCT-SYM-105  
## Épica: Gestión de adjuntos y evidencias del PIGCCT  
### Cargar adjunto asociado a un registro

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  
> **Quiero:** cargar un archivo adjunto asociado a un registro en el sistema.  
> **Para:** respaldar la información registrada mediante evidencias documentales, garantizando su trazabilidad, almacenamiento seguro y disponibilidad para consulta y auditoría.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de carga de adjuntos
1.1 El sistema debe permitir el acceso a la opción **"Cargar adjunto"** a todos los usuarios autenticados en el sistema.  
1.2 La opción debe estar disponible desde cualquier módulo que requiera evidencias documentales (acciones, medidas, indicadores, entre otros).  
1.3 Al seleccionar la opción, el sistema debe mostrar un formulario de carga de adjuntos.

### 2. Formulario de carga del adjunto
2.1 El formulario debe permitir ingresar los siguientes campos:
- **Archivo** (obligatorio): Selector de archivo desde el equipo del usuario.
- **Descripción** (obligatorio): Campo de texto para describir el propósito o contenido del archivo.
- **Registro relacionado** (automático): El sistema debe identificar automáticamente el registro al cual se asociará el adjunto.

2.2 El sistema debe validar que todos los campos obligatorios estén diligenciados antes de permitir la carga.  
2.3 El sistema debe mostrar el nombre original del archivo seleccionado antes de confirmar la carga.

### 3. Almacenamiento del archivo adjunto
3.1 Al confirmar la carga, el sistema debe almacenar el archivo en la **tabla adjuntos** con la siguiente información:
- **filename**: Nombre único generado por el sistema para el archivo almacenado.
- **originalname**: Nombre original del archivo cargado por el usuario.
- **descripción**: Descripción proporcionada por el usuario.
- **mimetype**: Tipo MIME del archivo (ej. application/pdf, image/png).
- **size**: Tamaño del archivo en bytes.
- **path**: Ruta de almacenamiento del archivo en el sistema.
- **createdat**: Fecha y hora de creación del registro.

3.2 El sistema debe asignar automáticamente un identificador único al adjunto cargado.

### 4. Registro de la referencia del adjunto
4.1 El sistema debe registrar la relación del adjunto con el registro asociado mediante los siguientes campos:
- **relatedschema**: Esquema de la base de datos al que pertenece el registro relacionado.
- **relatedtable**: Nombre de la tabla del registro relacionado (ej. 'accion', 'medida', 'indicador').
- **relatedid**: Identificador único del registro relacionado.

4.2 Esta información debe permitir la trazabilidad completa entre el adjunto y el registro al que respalda.

### 5. Validaciones de seguridad y almacenamiento
5.1 El sistema debe validar que el archivo cumpla con las políticas de seguridad del sistema (ver HU-PIGCCT-SYM-107 y HU-PIGCCT-SYM-108 para validaciones de tamaño y formato).  
5.2 El sistema debe almacenar el archivo en una ubicación segura del servidor, preservando su integridad.  
5.3 El archivo no debe ser accesible directamente mediante URL pública sin autenticación.

### 6. Mensajes y retroalimentación al usuario
6.1 Al cargar exitosamente el adjunto, el sistema debe mostrar un mensaje de confirmación: **"Adjunto cargado correctamente"**.  
6.2 En caso de error de validación o falla en el proceso, el sistema debe informar claramente la causa (ej. "El archivo supera el tamaño máximo permitido" o "Formato de archivo no permitido").  
6.3 El sistema debe permitir cancelar la carga sin guardar cambios.

### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar automáticamente:
- Usuario que cargó el adjunto.
- Fecha y hora de carga (createdat).
- Información de referencia completa (relatedschema, relatedtable, relatedid).

7.2 Esta información debe ser utilizada para fines de auditoría y control institucional.

### 8. Usabilidad y experiencia de usuario
8.1 El formulario debe ser claro, intuitivo y consistente con el diseño general del sistema.  
8.2 El sistema debe mostrar el progreso de carga para archivos de gran tamaño.  
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas al cierre del formulario.  
8.4 El usuario debe poder visualizar inmediatamente el adjunto cargado en la lista de evidencias del registro relacionado.

---

### Resultado esperado

Un **archivo adjunto cargado correctamente** en la tabla adjuntos del sistema, asociado de manera inequívoca a un registro específico mediante los campos de referencia (relatedschema, relatedtable, relatedid), con toda la metadata necesaria para su gestión, consulta y auditoría posterior.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-105.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-105.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-105.png)
