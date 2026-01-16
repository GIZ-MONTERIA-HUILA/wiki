# HU-PIGCCT-SYM-168  
## Épica: Formulario de Registro y Gestión de Acciones del PIGCCT  
### Adjuntar evidencias

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** adjuntar archivos como evidencias asociadas a una acción del PIGCCT.  
> **Para:** respaldar la información registrada, documentar el avance de la acción y soportar los procesos de seguimiento, monitoreo y evaluación.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la sección “Adjuntos”
1.1 El sistema debe permitir el acceso a la pestaña **“Adjuntos”** a usuarios con rol de **registrador** y **administrador**.  
1.2 Esta sección debe corresponder a la **sexta pestaña (tab)** del formulario de registro y gestión de acciones del PIGCCT.  
1.3 El sistema debe mostrar los controles necesarios para la carga, visualización y gestión de archivos adjuntos.


### 2. Controles de carga de archivos
2.1 El sistema debe mostrar un **botón “Agregar adjunto”** que permita seleccionar uno o varios archivos desde el dispositivo del usuario.  
2.2 Al seleccionar un archivo, el sistema debe iniciar el proceso de carga y mostrar el estado de la operación.  
2.3 El sistema debe permitir asociar cada archivo cargado a la acción correspondiente.


### 3. Listado de archivos adjuntos
3.1 El sistema debe mostrar una **lista o tabla de archivos adjuntos** asociados a la acción, con al menos los siguientes campos:
- **Nombre del archivo**.  
- **Tipo** (formato o extensión).  
- **Tamaño**.  
- **Descripción** (editable).  
- **Acciones**: **Descargar** / **Eliminar**.

3.2 El listado debe actualizarse automáticamente al agregar o eliminar un archivo.


### 4. Gestión de archivos
4.1 El sistema debe permitir:
- **Descargar** cualquier archivo adjunto disponible.
- **Eliminar** un archivo adjunto, siempre que el usuario tenga los permisos correspondientes.

4.2 Antes de eliminar un archivo:
- El sistema debe solicitar confirmación explícita al usuario.
- Debe advertir que la acción es irreversible.


### 5. Validaciones de archivos
5.1 El sistema debe validar:
- Tamaño máximo permitido por archivo.
- Tipos de archivo aceptados, según las políticas del sistema.

5.2 En caso de archivo no válido:
- El sistema debe rechazar la carga.
- Debe mostrar un mensaje claro indicando la causa (por ejemplo: formato no permitido o tamaño excedido).


### 6. Persistencia e integridad de la información
6.1 Al completar la carga:
- El sistema debe almacenar el archivo y su metadata (nombre, tipo, tamaño, descripción, usuario, fecha y hora).  
6.2 Los archivos adjuntos deben quedar asociados de forma permanente a la acción, salvo que sean eliminados por un usuario autorizado.  
6.3 La información debe estar disponible para:
- Seguimiento y monitoreo.
- Auditoría.
- Soporte documental del PIGCCT.


### 7. Guardado progresivo
7.1 El sistema debe permitir el **guardado progresivo** de los adjuntos:
- El usuario puede agregar archivos sin necesidad de completar todo el formulario.
- Los archivos cargados deben permanecer asociados aun cuando otras secciones no estén finalizadas.

7.2 En caso de error durante la carga:
- El sistema debe informar claramente la causa.
- No debe perderse la información previamente cargada.


### 8. Indicadores de estado y retroalimentación
8.1 El sistema debe mostrar mensajes claros de:
- Carga exitosa de archivos.
- Errores durante la carga o eliminación.

8.2 El sistema debe proporcionar retroalimentación visual del estado de cada archivo (por ejemplo: cargado, en proceso, error).


### 9. Usabilidad y experiencia de usuario
9.1 La interfaz de la pestaña **Adjuntos** debe ser clara, ordenada y consistente con el diseño general del sistema.  
9.2 El sistema debe facilitar la identificación y gestión de los archivos mediante acciones directas (descargar / eliminar).  
9.3 El sistema debe prevenir la pérdida de información mediante confirmaciones y mensajes de advertencia antes de eliminar archivos.

---

### Resultado esperado

El usuario puede **adjuntar, gestionar y consultar evidencias asociadas a una acción del PIGCCT**, mediante una interfaz clara con carga controlada de archivos, listado detallado, acciones de descarga y eliminación, y persistencia segura de la información como soporte documental para la gestión, seguimiento y evaluación del plan.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-168.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-168.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-168.png)
