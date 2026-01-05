[Inicio](/README.md)

# Proceso General del Módulo de Restauración SNIF – Descripción del Flujo BPMN

En el diagrama en mención, se utiliza un modelado y notación de procesos de negocio, o diagrama BPMN (Business Process Model and Notation), que se utiliza para crear diagramas de flujo de modelos de procesos de negocio fáciles de leer, que se puedan compartir en distintas industrias y organizaciones. A continuación, se describen los elementos gráficos utilizados en el Diagrama de procesos del "nuevo" módulo de restauración del SNIF.

El proceso general del **Módulo de Restauración SNIF** abarca la gestión integral de proyectos y áreas restauradas, desde el acceso y autenticación hasta la validación final y la consulta/exportación de datos, integrando funcionalidades SIG, gestión documental, reportes y control de calidad.

<img src="assets/bpmn.png" class="zoomable" />

## 1. Acceso y Autenticación

- El usuario accede a la plataforma IDEAM (vía enlace institucional o URL directa).
- Se despliega el formulario de inicio de sesión, donde ingresa sus credenciales.
- El sistema valida las credenciales (**Keycloak/LDAP**), registra el acceso y muestra la pantalla de bienvenida con ayuda contextual.
- Si la autenticación falla, se notifica al usuario y se registra el intento en los logs.

---

## 2. Navegación y Gestión de Proyectos

- Tras autenticarse, el usuario navega por el menú principal.
- Según su rol (**Administrador**, **Editor**, **Consulta**), puede crear, editar o solo visualizar proyectos.
- Al crear/editar un proyecto, se diligencia un formulario con validaciones automáticas (campos obligatorios, formatos, unicidad).
- Al guardar, el sistema valida los datos, genera identificadores automáticos y habilita pestañas adicionales:
  - Fuentes de financiación
  - Adjuntos
  - Áreas restauradas

---

## 3. Gestión de Fuentes de Financiación y Adjuntos

- El usuario puede agregar, editar o eliminar fuentes de financiación asociadas al proyecto.
- Puede cargar, descargar o eliminar adjuntos (documentos o archivos geográficos), con validaciones de tipo y tamaño.
- El sistema almacena los archivos, registra metadatos y logs de cada acción.

---

## 4. Gestión y Caracterización de Áreas Restauradas

- El usuario selecciona un proyecto y accede a la gestión de áreas restauradas.
- Puede cargar archivos geográficos (**Shapefile**, **KML**, **GeoJSON**) para registrar áreas (polígonos/multipolígonos).
- El sistema valida formato, topología y proyección, realiza intersecciones espaciales automáticas con capas de referencia (municipios, veredas, áreas protegidas, etc.) y almacena atributos espaciales y temáticos.
- El usuario puede visualizar, editar o eliminar áreas restauradas, así como registrar información detallada en pestañas especializadas:
  - Acciones implementadas
  - Técnicas de restauración
  - Indicadores de monitoreo
  - Disturbios/motores de degradación
  - Estrategias de restauración
  - Divulgación comunitaria
  - **Gestión de especies:** registro de especies asociadas, procedencia, técnica, área cubierta
  - Adjuntos (documentos y archivos geográficos asociados al área)

---

## 5. Consultas y Visualización SIG

- El usuario accede al visor geográfico integrado (**SIG**), con herramientas de navegación, zoom, medición, identificación y control de capas.
- Puede realizar consultas:
  - **Atributivas:** filtrar elementos por valores de campos.
  - **Espaciales:** dibujar geometrías (punto, línea, polígono) y buscar elementos que intersecten, contengan o estén contenidos.
  - **Por coordenada:** ingresar coordenadas y buscar elementos cercanos (buffer configurable).
  - **Por capa geográfica:** importar una capa poligonal para delimitar la consulta.
- Los resultados se visualizan en el mapa y en tablas, con opción de centrar, ver detalle y exportar.

---

## 6. Exportación y Descarga de Datos

- El usuario puede exportar resultados de consultas o capas completas en formatos soportados (**GeoJSON**, **Shapefile**, **Excel**, **KML**), con reproyección automática a **EPSG:4326**.
- El sistema valida permisos, limita el volumen de datos y registra cada exportación en los logs.

---

## 7. Integración con Reportes y Power BI

- Los usuarios con permisos pueden acceder al módulo de administración de reportes.
- Se gestionan reportes **Power BI** asociados a grupos temáticos, con metadatos y control de acceso.
- Los reportes activos están disponibles para consulta y visualización embebida o en nueva pestaña.

---

## 8. Validación Jerárquica de Registros

- Todo registro creado inicia con estado `UNDER_REVISION`.
- **Validación de Entidad:**
  - Un revisor institucional revisa los registros, puede aprobarlos o devolverlos con observaciones.
  - Si se aprueba, el registro pasa a estado `UNDER_REVISION_IDEAM`.
- **Validación IDEAM:**
  - Un validador designado por IDEAM revisa los registros, puede aprobarlos o devolverlos.
  - Si se aprueba, el registro pasa a estado `VALIDATED` y queda disponible para consulta y reportes.
- Todo el ciclo de validación, observaciones y cambios de estado queda registrado en logs de auditoría.

---

## 9. Cierre de Sesión y Seguridad

- El usuario puede cerrar sesión desde el menú de usuario.
- El sistema invalida la sesión, registra el evento y notifica al usuario.
- Se garantiza que no se pueda acceder a funcionalidades protegidas tras el cierre.

---

## Resumen de Roles y Permisos

| Rol                   | Descripción                                                                     |
| --------------------- | ------------------------------------------------------------------------------- |
| **Administrador**     | Acceso total a todas las funcionalidades, gestión de usuarios, reportes y logs. |
| **Editor**            | Puede crear, editar y eliminar proyectos, áreas, especies y adjuntos.           |
| **Validador Entidad** | Revisa y valida registros de su entidad.                                        |
| **Validador IDEAM**   | Revisa y valida registros a nivel nacional.                                     |
| **Consulta**          | Solo puede visualizar y exportar datos.                                         |

---

## Puntos Clave del Proceso

- Validaciones automáticas y jerárquicas en cada etapa para garantizar integridad y calidad de los datos.
- Registro detallado de todas las acciones en logs de auditoría.
- Gestión centralizada de archivos y adjuntos, con controles de seguridad y trazabilidad.
- Interfaz SIG avanzada para navegación, consulta y exportación de datos espaciales.
- Integración con reportes Power BI y gestión temática.
- Flujos jerárquicos de validación para asegurar la aprobación institucional y nacional.
- Interfaz dinámica y adaptativa según el rol y permisos del usuario.

---

> **Conclusión:**  
> Este flujo asegura la trazabilidad, control y validación de la información de restauración ecológica, alineado con los requerimientos técnicos y normativos del **SNIF** y el **IDEAM**.
