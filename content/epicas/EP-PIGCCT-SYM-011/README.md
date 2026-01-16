# Épica: Estructura y navegación del formulario de acciones

## 1. Descripción general
Esta épica define la **estructura, organización y navegación del formulario de registro de acciones del PIGCCT**, mediante un esquema guiado por pestañas que permite diligenciar la información de forma progresiva, ordenada y controlada. El diseño del formulario responde al estado de la acción y al rol del usuario, garantizando coherencia en el flujo de registro y evitando inconsistencias en la información.

## 2. Objetivo
Proporcionar un formulario de acciones estructurado por pestañas, que guíe al usuario en el registro de la información, habilitando secciones de manera progresiva según el estado de la acción y asegurando la correcta creación de relaciones con indicadores, adjuntos y procesos de validación.

## 3. Justificación / Valor de negocio
La estructuración del formulario:
- Mejora la usabilidad y experiencia del usuario registrador.
- Reduce errores en el diligenciamiento de la información.
- Garantiza que las relaciones se creen solo cuando exista una acción válida.
- Facilita el control del flujo de información según el ciclo de vida de la acción.
- Asegura coherencia entre registro, seguimiento y validación.

## 4. Alcance
Incluye:
- Visualización del formulario de acciones organizado por pestañas.
- Control de pestañas visibles según el estado de la acción.
- Visualización inicial limitada a pestañas básicas al crear una acción.
- Habilitación progresiva de pestañas de relaciones y validación.
- Restricción de navegación según reglas de negocio y rol del usuario.

No incluye:
- El diseño gráfico detallado de la interfaz.
- Reglas específicas de validación de contenido de cada campo (definidas en otras épicas).

## 5. Actores / Roles
- **Usuario registrador**: Diligencia la información de la acción.
- **Usuario validador**: Consulta la información registrada para su validación.
- **Administrador del sistema**: Configura parámetros generales del sistema.
- **Sistema**: Controla la navegación, visibilidad y habilitación de pestañas.

## 6. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-141**: Visualizar formulario guiado por pestañas.](/content/epicas/EP-PIGCCT-SYM-011/historias_usuario/HU-PIGCCT-SYM-141/HU-PIGCCT-SYM-141.md)  
- [**HU-PIGCCT-SYM-142**: Visualizar pestañas iniciales al crear una acción.](/content/epicas/EP-PIGCCT-SYM-011/historias_usuario/HU-PIGCCT-SYM-142/HU-PIGCCT-SYM-142.md)  
- [**HU-PIGCCT-SYM-143**: Habilitar pestañas de relaciones después de guardar la acción.](/content/epicas/EP-PIGCCT-SYM-011/historias_usuario/HU-PIGCCT-SYM-143/HU-PIGCCT-SYM-143.md)

## 7. Estructura de pestañas del formulario

### 7.1 Pestañas visibles al crear la acción
Disponibles únicamente durante el registro inicial:
- **Información general**
- **Territorio**
- **Articulación con el plan**
- **Programación y seguimiento**

### 7.2 Pestañas habilitadas después de guardar
Se habilitan solo cuando la acción ya existe en el sistema (tiene identificador válido):
- **Indicadores asociados**
- **Adjuntos**
- **Estado y validación**

## 8. Criterios de éxito
- El usuario solo visualiza las pestañas permitidas según el estado de la acción.
- No es posible asociar indicadores o adjuntos sin una acción previamente creada.
- El flujo de navegación es claro y consistente para el usuario.
- Se reduce la probabilidad de registros incompletos o inconsistentes.
- La estructura del formulario soporta correctamente el proceso de validación.

## 9. Dependencias y supuestos
**Dependencias**
- Existencia del modelo de datos de acción.
- Definición de estados de la acción y reglas de validación.
- Integración con las épicas de indicadores, adjuntos y validación de eventos.

**Supuestos**
- Los usuarios registradores siguen el flujo definido por el sistema.
- El estado de la acción controla correctamente la habilitación de pestañas.
- El formulario se usa principalmente en procesos secuenciales de registro.

## 10. Riesgos
- Confusión del usuario si no se comunica claramente el estado de la acción.
- Intentos de navegación forzada a pestañas no habilitadas.
- Cambios futuros en el flujo del formulario que requieran ajustes de lógica.
- Dependencia excesiva del estado de la acción para la experiencia de usuario.

## 11. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de acciones creadas correctamente en el primer intento.
  - Cantidad de errores por navegación indebida.
  - Tiempo promedio de diligenciamiento del formulario.
