# HU-PIGCCT-SYM-162  
## Épica: Consistencia entre acción y relaciones  
### Revertir estado de validación ante cambios

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión de estados.  
> **Quiero:** marcar una acción como pendiente de validación cuando se crea un nuevo evento después de validada.  
> **Para:** garantizar que cualquier cambio posterior a la validación sea revisado nuevamente antes de considerarse válido.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Principio de re-validación
1.1 El sistema debe implementar el principio: **"Cualquier cambio después de validar requiere nueva validación"**.  
1.2 Si una acción validada es modificada, debe volver a un estado que requiera revisión.  
1.3 Esto garantiza integridad: lo validado no cambia sin supervisión.

### 2. Detección de cambios post-validación
2.1 El sistema debe detectar cuando se crea un nuevo evento en una acción ya validada:
- Acción con `estado_accion = 'VALIDADO_ENTIDAD'` o `'VALIDADO_CAR'`
- Se genera un evento nuevo (create, update, delete) en acción o sus relaciones
- El evento tiene fecha posterior a la fecha de validación

2.2 Esto indica que la acción cambió después de ser validada.

### 3. Cambio automático de estado
3.1 Al detectar un cambio post-validación, cambiar el estado automáticamente:
```
Estado actual: VALIDADO_ENTIDAD
↓
Evento nuevo creado
↓
Nuevo estado: REQUIERE_REVALIDACION o BORRADOR
```

3.2 El cambio de estado debe ser automático e inmediato.

### 4. Notificación a validadores
4.1 Al revertir el estado, notificar a los validadores que aprobaron originalmente:
```
"La acción '[Nombre]' que validaste ha sido modificada"
"Usuario: [nombre] realizó cambios el [fecha]"
"La acción requiere nueva validación"
"Ver cambios realizados"
```

4.2 Los validadores deben saber que su validación ya no es válida.

### 5. Notificación al registrador
5.1 Notificar al usuario que realizó el cambio:
```
"Importante: Esta acción estaba validada"
"Al modificarla, necesitará ser validada nuevamente"
"Puedes continuar editando y luego reenviar a validación"
```

5.2 El usuario entiende las consecuencias de modificar información validada.

### 6. Registro del evento de reversión
6.1 Crear un evento que documente la reversión:
- `tipo_evento`: 'reversion_validacion'
- `estado_registro`: 'requiere_revalidacion'
- `usuario_evento`: Usuario que hizo el cambio
- `fecha_evento`: Fecha del cambio
- `datos_evento`: JSON con detalles del cambio que causó la reversión

6.2 Esto mantiene trazabilidad completa.

### 7. Identificación de qué cambió
7.1 El sistema debe identificar exactamente qué fue modificado:
- ¿La acción principal?
- ¿Un indicador asociado?
- ¿Se agregó o eliminó un adjunto?
- ¿Se modificaron valores de seguimiento?

7.2 Esta información ayuda a los validadores a re-revisar eficientemente.

### 8. Comparación antes/después
8.1 Proporcionar una vista de comparación:
```
CAMBIOS REALIZADOS DESPUÉS DE VALIDACIÓN:

Acción principal:
- Presupuesto: $50M → $75M (Modificado)
- Cronograma: Actualizado (Ver detalles)

Indicadores:
- Indicador 'Familias beneficiadas': Sin cambios
- Indicador 'Hectáreas': Meta 100 → 150 (Modificado)

Adjuntos:
+ Nuevo archivo: "Informe técnico actualizado.pdf"
```

8.2 Los validadores ven exactamente qué revisar.

### 9. Estados específicos de re-validación
9.1 Considerar estados más específicos en lugar de volver a BORRADOR:
- **REQUIERE_REVALIDACION_ENTIDAD**: Si fue validado por entidad y cambió
- **REQUIERE_REVALIDACION_CAR**: Si fue validado por CAR y cambió
- **MODIFICADO_POST_VALIDACION**: Estado intermedio

