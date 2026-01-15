# HU-PIGCCT-SYM-157  
## Épica: Estado y validación (visualización)  
### Visualizar estado de validación de la acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (registrador, validador o administrador).  
> **Quiero:** visualizar el estado de validación de una acción.  
> **Para:** conocer en qué etapa del proceso se encuentra y qué acciones están pendientes.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Estados posibles de validación
1.1 El sistema debe manejar y mostrar los siguientes estados de validación:
- **BORRADOR**: Acción en proceso de creación, no enviada
- **EN_VALIDACION_ENTIDAD**: Enviada, esperando revisión de validadores de entidad
- **VALIDADO_ENTIDAD**: Aprobada por entidad, pendiente de validación CAR
- **EN_VALIDACION_CAR**: Enviada a CAR, esperando revisión
- **VALIDADO_CAR**: Completamente validada y aprobada
- **RECHAZADO**: Rechazada, requiere correcciones
- **CANCELADO**: Acción cancelada (opcional)

1.2 Cada estado debe tener una representación visual clara y distintiva.

### 2. Indicador visual en el formulario
2.1 Al abrir una acción, debe mostrarse prominentemente el estado actual en el encabezado del formulario.  
2.2 El indicador debe incluir:
- Badge o etiqueta con el nombre del estado
- Color distintivo según el estado:
  - **Gris**: Borrador
  - **Amarillo/ámbar**: En validación
  - **Verde**: Validado
  - **Rojo**: Rechazado
  - **Azul**: Cancelado
- Ícono representativo del estado

2.3 El indicador debe ser visible en todas las pestañas del formulario.

### 3. Información de fechas clave
3.1 Junto al estado, mostrar fechas relevantes según el estado actual:
- **Borrador**: "Última actualización: [fecha]"
- **En validación**: "Enviado el: [fecha]"
- **Validado**: "Validado el: [fecha]"
- **Rechazado**: "Rechazado el: [fecha]"

3.2 Las fechas ayudan a entender la antigüedad del estado actual.

### 4. Línea de tiempo de validación
4.1 El sistema debe proporcionar una **línea de tiempo visual** que muestre el progreso:
```
Creación → Envío a entidad → Validación entidad → Envío a CAR → Validación CAR
   ✓            ✓                  [En proceso]          ⏳              ⏳
```

4.2 Indicar:
- Etapas completadas (✓ verde)
- Etapa actual (color destacado)
- Etapas pendientes (gris o icono de reloj)

4.3 Si fue rechazada, mostrar el punto de rechazo con ícono de advertencia.

### 5. Detalle del estado actual
5.1 Expandir información sobre el estado actual:
- **En validación por entidad**:
  - "Tu acción está siendo revisada por [nombre de la entidad]"
  - "Validadores notificados: [cantidad]"
  - "Tiempo en validación: [X días]"
  
- **Validado por entidad**:
  - "Validado por: [nombre del validador]"
  - "Fecha de validación: [fecha]"
  - "Pendiente: Envío a CAR"

- **Rechazado**:
  - "Rechazado por: [nombre del validador]"
  - "Fecha de rechazo: [fecha]"
  - "Motivo: Ver observaciones"
  - Botón: "Ver observaciones completas"

5.2 Proporcionar contexto completo sobre el estado.

### 6. Indicador en listado de acciones
6.1 En el listado de acciones, cada acción debe mostrar su estado:
- Columna "Estado" con badge de color
- Ordenamiento por estado disponible
- Filtrado por estado: "Mostrar solo borradores", "Mostrar solo en validación", etc.

6.2 El usuario debe poder identificar rápidamente el estado de múltiples acciones.

### 7. Contador de tiempo en estado
7.1 Para estados activos (en validación), mostrar cuánto tiempo lleva en ese estado:
- "En validación desde hace 3 días"
- "Esperando respuesta hace 1 semana"

7.2 Esto ayuda a identificar acciones estancadas o que requieren seguimiento.

