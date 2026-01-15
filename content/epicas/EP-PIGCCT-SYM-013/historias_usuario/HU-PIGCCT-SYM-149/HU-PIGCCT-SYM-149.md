# HU-PIGCCT-SYM-149  
## Épica: Asociación de indicadores y adjuntos  
### Adjuntar archivos en estado borrador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** cargar adjuntos a una acción en estado borrador.  
> **Para:** ir construyendo la evidencia del proyecto progresivamente antes de enviar a validación.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Requisito previo: acción guardada
1.1 El sistema debe requerir que la acción esté guardada (tenga `accion_id`) antes de permitir cargar adjuntos.  
1.2 Para acciones nuevas sin guardar, la pestaña **"Adjuntos"** debe estar deshabilitada (ver HU-142).  
1.3 Al intentar acceder, mostrar mensaje: "Guarda la acción primero para poder cargar archivos".

### 2. Habilitación de la pestaña de adjuntos
2.1 Una vez guardada la acción, la pestaña "Adjuntos" se habilita automáticamente (ver HU-143).  
2.2 El usuario puede acceder y cargar archivos inmediatamente después del primer guardado.  
2.3 La habilitación ocurre sin necesidad de recargar la página.

### 3. Acceso a la funcionalidad de carga
3.1 Al acceder a la pestaña "Adjuntos", el sistema debe mostrar:
- Lista de archivos ya cargados (si existen)
- Botón o área para "Cargar nuevo archivo"
- Indicador del total de archivos adjuntos

3.2 Inicialmente, para una acción recién creada, no habrá archivos adjuntos.

### 4. Tipos de archivos permitidos
4.1 El sistema debe permitir cargar archivos en formatos comunes:
- Documentos: PDF, DOC, DOCX
- Hojas de cálculo: XLS, XLSX
- Imágenes: JPG, PNG, GIF
- Comprimidos: ZIP, RAR
- Otros formatos según necesidades del proyecto

4.2 El sistema debe validar el tipo de archivo antes de permitir la carga.

### 5. Tamaño máximo de archivos
5.1 El sistema debe establecer un tamaño máximo por archivo (recomendado: 10-25 MB).  
5.2 Si el archivo excede el límite, debe rechazarse con mensaje claro:
```
"El archivo es demasiado grande. Tamaño máximo permitido: 25 MB"
```

5.3 El límite puede ser configurable por el administrador del sistema.

### 6. Proceso de carga de archivos
6.1 Al seleccionar un archivo para cargar, el sistema debe:
- Validar tipo y tamaño
- Mostrar barra de progreso durante la carga
- Solicitar información adicional: título, descripción, tipo de documento
- Guardar el archivo en almacenamiento seguro
- Crear registro en la tabla `adjuntos`

6.2 La carga debe ser asíncrona para no bloquear la interfaz.

### 7. Almacenamiento en tabla adjuntos
7.1 Cada archivo cargado debe registrarse en la tabla `adjuntos` con:
- `id`: Identificador único del adjunto
- `accion_id`: **Referencia obligatoria** a la acción
- `nombre_archivo`: Nombre original del archivo
- `ruta_archivo`: Ubicación en el almacenamiento
- `tipo_documento`: Categoría del documento (evidencia, soporte, imagen, etc.)
- `descripcion`: Descripción del contenido
- `tamanio`: Tamaño del archivo en bytes
- `extension`: Extensión del archivo
- `creado_por`: Usuario que cargó el archivo
- `fch_creacion`: Fecha de carga

7.2 Opcionalmente puede incluir hash del archivo para verificación de integridad.

### 8. Almacenamiento físico de archivos
8.1 Los archivos deben almacenarse en un sistema de archivos o servicio de almacenamiento seguro (ej: servidor de archivos, S3, Azure Blob Storage).  
8.2 La estructura de carpetas puede organizarse por:
- Año / Mes / ID de acción
- O ID de acción / tipo de documento

8.3 Los nombres de archivo en el almacenamiento deben ser únicos (ej: UUID + extensión).

### 9. Carga en estado borrador
9.1 Los archivos pueden cargarse mientras la acción está en estado borrador sin restricciones.  
9.2 No se requiere que la acción esté completa o validada para cargar evidencias.  
9.3 Esto permite ir construyendo la documentación progresivamente.

