# HU-PIGCCT-SYM-123  
## Épica: Gestión de eventos y validación de información del PIGCCT  
### Validar evento por la CAR

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario validador de la CAR (Corporación Autónoma Regional).  
> **Quiero:** poder validar o rechazar eventos previamente aprobados por la entidad.  
> **Para:** realizar el control regional y garantizar la calidad final de la información del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de validación CAR
1.1 El sistema debe permitir el acceso a la funcionalidad de validación únicamente a usuarios con rol de **"validador CAR"**.  
1.2 La opción de validación CAR debe estar disponible desde el módulo de validación o gestión de eventos.  
1.3 El validador CAR debe poder ver únicamente eventos que hayan sido previamente validados por la entidad.

### 2. Condición previa para validación CAR
2.1 El sistema debe validar que el evento cumpla con la condición:
- **validado_por_entidad = true**

2.2 Si un evento no ha sido validado por la entidad, el sistema **no debe permitir** que el validador CAR lo valide.  
2.3 Debe mostrarse un mensaje claro si el validador CAR intenta acceder a un evento que no cumple esta condición.

### 3. Visualización de eventos pendientes de validación CAR
3.1 El sistema debe mostrar una lista de eventos pendientes de validación CAR, con información relevante:
- Identificador del evento
- Tipo de afectación (create/update)
- Tabla y objeto afectado
- Usuario que creó el registro
- Fecha de creación y envío
- Validador de entidad que aprobó
- Fecha de validación por entidad
- Observaciones de la entidad (si existen)
- Estado actual

3.2 La lista debe ser filtrable por entidad, tabla, fecha, tipo de afectación, etc.

### 4. Revisión detallada del evento
4.1 El validador CAR debe poder seleccionar un evento para ver su información completa.  
4.2 El sistema debe mostrar:
- **Para eventos tipo create**: El contenido completo del registro nuevo.
- **Para eventos tipo update**: Comparación clara entre valor_anterior y valor_nuevo.
- **Contexto del registro**: Información de la acción asociada y otros datos relevantes.
- **Historial de validación**: Quién aprobó en la entidad y cuándo, con observaciones.

4.3 El validador CAR debe poder ver la decisión y observaciones del validador de entidad.

### 5. Opciones de validación CAR
5.1 El validador CAR debe tener dos opciones principales:
- **Aprobar** el evento
- **Rechazar** el evento

5.2 Ambas opciones deben requerir confirmación antes de ejecutarse.

### 6. Proceso de aprobación por CAR
6.1 Al aprobar un evento, el sistema debe actualizar los siguientes campos:
- **validado_por_car**: Establecer en **true**.
- **fch_validacion_car**: Fecha y hora de la validación por CAR.
- **estado_registro**: Cambiar a **"completamente validado"** o **"aprobado"**.

6.2 El validador CAR puede opcionalmente agregar observaciones complementarias en el campo **observacion** (sin sobrescribir las observaciones de la entidad).

6.3 El sistema debe aplicar definitivamente los cambios del evento al registro principal, haciéndolo visible y usable en el sistema.

### 7. Proceso de rechazo por CAR
7.1 Al rechazar un evento, el sistema debe:
- **validado_por_car**: Establecer en **false**.
- **fch_validacion_car**: Fecha y hora del rechazo.
- **estado_registro**: Cambiar a **"rechazado por CAR"**.
- **observacion**: **Obligatorio** - el validador CAR debe proporcionar una razón detallada del rechazo.

7.2 El sistema debe notificar:
- Al usuario que creó el registro
- Al validador de la entidad
- Informando sobre el rechazo y la razón

7.3 El evento rechazado por CAR debe devolverse al estado que permita correcciones (determinado por la política institucional).

### 8. Validación de permisos regionales
8.1 El sistema debe validar que el usuario validador CAR tenga permisos para validar eventos de las entidades bajo su jurisdicción regional.  
8.2 Un validador CAR de una región **no debe poder validar** eventos de entidades de otra región (si aplica esta restricción).

### 9. Registro de observaciones CAR
9.1 Las observaciones del validador CAR deben almacenarse sin eliminar las observaciones previas del validador de entidad.  
9.2 El sistema debe mantener un historial completo de observaciones de ambos niveles de validación.  
9.3 Formato sugerido: Concatenar con identificación clara del validador y fecha.

### 10. Notificaciones
10.1 Al aprobar un evento, el sistema debe notificar:
- Al usuario creador: informando que su registro ha sido completamente validado y está activo.
- Al validador de entidad: como información de cierre exitoso del proceso.

10.2 Al rechazar un evento, el sistema debe notificar:
- Al usuario creador: con las razones del rechazo y pasos a seguir.
- Al validador de entidad: informando sobre el rechazo para su conocimiento.

### 11. Trazabilidad
11.1 El sistema debe registrar en logs:
- Usuario validador CAR
- Acción realizada (aprobar/rechazar)
- Fecha y hora
- Identificador del evento
- Estado anterior y nuevo
- Observaciones registradas

### 12. Restricciones
12.1 El sistema **no debe permitir** validar eventos que ya hayan sido validados previamente por la CAR.  
12.2 Solo eventos en estado **"validado por entidad - pendiente CAR"** deben ser validables por la CAR.  
12.3 El sistema debe bloquear la validación CAR si validado_por_entidad ≠ true.

### 13. Impacto en la visibilidad del registro
13.1 Cuando el validador CAR aprueba el evento:
- El registro asociado debe volverse **completamente visible y usable** en el sistema.
- Debe estar disponible para reportes, consultas y análisis.
- La condición de visibilidad completa debe ser: validado_por_entidad = true AND validado_por_car = true.

13.2 Cuando el validador CAR rechaza el evento:
- El registro debe mantenerse oculto o marcado como "no validado".
- No debe incluirse en reportes oficiales o consultas públicas.

### 14. Validación masiva CAR
14.1 Opcionalmente, el sistema puede permitir aprobar múltiples eventos en una operación (útil para validaciones de lotes consistentes).  
14.2 El rechazo masivo debe permitir aplicar una observación general a todos los eventos seleccionados.

---

### Resultado esperado

Un **evento validado o rechazado correctamente** por el validador CAR, con los campos validado_por_car, fch_validacion_car, estado_registro y observacion actualizados apropiadamente, completando el proceso de validación de dos niveles y determinando la visibilidad final y usabilidad del registro en el sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-123.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-123.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-123.png)
