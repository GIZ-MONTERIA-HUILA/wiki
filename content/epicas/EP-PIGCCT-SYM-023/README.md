# Épica: Estadísticas territoriales del PIGCCT

## 1. Descripción general
Esta épica define el **módulo de estadísticas territoriales del PIGCCT**, orientado a la consolidación, análisis y visualización agregada de la información de acciones e indicadores a nivel municipal y departamental. El módulo permite interpretar el avance, cobertura y enfoque estratégico del PIGCCT mediante métricas territoriales claras y visualizaciones gráficas interactivas.

Las estadísticas territoriales complementan el visor geográfico, proporcionando una capa analítica que facilita la evaluación del desempeño del plan y el seguimiento de su implementación en el territorio.

## 2. Objetivo
Proveer un conjunto de estadísticas territoriales consolidadas y visualmente comprensibles que permitan analizar el avance, distribución y enfoque estratégico del PIGCCT por municipio, departamento, eje y medida, apoyando la toma de decisiones y el seguimiento institucional.

## 3. Justificación / Valor de negocio
Las estadísticas territoriales:
- Permiten evaluar el desempeño del PIGCCT a nivel local y regional.
- Facilitan el seguimiento del avance proyectado versus ejecutado.
- Apoyan la priorización territorial de acciones.
- Mejoran la rendición de cuentas y la transparencia.
- Proveen insumos clave para reportes institucionales.
- Transforman datos operativos en información estratégica.

## 4. Alcance
Incluye:
- Estadísticas consolidadas por municipio.
- Estadísticas consolidadas por departamento.
- Indicadores agregados de avance territorial.
- Análisis territorial por eje estratégico y medida.
- Visualización gráfica interactiva de resultados.
- Uso de gráficos y mapas para facilitar la interpretación.

No incluye:
- Edición de datos estadísticos.
- Configuración avanzada de indicadores.
- Modelos predictivos o proyecciones.
- Descarga de bases de datos crudas.
- Análisis estadístico avanzado.

## 5. Actores / Roles
- **Usuario registrador**: Consulta estadísticas territoriales de interés.
- **Usuario validador**: Analiza desempeño territorial para procesos de revisión.
- **Usuario administrador**: Accede a vistas consolidadas y comparativas.
- **Usuario consulta**: Visualiza estadísticas agregadas y validadas.
- **Sistema**: Consolida datos, calcula indicadores y presenta visualizaciones.

## 6. Principios de diseño del módulo
- Enfoque en información agregada y validada.
- Claridad y simplicidad en las métricas.
- Visualizaciones intuitivas e interactivas.
- Comparabilidad entre territorios.
- Consistencia con estados de validación.
- Integración con otros módulos del sistema.

## 7. Estructura general del módulo
El módulo de estadísticas territoriales se organiza en:

1. Panel de selección territorial (municipio / departamento)  
2. Panel de filtros temáticos (eje, medida, indicador)  
3. Vista de estadísticas consolidadas  
4. Panel de visualización gráfica interactiva  
5. Mapas temáticos (coropléticos)  

## 8. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-215**:](/content/epicas/EP-PIGCCT-SYM-023/HU-PIGCCT-SYM-215/HU-PIGCCT-SYM-215.md) Estadísticas por municipio  
- [**HU-PIGCCT-SYM-216**:](/content/epicas/EP-PIGCCT-SYM-023/HU-PIGCCT-SYM-216/HU-PIGCCT-SYM-216.md) Estadísticas por departamento  
- [**HU-PIGCCT-SYM-217**:](/content/epicas/EP-PIGCCT-SYM-023/HU-PIGCCT-SYM-217/HU-PIGCCT-SYM-217.md) Indicadores de avance territorial  
- [**HU-PIGCCT-SYM-218**:](/content/epicas/EP-PIGCCT-SYM-023/HU-PIGCCT-SYM-218/HU-PIGCCT-SYM-218.md) Estadísticas por eje y medida  
- [**HU-PIGCCT-SYM-219**:](/content/epicas/EP-PIGCCT-SYM-023/HU-PIGCCT-SYM-219/HU-PIGCCT-SYM-219.md) Visualización gráfica interactiva  

## 9. Reglas funcionales del módulo

### Consolidación territorial
Las estadísticas se calculan a partir de información agregada de acciones e indicadores, agrupadas por municipio y departamento, considerando únicamente los registros permitidos según el rol del usuario.

### Indicadores de avance
El sistema debe calcular indicadores de avance territorial comparando valores proyectados frente a valores ejecutados, permitiendo evaluar el nivel de cumplimiento del PIGCCT.

### Agrupación estratégica
Las estadísticas pueden agruparse por eje estratégico y medida, permitiendo analizar el enfoque y distribución temática de las acciones en el territorio.

### Visualización interactiva
Las estadísticas se presentan mediante gráficos interactivos, tales como:
- Gráficos de barras.
- Gráficos circulares.
- Mapas coropléticos.

El usuario puede interactuar con las visualizaciones para explorar la información.

## 10. Criterios de éxito
- Las estadísticas reflejan correctamente la información territorial consolidada.
- Los indicadores de avance son claros y comparables.
- Las visualizaciones facilitan la interpretación de los datos.
- El módulo responde adecuadamente a filtros territoriales y temáticos.
- La información mostrada es consistente con el estado de validación.

## 11. Dependencias y supuestos
**Dependencias**
- Disponibilidad de datos consolidados de acciones e indicadores.
- Definición clara de indicadores de avance.
- Capas territoriales oficiales (municipios y departamentos).
- Integración con el modelo de validación.

**Supuestos**
- Los datos usados para estadísticas han pasado por procesos de validación.
- El módulo se usa principalmente para análisis y seguimiento.
- Las visualizaciones se mantienen consistentes en todo el sistema.
- El rendimiento es adecuado para consultas agregadas.

## 12. Riesgos
- Interpretaciones erróneas por mala visualización.
- Retrasos en la actualización de estadísticas.
- Inconsistencias entre datos operativos y agregados.
- Sobrecarga visual por exceso de gráficos.
- Dependencia de la calidad de los datos de origen.

## 13. Estado y seguimiento
- **Estado actual**: En definición 
- **Indicadores de seguimiento**:
  - Frecuencia de consulta de estadísticas territoriales.
  - Uso de visualizaciones interactivas.
  - Tiempo promedio de carga del módulo.
  - Observaciones de usuarios sobre claridad de la información.