### 10. Generación de eventos para adjuntos
10.1 Al cargar un nuevo archivo, el sistema debe generar un evento de tipo **create** en la tabla evento (ver HU-150).  
10.2 El evento debe referenciar:
- `tabla`: 'adjuntos'
- `tabla_id`: ID del registro en la tabla adjuntos
- `accion_id_principal`: ID de la acción a la que pertenece
- `afectacion`: 'create'
- `valor_nuevo`: JSON con metadata del archivo (nombre, tipo, tamaño, descripción)

10.3 El evento permanece sin fecha de envío mientras la acción esté en borrador.

### 11. Visualización de archivos adjuntos
11.1 La pestaña "Adjuntos" debe mostrar una lista de archivos cargados con:
- Icono según tipo de archivo
- Nombre del archivo
- Tipo de documento
- Descripción
- Tamaño
- Fecha de carga
- Usuario que lo cargó
- Opciones: Descargar, Ver, Eliminar

11.2 Puede mostrarse como tabla o como tarjetas visuales.

### 12. Descarga de archivos
12.1 El usuario debe poder descargar cualquier archivo adjunto.  
12.2 Al hacer clic en "Descargar", el archivo debe descargarse con su nombre original.  
12.3 El sistema debe registrar las descargas para auditoría (opcional).

### 13. Vista previa de archivos
13.1 Para ciertos tipos de archivos (PDF, imágenes), el sistema puede ofrecer vista previa sin necesidad de descargar.  
13.2 La vista previa puede abrirse en modal o en nueva pestaña.  
13.3 Esto mejora la experiencia al revisar documentos rápidamente.

### 14. Edición de metadata de adjuntos
14.1 El usuario debe poder editar la metadata del archivo (título, descripción, tipo) mientras la acción esté en borrador.  
14.2 Al modificar metadata, se genera un evento de tipo **update**.  
14.3 No es posible editar el archivo en sí; debe eliminarse y cargarse uno nuevo.

### 15. Eliminación de adjuntos en borrador
15.1 El usuario debe poder eliminar archivos adjuntos mientras la acción esté en borrador.  
15.2 Al eliminar:
- Se elimina el registro de la tabla `adjuntos`
- Se elimina el archivo físico del almacenamiento (o se marca como eliminado)
- Se genera un evento registrando la eliminación

15.3 Debe confirmarse la acción antes de eliminar.

### 16. Múltiples adjuntos por acción
16.1 Una acción puede tener múltiples archivos adjuntos sin límite específico (o con límite configurable).  
16.2 El sistema debe gestionar eficientemente la carga y visualización de múltiples archivos.  
16.3 Puede mostrar contador: "Adjuntos (8)".

### 17. Seguridad de archivos
17.1 Los archivos deben estar protegidos contra acceso no autorizado.  
17.2 Solo usuarios con permisos sobre la acción deben poder ver y descargar sus adjuntos.  
17.3 El sistema debe verificar permisos antes de servir cualquier archivo.

### 18. Validación de contenido
18.1 El sistema puede implementar escaneo de archivos para detectar malware (opcional).  
18.2 Archivos sospechosos deben rechazarse con advertencia al usuario.  
18.3 Esto protege la infraestructura del sistema.

### 19. Feedback durante la carga
19.1 Durante la carga de archivos, mostrar:
- Barra de progreso con porcentaje
- Nombre del archivo que se está cargando
- Estimación de tiempo restante (opcional)

19.2 Al completar exitosamente:
```
"Archivo cargado correctamente"
```

19.3 Si falla:
```
"Error al cargar archivo: [razón del error]"
```

### 20. Transición a validación
20.1 Cuando la acción se envía a validación, los adjuntos se incluyen como parte de la evidencia.  
20.2 Los eventos de adjuntos reciben fecha de envío.  
20.3 Durante la validación, no se pueden cargar nuevos adjuntos ni eliminar existentes (depende de lógica de negocio).

---

### Resultado esperado

**Archivos adjuntos cargados y almacenados** para una acción en estado borrador, con registros en la tabla adjuntos y eventos correspondientes sin fecha de envío, permitiendo construir progresivamente la evidencia del proyecto antes de enviar a validación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-149.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-149.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-149.png)
