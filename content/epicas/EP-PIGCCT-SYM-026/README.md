# Épica: Usuario de consulta pública (sin autenticación)

## 1. Descripción general
Esta épica define el **rol de usuario de consulta pública del PIGCCT**, orientado a garantizar el acceso abierto, transparente y controlado a la información general del plan, sin requerir autenticación. Este rol permite a la ciudadanía, actores institucionales y partes interesadas consultar información validada, territorial y agregada, fortaleciendo la rendición de cuentas y la apropiación social del PIGCCT.

El acceso público se centra principalmente en el visor geográfico, las estadísticas territoriales generales y reportes públicos predefinidos, sin exponer información sensible ni habilitar acciones de modificación.

## 2. Objetivo
Garantizar el acceso público a información validada y agregada del PIGCCT, mediante un rol de consulta sin autenticación que permita visualizar el avance territorial del plan, fortaleciendo la transparencia y la difusión de resultados.

## 3. Justificación / Valor de negocio
El usuario de consulta pública:
- Fortalece la transparencia institucional.
- Facilita la rendición de cuentas a la ciudadanía.
- Promueve la apropiación social del PIGCCT.
- Reduce solicitudes manuales de información.
- Garantiza acceso controlado a información no sensible.
- Mejora la visibilidad del avance territorial del plan.

## 4. Alcance
Incluye:
- Acceso público al visor geográfico sin autenticación.
- Visualización de información validada y agregada.
- Consulta de estadísticas territoriales generales.
- Descarga de reportes públicos predefinidos.
- Restricción total de funcionalidades de edición o validación.

No incluye:
- Acceso a información administrativa o financiera.
- Visualización de datos en estado borrador o en validación.
- Creación, edición o validación de acciones.
- Acceso a tableros internos de control.
- Personalización avanzada de reportes.

## 5. Actores / Roles
- **Usuario de consulta pública**: Consulta información general del PIGCCT sin autenticación.
- **Sistema**: Aplica filtros de información pública, controla accesos y protege datos sensibles.
- **Usuario administrador**: Define qué información es pública y los reportes disponibles.

## 6. Principios de diseño del módulo
- Acceso abierto y sin barreras de autenticación.
- Información limitada a datos validados y agregados.
- Claridad y simplicidad en la presentación.
- Protección de información sensible.
- Consistencia con el visor y estadísticas institucionales.
- Experiencia de usuario intuitiva y liviana.

## 7. Estructura general del acceso público
El acceso para el usuario de consulta pública se organiza en:

1. Visor geográfico público  
2. Panel de filtros territoriales básicos  
3. Panel de información resumida  
4. Módulo de estadísticas territoriales públicas  
5. Sección de reportes públicos descargables  

## 8. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-229**: Acceso público al visor.](/content/epicas/EP-PIGCCT-SYM-026/historias_usuario/HU-PIGCCT-SYM-229/HU-PIGCCT-SYM-229.md)  
- [**HU-PIGCCT-SYM-230**: Información pública limitada.](/content/epicas/EP-PIGCCT-SYM-026/historias_usuario/HU-PIGCCT-SYM-230/HU-PIGCCT-SYM-230.md)  
- [**HU-PIGCCT-SYM-231**: Estadísticas públicas territoriales.](/content/epicas/EP-PIGCCT-SYM-026/historias_usuario/HU-PIGCCT-SYM-231/HU-PIGCCT-SYM-231.md)  
- [**HU-PIGCCT-SYM-232**: Reportes públicos.](/content/epicas/EP-PIGCCT-SYM-026/historias_usuario/HU-PIGCCT-SYM-232/HU-PIGCCT-SYM-232.md)  
- [**HU-PIGCCT-SYM-233**: Restricción de funcionalidades.](/content/epicas/EP-PIGCCT-SYM-026/historias_usuario/HU-PIGCCT-SYM-233/HU-PIGCCT-SYM-233.md)  
- **HU-PIGCCT-SYM-232**: Reportes públicos  
- **HU-PIGCCT-SYM-233**: Restricción de funcionalidades  

## 9. Reglas funcionales del módulo

### Acceso público
El sistema debe permitir el acceso al visor geográfico sin autenticación, garantizando disponibilidad continua y sin requerir credenciales.

### Información visible
Solo se debe mostrar información validada y agregada, excluyendo datos administrativos, financieros o sensibles.

### Estadísticas territoriales
Las estadísticas públicas deben presentarse a nivel municipal y departamental, utilizando indicadores generales de avance del PIGCCT.

### Reportes públicos
Los reportes disponibles para el usuario público deben ser predefinidos, estandarizados y orientados a divulgación y rendición de cuentas.

### Restricción de acciones
El usuario de consulta pública no debe tener acceso a funcionalidades de creación, edición, validación o descarga de información sensible.

## 10. Criterios de éxito
- El acceso público funciona sin autenticación.
- La información visible es clara, validada y no sensible.
- Las estadísticas públicas reflejan correctamente el avance territorial.
- Los reportes públicos son comprensibles y reutilizables.
- No existen brechas de seguridad ni exposición indebida de datos.

## 11. Dependencias y supuestos

**Dependencias**
- Definición clara de información pública vs. restringida.
- Integración con visor geográfico y estadísticas territoriales.
- Disponibilidad de datos validados.
- Configuración de reportes públicos.

**Supuestos**
- La información pública no requiere personalización avanzada.
- Los datos expuestos cumplen lineamientos de transparencia.
- El volumen de consultas públicas puede ser alto.
- El sistema maneja adecuadamente cargas sin autenticación.

## 12. Riesgos
- Exposición accidental de información sensible.
- Interpretación errónea de datos agregados.
- Sobrecarga del sistema por alto tráfico público.
- Desactualización de estadísticas públicas.
- Expectativas de acceso a información no disponible.

## 13. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de accesos públicos al visor.
  - Frecuencia de descarga de reportes públicos.
  - Uso de estadísticas territoriales públicas.
  - Retroalimentación ciudadana sobre claridad de la información.
  - Incidentes de seguridad o accesos no autorizados.
