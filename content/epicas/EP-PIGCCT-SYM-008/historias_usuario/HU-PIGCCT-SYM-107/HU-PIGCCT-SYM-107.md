# HU-PIGCCT-SYM-107  
## Épica: Gestión de adjuntos y evidencias del PIGCCT  
### Validar tamaño máximo del archivo

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** que el sistema valide el tamaño máximo permitido para archivos adjuntos.  
> **Para:** garantizar un uso eficiente del almacenamiento, prevenir saturación del servidor y mantener un rendimiento óptimo en la carga y descarga de documentos del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Definición del tamaño máximo permitido
1.1 El sistema debe tener definido un **tamaño máximo permitido** para archivos adjuntos.  
1.2 Este tamaño debe ser configurable a través de un parámetro del sistema (ej: `max_file_size_mb`).  
1.3 El valor debe poder expresarse en megabytes (MB) y almacenarse en la tabla de configuración o variables de entorno.

### 2. Validación durante la carga del archivo
2.1 El sistema debe validar el tamaño del archivo **antes de iniciar la carga** al servidor.  
2.2 La validación debe realizarse en el cliente (navegador) para evitar transferencias innecesarias.  
2.3 El sistema debe realizar una validación adicional en el servidor para garantizar seguridad.

### 3. Bloqueo de carga si se supera el límite
3.1 Si el archivo supera el tamaño máximo permitido, el sistema debe:
- Bloquear inmediatamente la carga.
- No permitir que el archivo se almacene en el servidor.
- No registrar ningún dato en la tabla `adjuntos`.

3.2 El sistema no debe consumir ancho de banda ni espacio temporal en el servidor para archivos que exceden el límite.

### 4. Mensajes de retroalimentación claros
4.1 Al detectar que el archivo supera el límite, el sistema debe mostrar un mensaje claro indicando:
- El tamaño del archivo intentado.
- El tamaño máximo permitido.
- Sugerencia de comprimir o dividir el archivo.

4.2 Ejemplo de mensaje:  
_"El archivo excede el tamaño máximo permitido. Tamaño del archivo: 25 MB. Tamaño máximo: 10 MB. Por favor, comprima el archivo o divídalo en partes más pequeñas."_

### 5. Visualización del límite antes de cargar
5.1 El formulario de carga debe mostrar claramente el tamaño máximo permitido antes de que el usuario seleccione el archivo.  
5.2 Ejemplo: _"Tamaño máximo por archivo: 10 MB"_  
5.3 Esta información debe estar visible en la interfaz de carga de adjuntos.

### 6. Validación individual en carga múltiple
6.1 Si el sistema permite carga múltiple de archivos, debe validar el tamaño de cada archivo individualmente.  
6.2 Los archivos que cumplan el límite deben procesarse correctamente.  
6.3 Los archivos que excedan el límite deben rechazarse con mensaje específico por cada archivo rechazado.

### 7. Gestión de configuración por administradores
7.1 Los usuarios con rol de **administrador del sistema** deben poder modificar el parámetro de tamaño máximo.  
7.2 El cambio debe aplicarse inmediatamente a todas las nuevas cargas.  
7.3 El sistema debe registrar auditoría de cambios en este parámetro crítico.

### 8. Consideraciones de rendimiento
8.1 La validación de tamaño debe ejecutarse de forma eficiente sin afectar la experiencia de usuario.  
8.2 El sistema debe prevenir ataques de tipo "denial of service" mediante intentos de carga de archivos excesivamente grandes.  
8.3 El servidor debe tener configuraciones adicionales (nginx, apache) para rechazar cargas superiores al límite configurado.

### 9. Excepciones y permisos especiales
9.1 El sistema puede permitir que ciertos usuarios o roles específicos (ej: superadministrador) tengan límites superiores o sin límite.  
9.2 Estas excepciones deben estar claramente documentadas y auditadas.

### 10. Usabilidad y experiencia de usuario
10.1 El mensaje de error debe ser amigable y orientado a la solución.  
10.2 El sistema debe permitir al usuario seleccionar otro archivo inmediatamente después del rechazo.  
10.3 No debe requerirse recargar la página o reiniciar el proceso completo.

---

### Resultado esperado

Un **sistema de validación efectivo** que bloquea la carga de archivos que superen el tamaño máximo configurado, informando claramente al usuario sobre el límite y la razón del rechazo, garantizando el uso eficiente del almacenamiento y el rendimiento óptimo del sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-107.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-107.png)
