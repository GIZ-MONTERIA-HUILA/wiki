# Épica: Visor geográfico del PIGCCT

## 1. Descripción general
Esta épica define el **visor geográfico del PIGCCT** como el componente espacial central para la consulta, análisis y visualización territorial de las acciones, indicadores y estadísticas del plan. El visor permite interpretar la información del PIGCCT desde una perspectiva geográfica, facilitando el análisis espacial, la focalización territorial y la toma de decisiones basada en el territorio.

El visor integra filtros temáticos, territoriales y de estado de validación, así como mecanismos de acceso contextual a la información detallada de las acciones.

## 2. Objetivo
Disponer de un visor geográfico interactivo que permita a los usuarios autorizados analizar y consultar las acciones del PIGCCT de manera territorial, asegurando claridad en la representación espacial, control de acceso según rol y coherencia con el estado de validación de la información.

## 3. Justificación / Valor de negocio
El visor geográfico:
- Facilita la comprensión territorial del PIGCCT.
- Permite identificar brechas, concentraciones y patrones espaciales.
- Apoya la toma de decisiones estratégicas y operativas.
- Mejora la transparencia y comunicación de la información.
- Integra análisis temáticos y territoriales en una sola vista.
- Fortalece el seguimiento y evaluación del impacto territorial de las acciones.

## 4. Alcance
Incluye:
- Acceso controlado al visor geográfico.
- Visualización espacial de acciones por municipio o cobertura departamental.
- Representación diferenciada de tipos de cobertura.
- Filtros territoriales, temáticos y por estado de validación.
- Visualización de información resumida en el mapa.
- Acceso contextual al detalle de las acciones.

No incluye:
- Edición geográfica directa de las acciones.
- Configuración avanzada de simbología.
- Análisis espacial avanzado (buffers, overlays).
- Generación de reportes cartográficos.
- Gestión de capas externas al PIGCCT.

## 5. Actores / Roles
- **Usuario registrador**: Consulta acciones propias y territoriales.
- **Usuario validador**: Analiza espacialmente acciones en proceso de validación.
- **Usuario administrador**: Accede a vistas consolidadas.
- **Usuario consulta**: Visualiza únicamente información validada.
- **Sistema**: Controla filtros, simbología y acceso según rol.

## 6. Principios de diseño del visor
- Enfoque en la claridad y legibilidad cartográfica.
- Simbología diferenciada según tipo de cobertura.
- Interacción simple e intuitiva.
- Filtros combinables y dinámicos.
- Integración fluida con otros módulos del sistema.
- Control de visibilidad según estado de validación y rol.

## 7. Estructura general del visor
El visor geográfico se compone de:

1. Mapa base interactivo  
2. Capas de acciones del PIGCCT  
3. Panel de filtros territoriales y temáticos  
4. Panel o popup de información resumida  
5. Accesos contextuales al detalle de la acción  

## 8. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-206:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-206/HU-PIGCCT-SYM-206.md) Acceso al visor geográfico  
- [**HU-PIGCCT-SYM-207:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-207/HU-PIGCCT-SYM-207.md) Visualizar acciones en el mapa  
- [**HU-PIGCCT-SYM-208:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-208/HU-PIGCCT-SYM-208.md) Representación diferenciada de cobertura  
- [**HU-PIGCCT-SYM-209:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-209/HU-PIGCCT-SYM-209.md) Filtrar acciones por departamento  
- [**HU-PIGCCT-SYM-210:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-210/HU-PIGCCT-SYM-210.md) Filtrar acciones por municipio  
- [**HU-PIGCCT-SYM-211:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-211/HU-PIGCCT-SYM-211.md) Filtrar acciones por eje, medida o indicador  
- [**HU-PIGCCT-SYM-212:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-212/HU-PIGCCT-SYM-212.md) Filtrar acciones por estado de validación  
- [**HU-PIGCCT-SYM-213:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-213/HU-PIGCCT-SYM-213.md) Visualizar información resumida en el mapa  
- [**HU-PIGCCT-SYM-214:**](/content/epicas/EP-PIGCCT-SYM-022/historias_usuario/HU-PIGCCT-SYM-214/HU-PIGCCT-SYM-214.md) Acceder al detalle de la acción desde el visor  

## 9. Reglas funcionales del visor

### Acceso y visibilidad
El acceso al visor y la información visible dependen del rol del usuario y del estado de validación de las acciones, garantizando que solo información permitida sea consultada.

### Representación espacial
Las acciones se representan según su cobertura territorial:
- Cobertura departamental.
- Cobertura municipal específica.

La simbología debe permitir distinguir claramente ambos tipos.

### Filtros territoriales y temáticos
El usuario puede aplicar filtros combinados por:
- Departamento.
- Municipio.
- Eje estratégico.
- Medida.
- Indicador.
- Estado de validación.

### Información contextual
Al seleccionar una acción en el mapa, el sistema muestra información clave resumida y permite, según permisos, acceder al detalle administrativo y de seguimiento.

## 10. Criterios de éxito
- El visor permite identificar claramente la distribución territorial de las acciones.
- Los filtros funcionan de forma combinada y coherente.
- La simbología diferencia correctamente los tipos de cobertura.
- La información mostrada es consistente con el estado de validación.
- El acceso al detalle de la acción es claro y controlado.

## 11. Dependencias y supuestos
**Dependencias**
- Disponibilidad de capas territoriales oficiales.
- Modelo de datos espacial de las acciones.
- Definición de estados de validación y roles.

**Supuestos**
- Las acciones cuentan con información territorial válida.
- El visor es principalmente de consulta y análisis.
- Los usuarios utilizan el visor como apoyo a decisiones.
- La información geográfica se mantiene actualizada.

## 12. Riesgos
- Sobrecarga visual por exceso de capas o simbología.
- Inconsistencias entre filtros y estados de validación.
- Rendimiento limitado con grandes volúmenes de datos.
- Confusión del usuario si la simbología no es clara.
- Dependencia de la calidad de los datos territoriales.

## 13. Estado y seguimiento
- **Estado actual**: En definición 
- **Indicadores de seguimiento**:
  - Número de consultas realizadas en el visor.
  - Uso de filtros territoriales y temáticos.
  - Tiempo promedio de interacción en el visor.
  - Incidencias reportadas relacionadas con visualización geográfica.
