# Épica: Navegación innovadora y experiencia de usuario

## 1. Descripción general
Esta épica define el **modelo de navegación y experiencia de usuario del sistema PIGCCT**, orientado a facilitar el acceso, la orientación y el uso eficiente de los módulos funcionales. Se basa en una navegación moderna y persistente, con componentes adaptativos que responden al contexto de uso, al rol del usuario y al tipo de información visualizada (formularios, visor geográfico, tableros).

El diseño prioriza la claridad, la reducción de carga cognitiva y la optimización del espacio de trabajo, especialmente en escenarios de análisis territorial y seguimiento.

## 2. Objetivo
Disponer de una experiencia de navegación intuitiva, consistente y adaptable que permita a los usuarios desplazarse de forma eficiente por el sistema, identificar su ubicación, acceder rápidamente a los módulos relevantes y maximizar el área útil de visualización según el contexto de uso.

## 3. Justificación / Valor de negocio
Una navegación innovadora:
- Reduce tiempos de aprendizaje y uso del sistema.
- Mejora la productividad de los usuarios operativos y validadores.
- Disminuye errores derivados de desorientación o accesos incorrectos.
- Facilita el trabajo con mapas, tableros y formularios complejos.
- Incrementa la adopción y aceptación institucional del sistema PIGCCT.
- Permite escalar el sistema sin perder coherencia en la experiencia.

## 4. Alcance
Incluye:
- Implementación de un sidebar principal persistente.
- Capacidad de colapsar el sidebar para optimizar el espacio visual.
- Panel contextual dinámico dependiente del módulo activo.
- Breadcrumb inteligente para navegación jerárquica.
- Adaptación de la navegación según rol y contexto.

No incluye:
- Definición de permisos y roles (cubierto en épicas de seguridad).
- Contenido funcional de los módulos.
- Reglas de negocio específicas de cada módulo.
- Diseño gráfico detallado (UI Kit).

## 5. Actores / Roles
- **Usuario registrador**: Navega entre acciones, formularios y seguimientos.
- **Usuario validador**: Accede a vistas de validación y análisis.
- **Usuario administrador**: Navega entre módulos de configuración.
- **Usuario consulta**: Accede a información validada y reportes.
- **Sistema**: Ajusta dinámicamente la navegación según rol y contexto.

## 6. Principios de diseño de la navegación
- Navegación persistente y predecible.
- Reducción de ruido visual.
- Prioridad al contenido principal (mapa, tablero, formulario).
- Adaptación al contexto del módulo activo.
- Consistencia visual y funcional en todo el sistema.
- Accesibilidad y claridad en los elementos de navegación.

## 7. Estructura general de la navegación
La navegación del sistema se compone de los siguientes elementos:

1. Sidebar principal persistente  
2. Sidebar colapsable (modo íconos)  
3. Panel contextual dinámico  
4. Breadcrumb inteligente  

Estos componentes trabajan de forma integrada para guiar al usuario y optimizar la experiencia.

## 8. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-202**:](/content/epicas/EP-PIGCCT-SYM-021/historias_usuario/HU-PIGCCT-SYM-202/HU-PIGCCT-SYM-202.md) Sidebar principal persistente  
- [**HU-PIGCCT-SYM-203**:](/content/epicas/EP-PIGCCT-SYM-021/historias_usuario/HU-PIGCCT-SYM-203/HU-PIGCCT-SYM-203.md) Sidebar colapsable  
- [**HU-PIGCCT-SYM-204**:](/content/epicas/EP-PIGCCT-SYM-021/historias_usuario/HU-PIGCCT-SYM-204/HU-PIGCCT-SYM-204.md) Panel contextual dinámico  
- [**HU-PIGCCT-SYM-205**:](/content/epicas/EP-PIGCCT-SYM-021/historias_usuario/HU-PIGCCT-SYM-205/HU-PIGCCT-SYM-205.md) Breadcrumb inteligente  

## 9. Reglas funcionales por componente

### Sidebar principal persistente
Permite acceder a los módulos principales del sistema en todo momento. El contenido del sidebar se adapta al rol del usuario y muestra únicamente las opciones permitidas.

### Sidebar colapsable
Permite contraer el sidebar a un modo de solo íconos, manteniendo tooltips informativos. Este modo prioriza el área de visualización del mapa, tableros y contenidos analíticos.

### Panel contextual dinámico
Muestra opciones, filtros o accesos secundarios según el módulo activo (por ejemplo: visor geográfico, tablero, formulario de acción), reduciendo la saturación del menú principal.

### Breadcrumb inteligente
Permite al usuario identificar claramente su ubicación dentro del sistema y navegar entre niveles jerárquicos (módulo → sección → elemento), manteniendo coherencia con el estado actual.

## 10. Criterios de éxito
- El usuario puede identificar fácilmente dónde se encuentra dentro del sistema.
- El acceso a los módulos es rápido y consistente.
- El espacio visual se optimiza según el contexto de uso.
- La navegación se adapta correctamente al rol del usuario.
- Se reduce la confusión y el número de acciones innecesarias.

## 11. Dependencias y supuestos
**Dependencias**
- Definición clara de roles y permisos.
- Estructura modular del sistema.
- Identificación de contextos de uso (mapa, tablero, formulario).

**Supuestos**
- Los usuarios interactúan frecuentemente con mapas y tableros.
- La navegación es transversal a todos los módulos.
- El breadcrumb refleja correctamente la jerarquía funcional.
- El sistema puede identificar el módulo activo en todo momento.

## 12. Riesgos
- Sobrecarga visual si no se controla el panel contextual.
- Inconsistencias entre navegación y permisos.
- Dificultad de adopción si el comportamiento no es predecible.
- Dependencia excesiva de estados dinámicos.
- Falta de claridad en el breadcrumb en flujos complejos.

## 13. Estado y seguimiento
- **Estado actual**: En definición 
- **Indicadores de seguimiento**:
  - Tiempo promedio de navegación entre módulos.
  - Número de accesos directos utilizados.
  - Tasa de uso del sidebar colapsado.
  - Incidencias relacionadas con desorientación del usuario.
