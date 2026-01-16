# HU-PIGCCT-SYM-108  
## Épica: Gestión de adjuntos y evidencias del PIGCCT  
### Validar formato del archivo

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** que el sistema permita únicamente formatos de archivo autorizados para adjuntos.  
> **Para:** garantizar la seguridad del sistema, prevenir la carga de archivos maliciosos, asegurar la compatibilidad con herramientas de visualización y facilitar la interoperabilidad de la información del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Definición de formatos permitidos
1.1 El sistema debe tener definida una lista de **formatos de archivo autorizados** para carga de adjuntos.  
1.2 Los formatos permitidos deben incluir, como mínimo:

**Documentos:**
- PDF
- DOC, DOCX

**Hojas de cálculo:**
- XLS, XLSX
- CSV

**Imágenes:**
- JPG, JPEG
- PNG

**Archivos geoespaciales:**
- SHP (shapefile con sus componentes: .shp, .shx, .dbf, .prj)
- GeoJSON
- KML

**Otros formatos:**
- TXT
- ZIP (para comprimir conjuntos de archivos como shapefiles)

1.3 La lista debe ser configurable por administradores del sistema según necesidades institucionales.

### 2. Configuración de formatos autorizados
2.1 Los formatos permitidos deben almacenarse en una tabla de configuración o parámetro del sistema.  
2.2 Los administradores deben poder agregar o eliminar formatos autorizados desde el módulo de configuración.  
2.3 Cada formato debe registrarse con su extensión y tipo MIME correspondiente.

### 3. Validación de extensión del archivo
3.1 El sistema debe validar la extensión del archivo seleccionado por el usuario.  
3.2 La validación debe realizarse en el cliente (navegador) antes de iniciar la carga.  
3.3 Si la extensión no está autorizada, el sistema debe bloquear la carga inmediatamente.

### 4. Validación de tipo MIME real del archivo
4.1 El sistema debe realizar una validación adicional en el servidor para verificar el **tipo MIME real** del archivo.  
4.2 Esta validación debe analizar el contenido del archivo, no solo confiar en la extensión.  
4.3 Si el tipo MIME real no coincide con los formatos autorizados, el sistema debe rechazar el archivo.  
4.4 Esta validación previene ataques donde se renombra un archivo malicioso con una extensión permitida.

### 5. Bloqueo de carga de formatos no autorizados
5.1 Si el archivo no cumple con los formatos autorizados, el sistema debe:
- Bloquear la carga del archivo.
- No almacenar el archivo en el servidor.
- No registrar información en la tabla `adjuntos`.

5.2 El rechazo debe ocurrir antes de consumir recursos del servidor.

### 6. Mensajes de retroalimentación claros
6.1 Al detectar un formato no autorizado, el sistema debe mostrar un mensaje claro indicando:
- El formato del archivo rechazado.
- Los formatos permitidos.
- Sugerencia de conversión o uso de formato alternativo.

6.2 Ejemplo de mensaje:  
_"Formato de archivo no permitido. El archivo con extensión .EXE no está autorizado. Formatos permitidos: PDF, DOCX, XLSX, JPG, PNG, SHP, GeoJSON, KML."_

### 7. Visualización de formatos permitidos
7.1 El formulario de carga debe mostrar claramente los formatos autorizados antes de que el usuario seleccione el archivo.  
7.2 Ejemplo: _"Formatos permitidos: PDF, DOC, DOCX, XLS, XLSX, JPG, PNG, SHP, GeoJSON, KML"_  
7.3 Esta información debe estar visible en la interfaz de carga de adjuntos.

### 8. Validación en carga múltiple
8.1 Si el sistema permite carga múltiple de archivos, debe validar el formato de cada archivo individualmente.  
8.2 Los archivos con formato permitido deben procesarse correctamente.  
8.3 Los archivos con formato no autorizado deben rechazarse con mensaje específico por cada uno.

### 9. Manejo de archivos comprimidos
9.1 Si se permite la carga de archivos ZIP, el sistema debe validar opcionalmente el contenido del archivo comprimido.  
9.2 El sistema puede restringir que dentro del ZIP solo haya formatos autorizados.  
9.3 Esta validación es especialmente importante para shapefiles que se cargan como conjunto de archivos.

---

### Resultado esperado

Un **sistema de validación robusto** que acepta únicamente formatos de archivo autorizados, validando tanto la extensión como el tipo MIME real del archivo, protegiendo el sistema contra archivos maliciosos y garantizando compatibilidad e interoperabilidad en la gestión documental del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-108.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-108.png)
