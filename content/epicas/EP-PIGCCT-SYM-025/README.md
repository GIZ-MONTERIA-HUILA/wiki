# Épica: Reportes y tableros de control del PIGCCT

## 1. Descripción general
Esta épica define el **módulo de reportes y tableros de control del PIGCCT**, orientado a la visualización sintética, el monitoreo permanente y la generación de reportes institucionales a partir de la información de acciones, indicadores y estados de validación.

El módulo integra tableros de control interactivos y capacidades de generación de reportes descargables, permitiendo transformar la información operativa y territorial en insumos claros para el seguimiento, la toma de decisiones y la rendición de cuentas del PIGCCT.

## 2. Objetivo
Proveer tableros de control y reportes estructurados que permitan monitorear el estado del PIGCCT, analizar avances territoriales y generar documentos formales para seguimiento institucional, garantizando control de acceso según el rol del usuario.

## 3. Justificación / Valor de negocio
Los reportes y tableros de control:
- Facilitan el monitoreo integral del PIGCCT.
- Centralizan información clave en vistas ejecutivas.
- Apoyan la toma de decisiones estratégicas.
- Fortalecen la rendición de cuentas y la transparencia.
- Permiten documentar avances territoriales de forma estandarizada.
- Reducen reprocesos en la elaboración manual de informes.

## 4. Alcance
Incluye:
- Tablero de control general del PIGCCT.
- Visualización de estados de acciones, indicadores y validaciones.
- Generación de reportes descargables (PDF, Excel).
- Generación de reportes desde tableros de control.
- Generación de reportes territoriales desde el visor geográfico.
- Reportes comparativos entre municipios y departamentos.
- Control de acceso a reportes según rol.

No incluye:
- Edición de datos desde los tableros.
- Configuración avanzada de métricas por el usuario final.
- Reportes predictivos o analítica avanzada.
- Diseño personalizado de plantillas por usuario.
- Automatización de envíos programados de reportes.

## 5. Actores / Roles
- **Usuario registrador**: Consulta tableros y reportes permitidos.
- **Usuario validador**: Analiza avances y estados para procesos de revisión.
- **Usuario administrador**: Accede a tableros completos y reportes consolidados.
- **Usuario consulta**: Visualiza información agregada autorizada.
- **Sistema**: Consolida información, aplica filtros y genera reportes.

## 6. Principios de diseño del módulo
- Información sintética y orientada a la toma de decisiones.
- Visualizaciones claras y consistentes.
- Reportes estandarizados y reproducibles.
- Integración con visor geográfico y estadísticas territoriales.
- Control de acceso basado en roles.
- Coherencia con estados de validación del sistema.

## 7. Estructura general del módulo
El módulo de reportes y tableros de control se organiza en:

1. Tablero de control general del PIGCCT  
2. Panel de indicadores clave (acciones, indicadores, validaciones)  
3. Filtros territoriales y temáticos  
4. Generación de reportes desde tableros  
5. Generación de reportes desde el visor geográfico  
6. Reportes comparativos territoriales  

## 8. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-224**: Tablero de control general.](/content/epicas/EP-PIGCCT-SYM-025/historias_usuario/HU-PIGCCT-SYM-224/HU-PIGCCT-SYM-224.md)  
- [**HU-PIGCCT-SYM-225**: Reportes desde tableros.](/content/epicas/EP-PIGCCT-SYM-025/historias_usuario/HU-PIGCCT-SYM-225/HU-PIGCCT-SYM-225.md)  
- [**HU-PIGCCT-SYM-226**: Reportes desde el visor geográfico.](/content/epicas/EP-PIGCCT-SYM-025/historias_usuario/HU-PIGCCT-SYM-226/HU-PIGCCT-SYM-226.md)  
- [**HU-PIGCCT-SYM-227**: Reportes comparativos territoriales.](/content/epicas/EP-PIGCCT-SYM-025/historias_usuario/HU-PIGCCT-SYM-227/HU-PIGCCT-SYM-227.md)  
- [**HU-PIGCCT-SYM-228**: Control de acceso a reportes.](/content/epicas/EP-PIGCCT-SYM-025/historias_usuario/HU-PIGCCT-SYM-228/HU-PIGCCT-SYM-228.md)  

## 9. Reglas funcionales del módulo

### Tablero de control general
El sistema debe presentar un tablero con indicadores clave del PIGCCT, mostrando el estado de las acciones, indicadores asociados y procesos de validación de manera consolidada.

### Generación de reportes
Los reportes deben generarse a partir de la información visible en los tableros y el visor, manteniendo coherencia entre lo visualizado y lo descargado.

### Reportes territoriales
El sistema debe permitir generar reportes específicos por municipio o departamento, directamente desde el visor geográfico, respetando los filtros activos.

### Reportes comparativos
Los reportes comparativos deben permitir analizar diferencias y avances entre territorios, utilizando criterios homogéneos y comparables.

### Control de acceso
La generación y descarga de reportes debe estar restringida según el rol del usuario y el nivel de información autorizado.

## 10. Criterios de éxito
- El tablero de control presenta información clara y actualizada.
- Los reportes reflejan fielmente la información del sistema.
- Los usuarios pueden generar reportes según su rol.
- Los reportes territoriales y comparativos son comprensibles.
- El módulo responde adecuadamente a filtros y consultas.

## 11. Dependencias y supuestos

**Dependencias**
- Disponibilidad de información consolidada de acciones e indicadores.
- Definición de indicadores clave del PIGCCT.
- Integración con visor geográfico y módulo estadístico.
- Definición clara de roles y permisos.

**Supuestos**
- La información usada en reportes ha sido validada.
- Los tableros son el principal medio de monitoreo.
- Los formatos de reporte cumplen lineamientos institucionales.
- El rendimiento del sistema es adecuado para consultas agregadas.

## 12. Riesgos
- Sobrecarga de información en los tableros.
- Retrasos en la actualización de datos.
- Interpretaciones erróneas de indicadores.
- Uso indebido de reportes sin contexto.
- Dependencia de la calidad de los datos de origen.

## 13. Estado y seguimiento
- **Estado actual**: En definición 
- **Indicadores de seguimiento**:
  - Frecuencia de uso del tablero de control.
  - Número de reportes generados por tipo.
  - Tiempo promedio de generación de reportes.
  - Retroalimentación de usuarios sobre utilidad de los tableros.
  - Uso de reportes en procesos institucionales.
