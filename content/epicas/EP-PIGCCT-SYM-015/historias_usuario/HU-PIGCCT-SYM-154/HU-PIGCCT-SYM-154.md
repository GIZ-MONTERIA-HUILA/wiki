# HU-PIGCCT-SYM-154  
## Épica: Bloqueo y control de edición  
### Bloquear edición tras envío a validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de validación.  
> **Quiero:** bloquear la edición de una acción enviada a validación.  
> **Para:** preservar la integridad de la información bajo revisión y evitar modificaciones mientras los validadores trabajan.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación de acciones en validación
1.1 El sistema debe identificar que una acción está en validación mediante:
- `estado_accion = 'EN_VALIDACION'`
- `fch_envio_validacion IS NOT NULL`

1.2 Cualquier acción que cumpla estas condiciones debe considerarse bloqueada para edición.

### 2. Bloqueo de campos del formulario
2.1 Al abrir una acción en validación, todos los campos del formulario deben mostrarse como **solo lectura**.  
2.2 Los campos deben tener indicadores visuales de bloqueo:
- Fondo gris o diferente
- Cursor "not-allowed"
- Ícono de candado junto a campos importantes

2.3 Los campos no deben responder a intentos de edición.

### 3. Bloqueo de todas las pestañas
3.1 El bloqueo debe aplicarse a todas las pestañas del formulario:
- **Información general**: Todos los campos bloqueados
- **Territorio**: Sin posibilidad de cambiar departamento, municipio, cobertura
- **Articulación con el plan**: Eje estratégico, medida, objetivos bloqueados
- **Programación y seguimiento**: Fechas y presupuesto bloqueados
- **Indicadores asociados**: No se pueden agregar, editar o eliminar indicadores
- **Adjuntos**: No se pueden cargar nuevos archivos ni eliminar existentes
- **Estado**: Solo consulta del estado actual

3.2 Todas las pestañas deben mostrar indicador visual de "Solo lectura".

### 4. Deshabilitación del botón "Guardar borrador"
4.1 El botón **"Guardar borrador"** debe:
- Estar completamente oculto, o
- Mostrarse deshabilitado con tooltip: "No puedes editar una acción en validación"

4.2 No debe ser posible guardar cambios mientras la acción está en validación.

### 5. Deshabilitación del botón "Enviar a validación"
5.1 El botón **"Enviar a validación"** también debe estar deshabilitado u oculto.  
5.2 No tiene sentido permitir reenviar algo que ya está en validación.  
5.3 Puede mostrar tooltip: "Esta acción ya está en proceso de validación".

### 6. Bloqueo de operaciones CRUD en relaciones
6.1 No se debe permitir:
- **Agregar** nuevos indicadores asociados
- **Modificar** indicadores existentes
- **Eliminar** indicadores asociados
- **Cargar** nuevos adjuntos
- **Eliminar** adjuntos existentes
- **Modificar** valores de seguimiento

6.2 Todas las operaciones de escritura en tablas relacionadas deben bloquearse.

### 7. Validación en backend
7.1 Además del bloqueo en frontend, el backend debe validar el estado antes de aceptar cualquier cambio.  
7.2 Si un usuario intenta modificar una acción en validación (por ejemplo, mediante API directa):
```
{
  "error": "No se puede modificar una acción en proceso de validación",
  "codigo": "ACCION_BLOQUEADA",
  "estado_actual": "EN_VALIDACION"
}
```

7.3 Esto previene bypass del bloqueo de frontend.

### 8. Mensaje informativo al abrir la acción
8.1 Al abrir una acción en validación, mostrar mensaje prominente:
```
"Esta acción está en proceso de validación"
"No puedes realizar cambios hasta que sea revisada"
"Recibirás notificación cuando los validadores terminen la revisión"
```

8.2 El mensaje debe ser visible en la parte superior del formulario.  
8.3 Puede incluir la fecha de envío: "Enviada el: [fecha]".

### 9. Indicador de estado en el encabezado
9.1 El encabezado del formulario debe mostrar claramente:
- Badge: "En validación"
- Color distintivo (por ejemplo, amarillo/ámbar)
- Ícono de reloj o validación pendiente

9.2 Este indicador debe ser visible en todas las pestañas.

### 10. Bloqueo de navegación hacia edición
10.1 Enlaces o botones que normalmente llevan a "Editar acción" deben:
- Redirigir a vista de solo lectura
- Mostrar mensaje: "Esta acción no puede editarse actualmente"

10.2 No debe haber rutas que permitan acceder a modo edición.

### 11. Consulta permitida
11.1 Aunque la edición esté bloqueada, la **consulta debe ser completamente funcional**.  
11.2 El usuario debe poder:
- Ver toda la información de la acción
- Navegar entre pestañas
- Consultar indicadores y adjuntos
- Ver el historial de cambios
- Descargar archivos adjuntos

11.3 La visualización no debe estar limitada, solo la edición.

### 12. Registro de intentos de edición
12.1 El sistema puede registrar intentos de edición de acciones bloqueadas:
- Usuario que intentó editar
- Fecha y hora del intento
- ID de la acción

12.2 Esto ayuda a identificar confusiones o problemas en la UI.

### 13. Notificación del estado en el listado
13.1 En el listado de acciones del usuario, las acciones en validación deben:
- Mostrar badge "En validación"
- Indicar con color diferente
- No tener botón "Editar", solo "Ver"
- Mostrar fecha de envío

13.2 El usuario debe saber de inmediato qué acciones puede editar y cuáles no.

### 14. Permiso de solo lectura para otros usuarios
14.1 Los validadores u otros usuarios con permisos pueden consultar la acción sin problemas.  
14.2 El bloqueo de edición aplica incluso para:
- El usuario registrador que la creó
- Administradores (a menos que tengan permiso especial)
- Otros usuarios de la misma entidad

14.3 Solo los validadores pueden aprobar/rechazar, no editar directamente.

### 15. Desbloqueo automático tras rechazo
15.1 Si la acción es **rechazada** por un validador, el sistema debe:
- Cambiar `estado_accion` a 'RECHAZADO'
- Permitir edición nuevamente (ver HU-155)
- Notificar al registrador que puede corregir

15.2 El bloqueo es temporal y depende del estado de validación.

### 16. Desbloqueo tras validación completa
16.1 Una vez que la acción es **validada completamente** (por entidad y CAR):
- Cambiar `estado_accion` a 'VALIDADO'
- Mantener campos bloqueados (la información validada no debe modificarse)
- O permitir edición solo con permisos especiales según reglas de negocio

16.2 La lógica de desbloqueo depende de los requisitos del proyecto.

### 17. Accesibilidad del bloqueo
17.1 Los campos bloqueados deben ser accesibles para lectores de pantalla:
- Atributo `aria-readonly="true"`
- Anuncio claro: "Campo solo lectura, acción en validación"

17.2 Usuarios con tecnologías asistivas deben entender que la acción está bloqueada.

### 18. Testing del bloqueo
18.1 El sistema debe tener pruebas que verifiquen:
- Campos no editables en todas las pestañas
- Backend rechaza cambios de acciones en validación
- Botones correctamente deshabilitados
- Mensajes informativos mostrados

18.2 Esto asegura que el bloqueo funcione correctamente en producción.

---

### Resultado esperado

Una **acción en validación completamente bloqueada para edición**, con todos los campos en modo solo lectura, botones de guardado deshabilitados, operaciones CRUD en relaciones bloqueadas, validación en backend que previene modificaciones no autorizadas, y mensajes claros que informan al usuario sobre el estado de bloqueo y cuándo podrá editar nuevamente.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-154.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-154.png)
