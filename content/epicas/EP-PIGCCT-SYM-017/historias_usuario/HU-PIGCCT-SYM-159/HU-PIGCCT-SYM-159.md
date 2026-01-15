# HU-PIGCCT-SYM-159  
## Épica: Reglas de estado derivado  
### Calcular estado de la acción desde eventos

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión de eventos.  
> **Quiero:** determinar el estado de una acción a partir de sus eventos.  
> **Para:** mantener trazabilidad completa y poder calcular el estado actual basándome en el historial de eventos registrados.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Estados derivados del sistema
1.1 El sistema debe manejar los siguientes estados derivados para las acciones:
- **BORRADOR**: Acción creada pero no enviada a validación
- **EN_VALIDACION_ENTIDAD**: Enviada, esperando aprobación de validadores de entidad
- **VALIDADO_ENTIDAD**: Aprobada por entidad, pendiente de envío a CAR
- **EN_VALIDACION_CAR**: Enviada a CAR, esperando aprobación
- **VALIDADO_CAR**: Completamente validada y aprobada
- **RECHAZADO**: Rechazada en cualquier etapa de validación

1.2 Estos estados pueden calcularse desde los eventos o almacenarse físicamente.

### 2. Campo físico de estado
2.1 La tabla `accion` debe tener un campo `estado_accion` que almacena el estado actual:
- Tipo: `VARCHAR` o `ENUM`
- Valores: Los estados listados en el punto 1.1
- NOT NULL con valor por defecto: 'BORRADOR'

2.2 Este campo se actualiza cada vez que ocurre un cambio de estado.

### 3. Cálculo de estado desde eventos
3.1 Opcionalmente, el sistema puede calcular el estado actual analizando los eventos más recientes de la acción.

3.2 El evento más reciente determina el estado:
- Evento con `estado_registro = 'en_validacion_entidad'` → Estado: EN_VALIDACION_ENTIDAD
- Evento con `estado_registro = 'validado_entidad'` → Estado: VALIDADO_ENTIDAD
- Evento con `estado_registro = 'rechazado'` → Estado: RECHAZADO

### 4. Sincronización entre campo y eventos
4.1 El campo físico `estado_accion` debe mantenerse sincronizado con los eventos.  
4.2 Cada vez que se genera un evento que cambia el estado, actualizar el campo:
```javascript
// Al generar evento
await crearEvento({
  tipo_evento: 'update',
  estado_registro: 'en_validacion_entidad',
  // ... otros campos
});

// Actualizar estado físico
await actualizarAccion({
  estado_accion: 'EN_VALIDACION_ENTIDAD'
});
```

4.3 Ambas operaciones deben ejecutarse en la misma transacción.

### 5. Regla: Estado BORRADOR
5.1 Una acción está en estado **BORRADOR** cuando:
- Ha sido creada (`tipo_evento = 'create'`)
- NO tiene fecha de envío a validación (`fch_envio_validacion IS NULL`)
- El evento más reciente tiene `estado_registro = 'borrador'` o NULL

5.2 El usuario puede editar libremente en este estado.

### 6. Regla: Estado EN_VALIDACION_ENTIDAD
6.1 Una acción está en **EN_VALIDACION_ENTIDAD** cuando:
- Tiene fecha de envío a validación (`fch_envio_validacion IS NOT NULL`)
- El evento de la acción tiene `estado_registro = 'en_validacion_entidad'`
- NO ha sido validada ni rechazada aún

6.2 La acción está bloqueada para edición en este estado.

### 7. Regla: Estado VALIDADO_ENTIDAD
7.1 Una acción está en **VALIDADO_ENTIDAD** cuando:
- Un validador de entidad la aprobó
- Existe un evento con `tipo_evento = 'validacion_entidad'` y `estado_registro = 'validado_entidad'`
- Fecha de validación por entidad existe (`fch_validacion_entidad IS NOT NULL`)

7.2 La acción está lista para envío a CAR pero aún no ha sido enviada.

### 8. Regla: Estado EN_VALIDACION_CAR
8.1 Una acción está en **EN_VALIDACION_CAR** cuando:
- Ha sido validada por entidad
- Ha sido enviada a CAR (`fch_envio_car IS NOT NULL`)
- El evento tiene `estado_registro = 'en_validacion_car'`
- NO ha sido validada ni rechazada por CAR

8.2 Esperando aprobación del validador CAR.

### 9. Regla: Estado VALIDADO_CAR
9.1 Una acción está en **VALIDADO_CAR** cuando:
- Ha sido aprobada por CAR
- Existe un evento con `tipo_evento = 'validacion_car'` y `estado_registro = 'validado_car'`
- Fecha de validación por CAR existe (`fch_validacion_car IS NOT NULL`)

9.2 Este es el estado final exitoso del proceso de validación.