9.2 Distinguir entre "nunca validado" y "validado pero cambió".

### 10. Permisos para modificar validadas
10.1 Definir quién puede modificar acciones validadas:
- **Registrador original**: Puede modificar (causa reversión)
- **Administrador**: Puede modificar con permiso especial
- **Validador**: No puede modificar directamente, solo aprobar/rechazar

10.2 Implementar control de permisos estricto.

### 11. Advertencia antes de modificar
11.1 Antes de permitir cambios en acción validada, mostrar advertencia:
```
⚠️ ADVERTENCIA

Esta acción está validada y aprobada.

Si la modificas:
- Requerirá nueva validación
- No estará disponible públicamente hasta re-aprobarse
- Los validadores serán notificados

¿Estás seguro de que deseas continuar?

[Cancelar] [Sí, modificar]
```

11.2 Dar oportunidad de cancelar antes de causar reversión.

### 12. Bloqueo temporal opcional
12.1 Opcionalmente, implementar período de bloqueo después de validar:
- Ejemplo: 24 horas después de validar, la acción no puede modificarse
- Requiere solicitud especial para cambios urgentes
- Previene modificaciones impulsivas

12.2 Esto depende de las reglas de negocio del proyecto.

### 13. Historial de validaciones
13.1 Mantener historial completo de validaciones y reversiones:
```
HISTORIAL:
- 15/01/2026 10:00 - Validada por entidad (María García)
- 16/01/2026 14:30 - Modificada por registrador (Juan Pérez)
  → Reversión automática a REQUIERE_REVALIDACION
- 16/01/2026 15:00 - Reenviada a validación
- 17/01/2026 09:00 - Re-validada por entidad (Pedro López)
```

13.2 Visibilidad completa del ciclo de validación-modificación-revalidación.

### 14. Métricas de re-validaciones
14.1 Registrar métricas sobre reversiones:
- Frecuencia de modificaciones post-validación
- Usuarios que más modifican acciones validadas
- Tiempo promedio entre validación y modificación
- Tasa de re-aprobación después de modificar

14.2 Estas métricas ayudan a identificar problemas de proceso.

### 15. Cambios menores vs mayores
15.1 Opcionalmente, distinguir entre cambios menores y mayores:
- **Menores**: Correcciones tipográficas, ajustes de formato → No requieren re-validación
- **Mayores**: Cambio de presupuesto, indicadores, territorio → Requieren re-validación

15.2 Esto requiere lógica más compleja pero puede ser más eficiente.

### 16. Autorización para cambios sin reversión
16.1 Roles especiales (ej: administrador) pueden tener permiso de modificar sin causar reversión.  
16.2 Estos cambios deben:
- Requerir justificación escrita
- Registrarse en auditoría especial
- Notificarse a validadores originales

16.3 Usar con extrema precaución.

### 17. Impacto en visibilidad pública
17.1 Al revertir validación, la acción debe:
- Dejar de ser visible públicamente
- Removerse de reportes y estadísticas públicas
- Mantenerse visible solo para el registrador y validadores

17.2 Consistencia con las reglas de visibilidad (HU-160).

### 18. Proceso de re-validación simplificado
18.1 La re-validación puede ser más rápida si:
- Solo se revisan los elementos modificados
- Se mantiene la aprobación de elementos no modificados
- Vista de "diff" facilita la revisión

18.2 Eficiencia para validadores sin comprometer calidad.

---

### Resultado esperado

Un **sistema automático de reversión de validación** que detecta cualquier cambio realizado en una acción validada, marca la acción como requiriendo nueva validación, notifica a validadores y registrador, documenta exactamente qué cambió, mantiene historial completo de validaciones y reversiones, ajusta la visibilidad pública automáticamente, y proporciona herramientas de comparación para facilitar la re-validación eficiente de los cambios realizados.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-162.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-162.png)
