# Épica: Estado y validación (visualización)

## 1. Descripción general
Esta épica define las funcionalidades de **visualización del estado de validación y de las observaciones asociadas a una acción del PIGCCT**, permitiendo a los usuarios conocer de forma clara y oportuna en qué etapa del proceso de validación se encuentra la información registrada y cuáles son los comentarios u observaciones realizados por los validadores institucionales.

## 2. Objetivo
Permitir que los usuarios del sistema, en especial el usuario registrador, puedan consultar el estado de validación de una acción y visualizar las observaciones emitidas durante el proceso, facilitando el seguimiento, la corrección de inconsistencias y la transparencia del flujo de validación.

## 3. Justificación / Valor de negocio
La visualización del estado y observaciones:
- Brinda claridad sobre el avance del proceso de validación.
- Reduce incertidumbre y reprocesos por falta de información.
- Facilita la corrección oportuna de acciones rechazadas.
- Mejora la comunicación entre registradores y validadores.
- Fortalece la transparencia y trazabilidad institucional.

## 4. Alcance
Incluye:
- Visualización del estado actual de validación de la acción.
- Consulta del historial de validaciones asociadas a la acción.
- Visualización de observaciones registradas por validadores.
- Diferenciación clara entre estados (borrador, enviado, rechazado, aprobado).
- Acceso controlado a la información según rol del usuario.

No incluye:
- La edición de observaciones por parte del registrador.
- La notificación automática de cambios de estado.
- La gestión del flujo de validación (definida en la épica de eventos).
- La modificación directa del estado de validación.

## 5. Actores / Roles
- **Usuario registrador**: Consulta el estado y revisa observaciones para corregir la acción.
- **Usuario validador**: Registra observaciones durante la validación.
- **Usuario consulta**: Visualiza únicamente acciones completamente validadas.
- **Sistema**: Presenta el estado y las observaciones de forma consistente y controlada.

## 6. Historias de usuario asociadas
- **HU-PIGCCT-SYM-157**: Visualizar estado de validación de la acción.  
- **HU-PIGCCT-SYM-158**: Visualizar observaciones de validación.

## 7. Visualización del estado y observaciones

### 7.1 Estado de validación de la acción
El sistema debe mostrar de forma clara:
- El estado actual de la acción (borrador, enviada, rechazada, aprobada).
- La entidad o rol que tiene la validación en curso.
- Las fechas clave del proceso (envío, validación, rechazo).
- El resultado final del proceso cuando aplique.

La información debe ser visible desde:
- El formulario de la acción.
- La vista de detalle o resumen de la acción.

### 7.2 Observaciones de validación
El sistema debe permitir al usuario registrador:
- Visualizar las observaciones emitidas por los validadores.
- Identificar quién realizó la observación (entidad / CAR).
- Conocer la fecha de la observación.
- Asociar claramente cada observación con el evento de validación correspondiente.

Las observaciones deben mostrarse en modo solo lectura y no ser editables por el registrador.

## 8. Criterios de éxito
- El estado de validación es visible en todo momento para los usuarios autorizados.
- Las observaciones de validación son claras y están correctamente asociadas.
- El usuario registrador puede identificar fácilmente si debe corregir la acción.
- No se muestran observaciones ni estados inconsistentes con el evento real.
- Los usuarios de consulta solo visualizan acciones completamente aprobadas.

## 9. Dependencias y supuestos
**Dependencias**
- Existencia del modelo de eventos y estados de validación.
- Registro adecuado de observaciones por parte de los validadores.
- Integración con la épica de gestión de eventos y validación.
- Control de visibilidad por rol.

**Supuestos**
- Cada rechazo incluye al menos una observación.
- Los estados de validación están correctamente sincronizados con los eventos.
- El usuario comprende el significado de cada estado.
- Las observaciones no se eliminan ni sobrescriben.

## 10. Riesgos
- Confusión del usuario si los estados no son claros o consistentes.
- Falta de observaciones detalladas que dificulten la corrección.
- Retrasos en el proceso por desconocimiento del estado actual.
- Problemas de sincronización entre eventos y visualización.

## 11. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de acciones rechazadas con observaciones visibles.
  - Tiempo promedio entre rechazo y corrección.
  - Cantidad de consultas al estado de validación por acción.
