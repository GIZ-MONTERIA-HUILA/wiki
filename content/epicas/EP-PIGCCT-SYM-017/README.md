# Épica: Reglas de estado derivado

## 1. Descripción general
Esta épica define las **reglas para la determinación del estado de una acción del PIGCCT a partir de los eventos de validación**, estableciendo un estado derivado que refleja de manera fiel el avance real del proceso institucional. El estado de la acción no se gestiona de forma manual, sino que se calcula con base en los eventos registrados, garantizando coherencia, trazabilidad y control de visibilidad de la información.

## 2. Objetivo
Permitir que el sistema determine automáticamente el estado de cada acción a partir de los eventos asociados, y controle la visibilidad y uso de la información según el nivel de validación alcanzado, evitando inconsistencias y uso de datos no aprobados.

## 3. Justificación / Valor de negocio
La gestión de estados derivados:
- Elimina ambigüedades entre el estado real y el estado visual de una acción.
- Garantiza que solo información validada sea utilizada para análisis y reportes.
- Simplifica el control del flujo de validación.
- Refuerza la trazabilidad institucional del PIGCCT.
- Reduce errores derivados de cambios manuales de estado.

## 4. Alcance
Incluye:
- Cálculo del estado de la acción a partir de los eventos asociados.
- Definición de estados derivados normalizados.
- Uso opcional de un campo físico de estado para optimización.
- Control de visibilidad de acciones y relaciones según validación.
- Aplicación de reglas de visibilidad a acciones, indicadores, seguimientos y adjuntos.

No incluye:
- La generación de eventos de validación (definida en la épica de gestión de eventos).
- La visualización detallada del estado (definida en la épica de estado y validación).
- La modificación manual del estado por parte de los usuarios.

## 5. Actores / Roles
- **Sistema**: Calcula el estado derivado y controla la visibilidad.
- **Usuario registrador**: Consulta el estado derivado de sus acciones.
- **Usuario validador**: Incide en el estado mediante la validación o rechazo de eventos.
- **Usuario consulta**: Accede únicamente a acciones completamente validadas.

## 6. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-159**: Calcular estado de la acción desde eventos.](/content/epicas/EP-PIGCCT-SYM-017/historias_usuario/HU-PIGCCT-SYM-159/HU-PIGCCT-SYM-159.md)  
- [**HU-PIGCCT-SYM-160**: Controlar visibilidad según validación.](/content/epicas/EP-PIGCCT-SYM-017/historias_usuario/HU-PIGCCT-SYM-160/HU-PIGCCT-SYM-160.md)

## 7. Estados derivados de la acción
El sistema debe determinar el estado de la acción con base en los eventos asociados, considerando los siguientes estados derivados:

- **Borrador**  
  La acción tiene eventos creados o actualizados sin fecha de envío a validación.

- **En validación**  
  Existen eventos enviados a validación que aún no han sido aprobados o rechazados.

- **Validado por entidad**  
  Los eventos han sido aprobados por la entidad, pero no por la CAR.

- **Validado por CAR**  
  Todos los eventos asociados han sido aprobados por la CAR.  
  Este estado equivale a una acción completamente validada.

- **Rechazado**  
  Al menos un evento ha sido rechazado y requiere corrección.

El estado derivado debe recalcularse automáticamente ante cualquier cambio en los eventos.

## 8. Reglas de visibilidad según validación
El sistema debe aplicar las siguientes reglas:

- Una acción y sus relaciones (indicadores, seguimientos, adjuntos) son **visibles y utilizables** solo si:
  - Validado por entidad = true **y**
  - Validado por CAR = true

- Los usuarios registradores y validadores pueden visualizar:
  - Sus propios registros en estado borrador o en validación.
  - Registros rechazados con observaciones.

- Los usuarios de consulta solo pueden visualizar:
  - Acciones y relaciones completamente validadas.

## 9. Criterios de éxito
- El estado derivado refleja correctamente la situación real de la acción.
- No existen discrepancias entre eventos y estado mostrado.
- La visibilidad de información se controla estrictamente por validación.
- Las acciones rechazadas se identifican claramente.
- El estado se actualiza automáticamente ante cambios en eventos.

## 10. Dependencias y supuestos
**Dependencias**
- Existencia del modelo de eventos y campos de validación.
- Integración con las épicas de envío a validación, bloqueo de edición y visualización.
- Reglas claras de aprobación por entidad y CAR.

**Supuestos**
- Todos los cambios relevantes generan eventos.
- No se permiten validaciones parciales inconsistentes.
- El campo físico de estado (si existe) se sincroniza con el estado derivado.
- Los eventos son la fuente de verdad del estado.

## 11. Riesgos
- Desincronización entre eventos y campo físico de estado.
- Complejidad excesiva en el cálculo del estado derivado.
- Errores de visibilidad que expongan información no validada.
- Dependencia fuerte de la correcta generación de eventos.

## 12. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Porcentaje de acciones en cada estado derivado.
  - Número de inconsistencias detectadas entre eventos y estado.
  - Tiempo promedio por estado del flujo de validación.
