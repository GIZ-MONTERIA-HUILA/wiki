# Épica: Envío a validación

## 1. Descripción general
Esta épica define el **proceso de envío de una acción del PIGCCT al flujo de validación institucional**, asegurando que la información registrada esté completa, consistente y acompañada de todos los elementos asociados (indicadores, seguimientos y adjuntos). El envío marca el cierre del trabajo en estado borrador y el inicio formal de la revisión por parte de los roles validadores.

## 2. Objetivo
Permitir que el usuario registrador envíe una acción completa a validación, garantizando el cumplimiento de reglas mínimas de calidad de la información y asegurando que todos los eventos relacionados ingresen de manera conjunta y trazable al proceso de validación.

## 3. Justificación / Valor de negocio
El envío controlado a validación:
- Garantiza que solo acciones completas entren al proceso institucional.
- Reduce reprocesos por información incompleta o inconsistente.
- Asegura una revisión integral de la acción y sus componentes.
- Mantiene trazabilidad clara del momento y responsable del envío.
- Facilita la gestión ordenada de los flujos de validación.

## 4. Alcance
Incluye:
- Validación previa de campos obligatorios antes del envío.
- Verificación de la existencia de al menos un indicador asociado.
- Validación de valores proyectados diligenciados.
- Envío conjunto de todos los eventos relacionados con la acción.
- Marcado de eventos como enviados a validación.
- Registro de usuario y fecha de envío.

No incluye:
- La decisión de aprobación o rechazo.
- Las reglas detalladas de validación técnica o institucional.
- El retorno de observaciones o ajustes posteriores.
- La notificación a los validadores (cubierta en otra épica).

## 5. Actores / Roles
- **Usuario registrador**: Envía la acción a validación.
- **Usuario validador**: Recibe y revisa la información enviada.
- **Sistema**: Verifica condiciones, actualiza estados y registra eventos.

## 6. Historias de usuario asociadas
- **HU-PIGCCT-SYM-151**: Enviar acción completa a validación.  
- **HU-PIGCCT-SYM-152**: Enviar a validación todos los eventos asociados.  
- **HU-PIGCCT-SYM-153**: Marcar eventos como enviados.

## 7. Reglas del envío a validación

### 7.1 Validaciones previas al envío
El sistema debe verificar que:
- Todos los campos obligatorios de la acción estén diligenciados.
- Exista al menos un indicador asociado a la acción.
- Los valores proyectados de los indicadores estén completos.
- No existan inconsistencias críticas en la información registrada.

Si alguna condición no se cumple, el envío se bloquea y se informa al usuario.

### 7.2 Envío integral de la acción
Al enviar a validación:
- La acción pasa del estado **borrador** a **enviada a validación**.
- Se incluyen todos los elementos relacionados a la acción.
- El envío se realiza como una operación lógica única.

### 7.3 Envío de eventos asociados
Se envían a validación los eventos correspondientes a:
- Acción.
- Indicadores asociados.
- Registros de seguimiento.
- Adjuntos.

Todos los eventos quedan vinculados al mismo proceso de validación.

### 7.4 Marcado de eventos como enviados
El sistema debe:
- Registrar la fecha de envío del evento.
- Registrar el usuario que realizó el envío.
- Marcar el evento como **enviado a validación**.
- Impedir modificaciones posteriores, salvo que el flujo lo permita explícitamente.

## 8. Criterios de éxito
- No es posible enviar una acción incompleta a validación.
- El envío incluye todos los eventos relacionados.
- Los eventos enviados quedan correctamente marcados y trazables.
- El usuario queda identificado como responsable del envío.
- La acción entra formalmente al flujo de validación institucional.

## 9. Dependencias y supuestos
**Dependencias**
- Definición de campos obligatorios de la acción.
- Existencia del modelo de indicadores y valores proyectados.
- Integración con la épica de gestión de eventos y validación.
- Control de estados de la acción.

**Supuestos**
- El usuario registrador conoce cuándo la acción está lista para validación.
- El sistema impide ediciones posteriores al envío, según reglas definidas.
- Todos los eventos en borrador pueden ser enviados de forma conjunta.

## 10. Riesgos
- Envío de información incompleta si fallan las validaciones previas.
- Bloqueo del flujo si algún evento asociado queda inconsistente.
- Confusión del usuario sobre qué elementos se envían a validación.
- Dependencia fuerte de la correcta generación de eventos previos.

## 11. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de acciones enviadas a validación.
  - Porcentaje de acciones rechazadas por información incompleta.
  - Tiempo promedio entre creación y envío a validación.
  - Número de eventos asociados por acción enviada.
