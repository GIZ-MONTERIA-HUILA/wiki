# Épica: Bloqueo y control de edición

## 1. Descripción general
Esta épica define las **reglas de bloqueo y habilitación de edición de las acciones del PIGCCT**, una vez han sido enviadas al proceso de validación. Su objetivo es preservar la integridad de la información validada o en proceso de revisión, permitiendo modificaciones únicamente cuando exista un rechazo formal y sea necesario corregir observaciones realizadas por los validadores.

## 2. Objetivo
Garantizar que las acciones enviadas a validación no puedan ser modificadas de forma directa, habilitando la edición solo bajo condiciones controladas (rechazo del evento) y asegurando que cualquier corrección genere un nuevo evento que reinicie el ciclo de validación.

## 3. Justificación / Valor de negocio
El control estricto de la edición:
- Preserva la integridad y confiabilidad de la información enviada a validación.
- Evita cambios no auditados durante el proceso de revisión.
- Garantiza trazabilidad completa de correcciones y ajustes.
- Permite un flujo ordenado de observaciones y subsanaciones.
- Refuerza la transparencia del proceso de validación institucional.

## 4. Alcance
Incluye:
- Bloqueo automático de la edición tras el envío a validación.
- Habilitación de edición únicamente cuando el evento es rechazado.
- Generación de nuevos eventos al corregir una acción rechazada.
- Reinicio del ciclo de validación tras una corrección.

No incluye:
- Las reglas de rechazo y observaciones de los validadores.
- El proceso de aprobación final.
- La notificación de rechazo o aprobación al usuario registrador.
- Cambios directos sobre eventos ya validados.

## 5. Actores / Roles
- **Usuario registrador**: Corrige la acción cuando ha sido rechazada.
- **Usuario validador**: Rechaza acciones y emite observaciones.
- **Sistema**: Controla estados, bloqueos de edición y generación de eventos.

## 6. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-154**: Bloquear edición tras envío a validación.](/content/epicas/EP-PIGCCT-SYM-015/historias_usuario/HU-PIGCCT-SYM-154/HU-PIGCCT-SYM-154.md)  
- [**HU-PIGCCT-SYM-155**: Permitir edición solo si el evento es rechazado.](/content/epicas/EP-PIGCCT-SYM-015/historias_usuario/HU-PIGCCT-SYM-155/HU-PIGCCT-SYM-155.md)  
- [**HU-PIGCCT-SYM-156**: Generar nuevo evento al corregir una acción.](/content/epicas/EP-PIGCCT-SYM-015/historias_usuario/HU-PIGCCT-SYM-156/HU-PIGCCT-SYM-156.md)

## 7. Reglas de bloqueo y edición

### 7.1 Bloqueo de edición tras envío
Cuando una acción es enviada a validación:
- El sistema bloquea toda edición directa de la acción.
- Las pestañas del formulario quedan en modo solo lectura.
- No se permite modificar indicadores, seguimientos ni adjuntos.
- La acción permanece bloqueada mientras el evento esté en estado pendiente o aprobado.

### 7.2 Habilitación de edición por rechazo
El sistema habilita nuevamente la edición únicamente si:
- El evento asociado a la acción ha sido marcado como **rechazado**.
- Existen observaciones registradas por el validador.
- El usuario que edita es el registrador autorizado.

En este estado:
- La acción vuelve a estado **editable**.
- El usuario puede corregir la información observada.

### 7.3 Corrección y generación de nuevo evento
Al guardar una acción corregida:
- El sistema genera un nuevo evento de tipo `update`.
- El nuevo evento registra los valores corregidos.
- El evento anterior permanece como histórico.
- El ciclo de validación se reinicia para la acción corregida.

## 8. Criterios de éxito
- No es posible editar acciones enviadas a validación.
- La edición solo se habilita tras un rechazo formal.
- Cada corrección genera un nuevo evento trazable.
- Se conserva el historial completo de versiones y validaciones.
- El flujo de validación se reinicia correctamente tras la corrección.

## 9. Dependencias y supuestos
**Dependencias**
- Definición clara de estados del evento (enviado, rechazado, aprobado).
- Integración con la épica de gestión de eventos y validación.
- Control de permisos por rol.
- Modelo de auditoría y trazabilidad.

**Supuestos**
- El rechazo siempre incluye observaciones claras.
- El usuario registrador corrige exclusivamente lo observado.
- El sistema no permite sobrescribir eventos anteriores.
- Cada ciclo de validación es independiente y auditable.

## 10. Riesgos
- Bloqueo indebido de edición por errores de estado.
- Confusión del usuario sobre cuándo puede volver a editar.
- Generación excesiva de eventos por correcciones menores.
- Dependencia estricta de la correcta gestión de estados del evento.

## 11. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de acciones bloqueadas tras envío.
  - Cantidad de acciones rechazadas y corregidas.
  - Número promedio de ciclos de validación por acción.
  - Tiempo promedio entre rechazo y reenvío a validación.
