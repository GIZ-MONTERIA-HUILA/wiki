# Épica: Botones del formulario y comportamiento

## 1. Descripción general
Esta épica define el **comportamiento de los botones globales del formulario de registro de acciones del PIGCCT**, los cuales permiten al usuario gestionar el ciclo de vida de una acción de manera transversal, independientemente de la pestaña activa. Los botones facilitan el guardado progresivo, el envío a validación y la cancelación del proceso, garantizando control, trazabilidad y una experiencia de usuario consistente.

## 2. Objetivo
Permitir que el usuario registrador gestione el estado de una acción mediante botones globales visibles en todo el formulario, asegurando la posibilidad de guardar borradores, continuar la edición y enviar la información a validación cuando esté completa.

## 3. Justificación / Valor de negocio
La implementación de botones globales:
- Mejora la usabilidad y fluidez del formulario.
- Permite guardar avances parciales sin pérdida de información.
- Reduce errores y abandonos en el registro de acciones complejas.
- Facilita el control del flujo entre borrador y validación.
- Asegura trazabilidad mediante la generación controlada de eventos.

## 4. Alcance
Incluye:
- Visualización permanente de botones globales en el formulario.
- Gestión del botón **Guardar borrador**.
- Gestión del botón **Enviar a validación** (articulado con la épica de eventos).
- Gestión del botón **Cancelar**.
- Generación de eventos al guardar acciones.
- Control del estado **borrador** y sus reglas de edición.

No incluye:
- Las reglas de validación institucional (definidas en la épica de gestión de eventos).
- Confirmaciones visuales o mensajes de UX detallados.

## 5. Actores / Roles
- **Usuario registrador**: Guarda, edita y envía acciones a validación.
- **Usuario validador**: Consulta acciones enviadas a validación.
- **Sistema**: Controla estados, eventos y habilitación de edición.

## 6. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-144**: Visualizar botones globales del formulario.](/content/epicas/EP-PIGCCT-SYM-012/historias_usuario/HU-PIGCCT-SYM-144/HU-PIGCCT-SYM-144.md)  
- [**HU-PIGCCT-SYM-145**: Guardar acción como borrador.](/content/epicas/EP-PIGCCT-SYM-012/historias_usuario/HU-PIGCCT-SYM-145/HU-PIGCCT-SYM-145.md)  
- [**HU-PIGCCT-SYM-146**: Mantener edición habilitada en estado borrador.](/content/epicas/EP-PIGCCT-SYM-012/historias_usuario/HU-PIGCCT-SYM-146/HU-PIGCCT-SYM-146.md)

## 7. Botones del formulario

### 7.1 Guardar borrador
Permite:
- Guardar la acción en cualquier momento.
- Crear o actualizar el registro en la tabla **acción**.
- Generar un evento de tipo `create` o `update`.
- Mantener el evento sin fecha de envío.
- Conservar la acción en estado **borrador**.
- Permitir edición completa posterior.

### 7.2 Enviar a validación
Permite:
- Enviar la acción al flujo de validación institucional.
- Registrar la fecha de envío del evento.
- Cambiar el estado del registro para control de edición.
- Integrarse con la épica de **Gestión de eventos y validación**.

### 7.3 Cancelar
Permite:
- Salir del formulario sin enviar a validación.
- Mantener la información previamente guardada (si existe borrador).
- Evitar cambios no deseados durante el registro.

## 8. Criterios de éxito
- Los botones son visibles desde cualquier pestaña del formulario.
- El usuario puede guardar la acción sin completar todas las pestañas.
- Las acciones en estado borrador permanecen completamente editables.
- Cada guardado genera un evento correctamente trazable.
- El envío a validación solo ocurre cuando el usuario lo decide explícitamente.

## 9. Dependencias y supuestos
**Dependencias**
- Existencia del modelo de datos de acción.
- Definición de estados de la acción (borrador, enviado, validado).
- Integración con la épica de eventos y validación.

**Supuestos**
- El usuario comprende la diferencia entre guardar borrador y enviar a validación.
- El sistema controla correctamente los estados y permisos de edición.
- El evento sin fecha de envío no entra al flujo de validación.

## 10. Riesgos
- Confusión del usuario entre guardar y enviar a validación.
- Generación excesiva de eventos por guardados frecuentes.
- Pérdida de cambios si el usuario cancela sin guardar.
- Dependencia estricta del estado para el control de edición.

## 11. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de acciones guardadas como borrador.
  - Tiempo promedio entre creación y envío a validación.
  - Cantidad de ediciones realizadas antes del envío.
