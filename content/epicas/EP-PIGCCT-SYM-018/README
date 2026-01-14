# Épica: Consistencia entre acción y relaciones

## 1. Descripción general
Esta épica define las **reglas de consistencia entre la acción del PIGCCT y sus entidades relacionadas** (indicadores, seguimientos y adjuntos), garantizando que el proceso de envío a validación sea coherente, completo y trazable. Busca evitar que una acción sea validada mientras existan cambios pendientes en sus relaciones, y asegurar que cualquier modificación posterior reactive el ciclo de validación.

## 2. Objetivo
Garantizar que una acción solo pueda enviarse a validación cuando todas sus relaciones estén en un estado consistente, y que cualquier cambio posterior en la acción o en sus entidades relacionadas obligue a una nueva validación institucional.

## 3. Justificación / Valor de negocio
La consistencia entre acción y relaciones:
- Evita validaciones parciales o incoherentes.
- Garantiza que los validadores revisen siempre información completa y actualizada.
- Refuerza la trazabilidad de cambios posteriores a una validación.
- Reduce riesgos de uso de información desactualizada en reportes.
- Aumenta la confianza institucional en los datos del PIGCCT.

## 4. Alcance
Incluye:
- Validación de eventos pendientes antes del envío a validación de una acción.
- Verificación de consistencia entre la acción y sus tablas relacionadas.
- Reversión automática del estado de validación ante nuevos cambios.
- Control del estado derivado cuando se generan nuevos eventos.
- Integración con las reglas de eventos y estados derivados.

No incluye:
- La generación de eventos (definida en la épica de gestión de eventos).
- El flujo de validación institucional (definido en la épica de envío a validación).
- La visualización del estado (definida en la épica de estado y validación).

## 5. Actores / Roles
- **Usuario registrador**: Realiza cambios en la acción y sus relaciones.
- **Usuario validador**: Valida acciones coherentes y completas.
- **Sistema**: Verifica consistencia, controla estados y revierte validaciones cuando aplica.

## 6. Historias de usuario asociadas
- **HU-PIGCCT-SYM-161**: Validar consistencia antes del envío.  
- **HU-PIGCCT-SYM-162**: Revertir estado de validación ante cambios.

## 7. Reglas de consistencia antes del envío a validación
Antes de permitir el envío de una acción a validación, el sistema debe verificar que:

- No existan eventos pendientes de envío en:
  - acción
  - indicador_accion
  - indicador_accion_valor
  - adjuntos
- Todos los eventos relacionados pertenezcan a la misma acción.
- No existan eventos en estado borrador asociados a la acción.
- La información relacionada refleje el último estado guardado.

Si alguna de estas condiciones no se cumple, el sistema debe:
- Bloquear el envío a validación.
- Informar claramente que existen cambios pendientes en las relaciones.

## 8. Reglas de reversión del estado de validación
El sistema debe aplicar las siguientes reglas:

- Si una acción o cualquiera de sus relaciones genera un nuevo evento (`create` o `update`):
  - El estado derivado de la acción pasa automáticamente a **pendiente de validación**.
  - Se invalida la validación previa (sin borrar el historial).
  - El nuevo evento debe completar nuevamente el flujo de validación.

- Esta regla aplica a cambios en:
  - La acción.
  - Indicadores asociados.
  - Registros de seguimiento.
  - Adjuntos.

## 9. Criterios de éxito
- Ninguna acción puede enviarse a validación con eventos pendientes.
- Cualquier cambio posterior reactiva automáticamente el ciclo de validación.
- El estado derivado refleja correctamente la consistencia real del registro.
- No se pierde el historial de validaciones previas.
- Los validadores siempre revisan información actualizada.

## 10. Dependencias y supuestos
**Dependencias**
- Modelo de eventos implementado y funcional.
- Reglas de estado derivado definidas.
- Integración con épicas de envío a validación y bloqueo de edición.

**Supuestos**
- Todo cambio relevante genera un evento.
- Los eventos son la fuente de verdad para el control de consistencia.
- No se permiten ediciones silenciosas sin evento.
- El estado físico (si existe) se sincroniza con el estado derivado.

## 11. Riesgos
- Generación excesiva de eventos por cambios menores.
- Reprocesos frecuentes de validación por ajustes pequeños.
- Complejidad en la verificación de consistencia.
- Confusión del usuario si no se comunica claramente el motivo del bloqueo.
- Dependencia crítica de la correcta gestión de eventos.

## 12. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de envíos a validación bloqueados por inconsistencias.
  - Cantidad de reversiones de estado por cambios posteriores.
  - Tiempo promedio entre modificación y reenvío a validación.
