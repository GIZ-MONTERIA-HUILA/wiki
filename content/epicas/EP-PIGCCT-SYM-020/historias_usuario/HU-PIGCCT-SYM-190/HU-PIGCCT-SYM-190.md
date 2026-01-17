# HU-PIGCCT-SYM-190  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Exportar reportes

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado con permisos de consulta o administración.  
> **Quiero:** exportar los reportes generados en formatos PDF y Excel.  
> **Para:** descargar, compartir y presentar la información del PIGCCT respetando los filtros y criterios seleccionados.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la exportación de reportes
1.1 El sistema debe permitir la opción **“Exportar reporte”** a usuarios con permisos de consulta, validación o administración.  
1.2 La opción debe estar disponible dentro del módulo de **Reportes**.  
1.3 El sistema no debe permitir la exportación a usuarios no autorizados.

### 2. Formatos de exportación
2.1 El sistema debe permitir exportar los reportes en los siguientes formatos:
- **PDF**.
- **Excel (XLSX)**.

2.2 El usuario debe poder seleccionar el formato de exportación antes de generar el archivo.

### 3. Respeto de filtros activos
3.1 El sistema debe generar los archivos exportados **respetando los filtros activos**, tales como:
- Departamento.
- Municipio.
- Componente (eje, medida, indicador).
- Periodo de tiempo.
- Estado de las acciones.

3.2 El contenido exportado debe coincidir con la información visualizada en pantalla.

### 4. Contenido del archivo exportado
4.1 El archivo exportado debe incluir:
- Título del reporte.
- Fecha de generación.
- Filtros aplicados.
- Información consolidada del reporte.

4.2 En el caso de PDF:
- El diseño debe ser legible y estructurado.
- Debe conservar la identidad visual institucional.

4.3 En el caso de Excel:
- La información debe presentarse en hojas organizadas.
- Los datos deben ser editables.

### 5. Generación y descarga del archivo
5.1 Al confirmar la exportación, el sistema debe generar el archivo automáticamente.  
5.2 El usuario debe poder descargar el archivo una vez finalizada la generación.  
5.3 El sistema debe mostrar mensajes claros durante el proceso (generando, listo, error).

### 6. Control de acceso y seguridad
6.1 El sistema debe garantizar que el usuario solo pueda exportar información autorizada.  
6.2 Los archivos generados no deben incluir información restringida.

### 7. Usabilidad y experiencia de usuario
7.1 El proceso de exportación debe ser sencillo e intuitivo.  
7.2 El sistema debe informar claramente el resultado de la exportación.  
7.3 El usuario debe poder repetir la exportación con diferentes filtros si lo requiere.

---

## Resultado esperado

El usuario puede **exportar los reportes del PIGCCT en formatos PDF y Excel**, obteniendo archivos que respetan los filtros activos y presentan información clara, estructurada y lista para su análisis, presentación o rendición de cuentas.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-190.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-190.png)