### 10. Regla: Estado RECHAZADO
10.1 Una acción está en **RECHAZADO** cuando:
- Un validador (entidad o CAR) la rechazó
- Existe un evento con `estado_registro = 'rechazado'`
- Fecha de rechazo existe (`fch_rechazo IS NOT NULL`)
- Hay observaciones de validación registradas

10.2 La acción vuelve a ser editable para realizar correcciones.

### 11. Transiciones de estado válidas
11.1 El sistema debe validar que las transiciones de estado sean lógicas:
```
BORRADOR → EN_VALIDACION_ENTIDAD → VALIDADO_ENTIDAD → EN_VALIDACION_CAR → VALIDADO_CAR
              ↓                          ↓                        ↓
         RECHAZADO ← → BORRADOR → EN_VALIDACION_ENTIDAD
```

11.2 Transiciones no permitidas:
- De BORRADOR directo a VALIDADO_ENTIDAD (debe pasar por validación)
- De RECHAZADO a VALIDADO sin pasar por EN_VALIDACION
- Regresar de VALIDADO_CAR a estados anteriores (salvo con permisos especiales)

### 12. Validación de transición
12.1 Antes de cambiar el estado, validar que la transición sea permitida:
```javascript
function esTransicionValida(estadoActual, estadoNuevo) {
  const transiciones = {
    'BORRADOR': ['EN_VALIDACION_ENTIDAD'],
    'EN_VALIDACION_ENTIDAD': ['VALIDADO_ENTIDAD', 'RECHAZADO'],
    'VALIDADO_ENTIDAD': ['EN_VALIDACION_CAR'],
    'EN_VALIDACION_CAR': ['VALIDADO_CAR', 'RECHAZADO'],
    'RECHAZADO': ['BORRADOR', 'EN_VALIDACION_ENTIDAD'],
    'VALIDADO_CAR': [] // Estado final
  };
  
  return transiciones[estadoActual]?.includes(estadoNuevo);
}
```

12.2 Si la transición no es válida, rechazar con error explicativo.

### 13. Historial de cambios de estado
13.1 Todos los cambios de estado deben registrarse en la tabla `evento`:
- Evento anterior: Estado previo
- Evento nuevo: Estado actual
- Usuario que causó el cambio
- Fecha y hora del cambio
- Motivo del cambio (si aplica)

13.2 Esto permite auditoría completa del ciclo de vida de la acción.

### 14. Reconciliación de inconsistencias
14.1 El sistema debe tener una función de reconciliación que:
- Compare el estado físico (`estado_accion`) con el estado calculado desde eventos
- Identifique inconsistencias
- Ofrezca corregir el estado físico basándose en eventos

14.2 Útil para detectar y corregir errores de sincronización.

### 15. Consulta de estado actual
15.1 Proporcionar función que retorne el estado actual con toda su información:
```javascript
getEstadoAccion(accionId) {
  return {
    estado: 'EN_VALIDACION_ENTIDAD',
    fecha_estado: '2026-01-15T10:30:00Z',
    usuario_responsable: 'María García',
    puede_editar: false,
    siguiente_accion: 'Esperar validación de entidad',
    transiciones_disponibles: ['VALIDADO_ENTIDAD', 'RECHAZADO']
  }
}
```

15.2 Esta información se usa en la interfaz para mostrar estado y acciones disponibles.

### 16. Performance de cálculo
16.1 Si el estado se calcula desde eventos, optimizar con:
- Índice en `accion_id_principal`, `tabla_evento`, `fecha_evento`
- Cache del estado calculado
- Actualización del campo físico para consultas rápidas

16.2 El acceso al estado debe ser eficiente incluso con muchos eventos.

### 17. Estados compuestos
17.1 Opcionalmente, considerar subestados más detallados:
- `EN_VALIDACION_ENTIDAD_PENDIENTE`: Enviado pero no revisado
- `EN_VALIDACION_ENTIDAD_EN_REVISION`: Al menos un validador está revisando
- `VALIDADO_ENTIDAD_PARCIAL`: Algunos validadores aprobaron, otros pendientes

17.2 Esto proporciona mayor granularidad si se requiere.

### 18. Documentación de reglas de estado
18.1 Mantener documentación clara de:
- Todos los estados posibles
- Condiciones para cada estado
- Transiciones permitidas
- Permisos asociados a cada estado

18.2 Esta documentación es crítica para mantenimiento futuro.

---

### Resultado esperado

Un **sistema de gestión de estados robusto** que puede derivar el estado de una acción desde sus eventos o mantenerlo en un campo físico sincronizado, con reglas claras de transición entre estados (BORRADOR → EN_VALIDACION_ENTIDAD → VALIDADO_ENTIDAD → EN_VALIDACION_CAR → VALIDADO_CAR, o RECHAZADO), validación de transiciones permitidas, historial completo de cambios, y mecanismos de reconciliación para mantener consistencia entre el estado físico y los eventos.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-159.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-159.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-159.png)
