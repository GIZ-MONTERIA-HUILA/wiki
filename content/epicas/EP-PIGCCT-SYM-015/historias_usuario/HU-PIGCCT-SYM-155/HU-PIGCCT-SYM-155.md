# HU-PIGCCT-SYM-155  
## Épica: Bloqueo y control de edición  
### Permitir edición solo si el evento es rechazado

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** poder editar una acción que fue rechazada en validación.  
> **Para:** corregir las observaciones realizadas por los validadores y poder reenviarla.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación de acciones rechazadas
1.1 El sistema debe identificar que una acción fue rechazada mediante:
- `estado_accion = 'RECHAZADO'`
- `fch_rechazo IS NOT NULL`
- Existencia de observaciones de validación

1.2 Solo las acciones en estado rechazado deben habilitarse para edición.

### 2. Notificación de rechazo al usuario
2.1 El sistema debe notificar al usuario registrador cuando su acción es rechazada:
- **Notificación en el sistema**: "Tu acción [Nombre] ha sido rechazada"
- **Correo electrónico**: Con detalles del rechazo y observaciones
- **Dashboard**: Indicador de "Acciones rechazadas pendientes de corrección"

2.2 La notificación debe incluir:
- Nombre de la acción rechazada
- Fecha de rechazo
- Validador que rechazó
- Observaciones o motivos del rechazo
- Enlace directo para corregir

### 3. Visualización de observaciones
3.1 Al abrir una acción rechazada, debe mostrarse prominentemente:
```
"Esta acción fue rechazada en validación"
"Fecha de rechazo: [fecha]"
"Validador: [nombre del validador]"

"Observaciones:"
[Texto de las observaciones del validador]

"Debes corregir los problemas señalados y reenviar la acción"
```

3.2 Las observaciones deben ser claramente visibles en la parte superior del formulario.

### 4. Habilitación de campos para edición
4.1 Al abrir una acción rechazada, todos los campos deben volver a ser **editables**.  
4.2 Los campos deben mostrar el comportamiento normal:
- Cursor de texto en campos de entrada
- Sin fondo gris de bloqueo
- Dropdowns funcionales
- Fechas seleccionables

4.3 El formulario debe comportarse como si estuviera en estado borrador.

### 5. Habilitación de todas las pestañas
5.1 Todas las pestañas del formulario deben permitir edición:
- **Información general**: Campos editables
- **Territorio**: Puede cambiar departamento, municipio, cobertura
- **Articulación con el plan**: Modificable
- **Programación y seguimiento**: Fechas y presupuesto editables
- **Indicadores asociados**: Puede agregar, editar o eliminar indicadores
- **Adjuntos**: Puede cargar nuevos archivos o eliminar existentes
- **Estado**: Actualizable según cambios

5.2 No debe haber restricciones en ninguna pestaña.

### 6. Habilitación del botón "Guardar borrador"
6.1 El botón **"Guardar borrador"** debe estar visible y habilitado.  
6.2 El usuario debe poder guardar cambios parciales mientras corrige.  
6.3 Al guardar, el estado debe mantenerse en 'RECHAZADO' hasta que se reenvíe.

### 7. Habilitación del botón "Enviar a validación"
7.1 El botón **"Enviar a validación"** debe estar visible y habilitado.  
7.2 Permite al usuario reenviar la acción después de realizar las correcciones.  
7.3 Al reenviar (ver HU-156), se genera un nuevo evento y cambia el estado.

### 8. Operaciones CRUD en relaciones
8.1 El usuario debe poder realizar todas las operaciones en tablas relacionadas:
- **Agregar** nuevos indicadores asociados
- **Modificar** indicadores existentes
- **Eliminar** indicadores (si es necesario para corregir)
- **Cargar** nuevos adjuntos
- **Eliminar** adjuntos incorrectos
- **Modificar** valores de seguimiento

8.2 Libertad completa de edición para realizar correcciones.

