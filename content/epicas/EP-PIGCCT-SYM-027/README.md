# Épica: Detalle funcional del visor geográfico del PIGCCT

## 1. Descripción general
Esta épica define el **detalle funcional del visor geográfico del PIGCCT**, como el componente central de análisis territorial del sistema. El visor permite visualizar, explorar y analizar las acciones del PIGCCT sobre el territorio mediante capas geográficas, simbología dinámica, filtros avanzados e interacción directa con mapas y tableros.

El visor integra información espacial, estadística y de validación, proporcionando una experiencia de análisis geográfico coherente, interactiva y alineada con los procesos de seguimiento del PIGCCT.

## 2. Objetivo
Disponer de un visor geográfico robusto e interactivo que permita a los usuarios analizar territorialmente las acciones, indicadores y avances del PIGCCT, integrando mapas, filtros, simbología y tableros para apoyar la toma de decisiones y el seguimiento institucional.

## 3. Justificación / Valor de negocio
El visor geográfico:
- Facilita la comprensión territorial del PIGCCT.
- Permite identificar patrones espaciales y brechas territoriales.
- Integra información geográfica y estadística en un solo entorno.
- Mejora el análisis por estado de validación, eje y medida.
- Apoya procesos de planificación, seguimiento y rendición de cuentas.
- Incrementa el valor analítico de la información registrada en el sistema.

## 4. Alcance
Incluye:
- Inicialización y carga contextual del visor.
- Selección dinámica del PIGCCT activo.
- Visualización de capas base y capas temáticas.
- Representación espacial de acciones.
- Control de visibilidad de capas.
- Simbología dinámica por estado, eje o medida.
- Mapas coropléticos.
- Interacción directa con entidades geográficas.
- Sincronización entre mapa y tableros.
- Filtros territoriales y temporales avanzados.

No incluye:
- Edición directa de geometrías.
- Análisis geoespacial avanzado (buffer, intersecciones).
- Descarga de capas geográficas crudas.
- Configuración técnica de servicios GIS.
- Administración de catálogos territoriales.

## 5. Actores / Roles
- **Usuario registrador**: Consulta y analiza acciones en el territorio.
- **Usuario validador**: Analiza espacialmente acciones para procesos de revisión.
- **Usuario administrador**: Supervisa información territorial consolidada.
- **Usuario consulta**: Visualiza información territorial validada.
- **Sistema**: Carga capas, aplica filtros, sincroniza visualizaciones y controla accesos.

## 6. Principios de diseño del visor
- Contextualización territorial inmediata.
- Interacción directa e intuitiva con el mapa.
- Visualización clara y consistente.
- Integración mapa–tablero.
- Simbología significativa y configurable.
- Rendimiento adecuado para grandes volúmenes de datos.
- Coherencia con estados de validación y roles.

## 7. Estructura general del visor
El visor geográfico se organiza en:

1. Vista inicial y selección de PIGCCT activo  
2. Panel de capas (base y temáticas)  
3. Área principal de mapa interactivo  
4. Panel de simbología y visualización  
5. Panel de filtros avanzados  
6. Popup informativo  
7. Panel lateral de detalle territorial  
8. Integración con tableros y gráficos  

## 8. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-234**: Carga inicial del visor.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-234/HU-PIGCCT-SYM-234.md)  
- [**HU-PIGCCT-SYM-235**: Selección de PIGCCT activo.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-235/HU-PIGCCT-SYM-235.md)    
- [**HU-PIGCCT-SYM-236**: Visualizar capas base.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-236/HU-PIGCCT-SYM-236.md)    
- [**HU-PIGCCT-SYM-237**: Visualizar capa de municipios.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-237/HU-PIGCCT-SYM-237.md)   
- [**HU-PIGCCT-SYM-238**: Visualizar capa de acciones.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-238/HU-PIGCCT-SYM-238.md)    
- [**HU-PIGCCT-SYM-239**: Control de visibilidad de capas.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-239/HU-PIGCCT-SYM-239.md)    
- [**HU-PIGCCT-SYM-240**: Simbología por estado de validación.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-240/HU-PIGCCT-SYM-240.md)    
- [**HU-PIGCCT-SYM-241**: Simbología por eje o medida.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-241/HU-PIGCCT-SYM-241.md)    
- [**HU-PIGCCT-SYM-242**: Mapas coropléticos.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-242/HU-PIGCCT-SYM-242.md)   
- [**HU-PIGCCT-SYM-243**: Seleccionar entidad geográfica.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-243/HU-PIGCCT-SYM-243.md)    
- [**HU-PIGCCT-SYM-244**: Popup informativo.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-244/HU-PIGCCT-SYM-244.md)  
- [**HU-PIGCCT-SYM-245**: Panel de detalle territorial.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-245/HU-PIGCCT-SYM-245.md)    
- [**HU-PIGCCT-SYM-246**: Sincronización mapa–tablero.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-246/HU-PIGCCT-SYM-246.md)    
- [**HU-PIGCCT-SYM-247**: Filtros territoriales combinados.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-247/HU-PIGCCT-SYM-247.md)    
- [**HU-PIGCCT-SYM-248**: Filtros por rango temporal.](/content/epicas/EP-PIGCCT-SYM-027/historias_usuario/HU-PIGCCT-SYM-248/HU-PIGCCT-SYM-248.md)    

## 9. Reglas funcionales del visor

### Inicialización
El visor debe cargarse con una vista inicial centrada en el departamento del PIGCCT activo, asegurando una contextualización territorial inmediata.

### Capas geográficas
El sistema debe permitir gestionar capas base y temáticas, habilitando o deshabilitando su visualización según las necesidades del usuario.

### Representación y simbología
Las acciones deben representarse mediante simbología configurable, diferenciando estados de validación, ejes, medidas o niveles de intensidad territorial.

### Interacción
El usuario puede seleccionar municipios o acciones directamente en el mapa, accediendo a información resumida y a paneles de detalle territorial.

### Integración analítica
Las selecciones realizadas en el mapa deben reflejarse automáticamente en gráficos y tablas asociadas, garantizando un análisis integrado.

### Filtros avanzados
El visor debe permitir aplicar filtros combinados territoriales, temáticos y temporales, actualizando dinámicamente las capas visibles y la información asociada.

## 10. Criterios de éxito
- El visor carga correctamente y de forma contextual.
- Las capas se visualizan de manera clara y consistente.
- La simbología es comprensible y configurable.
- La interacción con el mapa es fluida e intuitiva.
- La sincronización mapa–tablero funciona correctamente.
- Los filtros actualizan la visualización sin inconsistencias.

## 11. Dependencias y supuestos

**Dependencias**
- Disponibilidad de servicios geográficos y capas oficiales.
- Definición de simbología y reglas de visualización.
- Integración con datos validados del PIGCCT.
- Infraestructura GIS con buen rendimiento.

**Supuestos**
- Las geometrías territoriales están actualizadas.
- El visor es un componente transversal del sistema.
- Los usuarios tienen conocimientos básicos de lectura cartográfica.
- La información espacial se mantiene sincronizada con los datos alfanuméricos.

## 12. Riesgos
- Problemas de rendimiento con grandes volúmenes de datos.
- Sobrecarga visual por exceso de capas o simbología.
- Interpretación incorrecta de mapas coropléticos.
- Dependencia de servicios GIS externos.
- Inconsistencias entre mapa y datos tabulares.

## 13. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Uso del visor geográfico.
  - Tiempo promedio de carga del mapa.
  - Frecuencia de uso de filtros avanzados.
  - Interacciones mapa–tablero realizadas.
  - Retroalimentación de usuarios sobre usabilidad.