### 8. Historial completo de estados
8.1 Proporcionar un historial detallado de cambios de estado:
```
Historial de estados:
- 15/01/2026 10:30 - Creada por Juan Pérez
- 16/01/2026 14:20 - Enviada a validación por Juan Pérez
- 17/01/2026 09:15 - Rechazada por María García
  Motivo: "Falta información de presupuesto"
- 17/01/2026 16:00 - Corregida por Juan Pérez
- 17/01/2026 16:05 - Reenviada a validación
- 18/01/2026 11:00 - Validada por entidad - Pedro López
- 18/01/2026 11:05 - Enviada a CAR
```

8.2 Cada entrada debe incluir: fecha/hora, acción realizada, usuario responsable.

### 9. Notificaciones de cambio de estado
9.1 Al cambiar el estado de una acción, notificar a los usuarios relevantes:
- **Enviada**: Notificar a validadores
- **Validada**: Notificar al registrador
- **Rechazada**: Notificar al registrador con observaciones
- **Enviada a CAR**: Notificar a validadores CAR

9.2 Las notificaciones deben incluir el nuevo estado y enlace a la acción.

### 10. Dashboard de estados
10.1 Proporcionar un dashboard con resumen de estados:
```
Mis acciones:
- 3 Borradores
- 5 En validación por entidad
- 2 Validadas
- 1 Rechazada (requiere atención)
- 10 Validadas completamente
```

10.2 Cada categoría debe ser clickeable para ver las acciones correspondientes.

### 11. Estados por validación de componentes
11.1 Opcionalmente, mostrar estado de validación granular:
- **Acción principal**: ✓ Validada
- **Indicadores**: ✓ Validados (3/3)
- **Adjuntos**: ⚠️ Pendiente (2/5 validados)
- **Valores de seguimiento**: ✓ Validados

11.2 Esto proporciona visibilidad detallada del progreso de validación.

### 12. Permisos de visualización
12.1 Los diferentes roles deben ver información apropiada:
- **Registrador**: Ve sus propias acciones y estados
- **Validador entidad**: Ve acciones pendientes de validación de su entidad
- **Validador CAR**: Ve acciones pendientes de validación CAR
- **Administrador**: Ve todas las acciones y estados

12.2 El sistema debe filtrar la información según el rol del usuario.

### 13. Exportación de reporte de estados
13.1 Permitir exportar un reporte con estados de acciones:
- Formato Excel o PDF
- Incluye: ID, nombre, estado, fechas clave, responsable
- Filtrable por entidad, fecha, estado

13.2 Útil para seguimiento y reportes gerenciales.

### 14. API para consulta de estado
14.1 Proporcionar endpoint API para consultar estado:
```
GET /api/acciones/{id}/estado
Response:
{
  "accion_id": 123,
  "estado_actual": "EN_VALIDACION_ENTIDAD",
  "fecha_estado": "2026-01-15T10:30:00Z",
  "responsable_actual": "Validadores de Entidad X",
  "historial": [...],
  "siguiente_accion": "Esperar validación"
}
```

14.2 Permite integraciones con otros sistemas.

### 15. Accesibilidad de estados
15.1 Los indicadores de estado deben ser accesibles:
- No depender solo del color (incluir texto e íconos)
- Atributos ARIA apropiados: `role="status"`, `aria-label="Estado: En validación"`
- Lectores de pantalla deben anunciar cambios de estado

15.2 Usuarios con discapacidad visual deben entender el estado claramente.

---

### Resultado esperado

Una **visualización clara y completa del estado de validación** de cada acción, con indicadores visuales distintivos por estado, línea de tiempo de progreso, información sobre responsables de la siguiente acción, historial completo de cambios, alertas de tiempos excedidos, y un dashboard general que permite a cada usuario entender rápidamente en qué etapa se encuentran sus acciones y qué acciones requieren atención.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-157.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-157.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-157.png)