### 9. Marcado de campos con observaciones
9.1 Si las observaciones del validador señalan **campos específicos** con problemas:
- Resaltar esos campos con borde rojo o color distintivo
- Mostrar la observación específica junto al campo
- Ejemplo: "Validador: La fecha de inicio es inconsistente con el cronograma"

9.2 Esto ayuda al usuario a identificar exactamente qué corregir.

### 10. Validación en backend
10.1 El backend debe verificar el estado antes de permitir edición:
```javascript
if (accion.estado_accion === 'RECHAZADO') {
  // Permitir edición
  return { editable: true };
} else if (accion.estado_accion === 'EN_VALIDACION') {
  // Bloquear edición
  return { 
    editable: false, 
    mensaje: "No puedes editar una acción en validación" 
  };
}
```

10.2 Solo acciones rechazadas o en borrador son editables.

### 11. Historial de rechazos
11.1 El sistema debe mantener un historial de todos los rechazos:
- Fecha de cada rechazo
- Validador que rechazó
- Observaciones de cada rechazo
- Correcciones realizadas

11.2 Esto proporciona trazabilidad completa del proceso de corrección.

### 12. Cambio de estado al guardar
12.1 Al guardar cambios en una acción rechazada (sin reenviar):
- Mantener `estado_accion = 'RECHAZADO'`
- Actualizar `fch_actualizacion`
- Generar evento de tipo "update"
- NO cambiar `fch_envio_validacion` ni `fch_rechazo`

12.2 El estado sigue siendo rechazado hasta que se reenvíe.

### 13. Indicadores visuales de acción rechazada
13.1 El formulario debe mostrar claramente que es una acción rechazada:
- Badge: "Rechazada - Requiere corrección"
- Color distintivo (por ejemplo, rojo)
- Ícono de alerta o advertencia
- Panel de observaciones siempre visible

13.2 El usuario debe saber en todo momento que está corrigiendo una acción rechazada.

### 14. Bloqueo para otros usuarios
14.1 Aunque la acción esté rechazada, solo el **usuario registrador original** debe poder editarla.  
14.2 Otros usuarios (incluso de la misma entidad) no deben poder modificarla.  
14.3 Los validadores pueden verla pero no editarla directamente.

### 15. Timeout de corrección (opcional)
15.1 Opcionalmente, el sistema puede establecer un plazo para corregir:
- "Tienes [X] días para corregir y reenviar esta acción"
- Mostrar contador de días restantes
- Enviar recordatorios si se acerca el plazo

15.2 Si expira el plazo, puede requerir intervención del administrador.

### 16. Comparación antes/después
16.1 El sistema puede ofrecer una vista de comparación:
- "Ver cambios realizados desde el rechazo"
- Resaltar qué campos fueron modificados
- Ayuda a verificar que se corrigió lo solicitado

16.2 Esta funcionalidad facilita la verificación antes de reenviar.

### 17. Mensaje de confirmación al guardar
17.1 Al guardar cambios en una acción rechazada, mostrar:
```
"Cambios guardados exitosamente"
"La acción sigue en estado rechazado"
"Recuerda reenviarla a validación cuando termines las correcciones"
```

17.2 Recordatorio claro de que debe reenviar cuando esté lista.

### 18. Transición a reenvío
18.1 Cuando el usuario está listo para reenviar:
- Validar nuevamente campos obligatorios
- Verificar que las observaciones fueron atendidas
- Permitir agregar comentarios sobre las correcciones realizadas
- Generar nuevo evento (ver HU-156)
- Cambiar estado a 'EN_VALIDACION' nuevamente

18.2 Esto cierra el ciclo de corrección y reinicia la validación.

---

### Resultado esperado

Una **acción rechazada totalmente editable** por el usuario registrador, con observaciones del validador claramente visibles, campos específicos señalados si aplica, botones de guardado y reenvío habilitados, validación en backend que permite solo edición de acciones rechazadas o en borrador, y un flujo claro para realizar correcciones y reenviar la acción al proceso de validación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-155.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-155.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-155.png)
