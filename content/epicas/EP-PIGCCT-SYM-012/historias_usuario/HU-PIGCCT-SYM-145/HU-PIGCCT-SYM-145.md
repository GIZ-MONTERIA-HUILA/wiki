# HU-PIGCCT-SYM-145  
## Épica: Botones del formulario y comportamiento  
### Guardar acción como borrador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** guardar la acción como borrador sin enviarla a validación.  
> **Para:** continuar completándola posteriormente de manera progresiva y enviarla solo cuando esté lista.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Funcionalidad de guardar borrador
1.1 El sistema debe permitir guardar la acción en cualquier momento desde el formulario.  
1.2 El guardado como borrador no debe requerir que todos los campos obligatorios estén completos.  
1.3 El sistema debe validar solo campos críticos mínimos (ej: nombre de la acción).

### 2. Almacenamiento en la tabla acción
2.1 Al guardar como borrador, el sistema debe almacenar la información en la tabla **accion**.  
2.2 Debe incluir todos los campos diligenciados hasta el momento.  
2.3 Los campos no diligenciados se guardan como nulos o con valores por defecto.

### 3. Asignación de identificador
3.1 Si es una acción nueva (primer guardado), el sistema debe:
- Asignar un identificador único (`accion_id`)
- Establecer fecha de creación
- Registrar usuario creador

3.2 Si es una acción existente (guardado posterior), debe actualizar el registro existente.

### 4. Estado de la acción
4.1 El sistema debe establecer el estado de la acción como **"Borrador"** o equivalente.  
4.2 Este estado debe ser diferenciado de:
- "En validación"
- "Validada"
- "Rechazada"

4.3 El campo de estado puede ser `estado_accion = 'BORRADOR'` en la tabla accion.

### 5. Generación de evento
5.1 Al guardar el borrador, el sistema debe generar un evento en la tabla **evento** (ver HU-117, HU-118).  
5.2 El tipo de evento depende del contexto:
- **create**: Si es la primera vez que se guarda la acción
- **update**: Si la acción ya existía previamente

5.3 El evento debe incluir:
- `tabla`: 'accion'
- `tabla_id`: ID de la acción
- `afectacion`: 'create' o 'update'
- `valor_nuevo`: JSON con los datos actuales
- `valor_anterior`: JSON con los datos previos (solo para update)
- `creado_por`: ID del usuario

### 6. Fecha de envío del evento
6.1 El evento generado **no debe tener fecha de envío** (`fch_envio_validacion` = null).  
6.2 Esto indica que el evento aún no ha sido enviado al flujo de validación.  
6.3 El campo `estado_registro` puede ser 'borrador' o 'pendiente_envio'.

### 7. Mantener acción editable
7.1 Después de guardar como borrador, la acción debe permanecer **completamente editable**.  
7.2 El usuario debe poder:
- Modificar cualquier campo
- Agregar información en pestañas adicionales
- Guardar nuevamente como borrador múltiples veces
- Eventualmente enviar a validación cuando esté lista

### 8. Validaciones mínimas
8.1 El sistema debe validar solo campos críticos al guardar como borrador:
- Nombre de la acción (obligatorio)
- Relación con PIGCCT (obligatorio)
- Usuario creador (automático)

8.2 Otros campos obligatorios para envío a validación pueden quedar pendientes.

### 9. Feedback al usuario
9.1 Al guardar exitosamente, el sistema debe mostrar mensaje:
```
"Borrador guardado exitosamente a las [HH:MM]"
```

9.2 Si es el primer guardado, debe indicar que ahora puede acceder a pestañas de relaciones:
```
"Acción creada. Ahora puedes agregar indicadores y adjuntos."
```

9.3 Si falla el guardado, debe mostrar mensaje de error con la causa.

### 10. Actualización del formulario
10.1 Después de guardar por primera vez, el sistema debe:
- Actualizar el título del formulario con el ID de la acción
- Habilitar las pestañas de relaciones (ver HU-143)
- Mantener la información en el formulario (no recargar la página)

10.2 El usuario debe poder continuar editando inmediatamente.

### 11. Contador de cambios sin guardar
11.1 El sistema puede mostrar un indicador de "cambios sin guardar" cuando el usuario modifica datos.  
11.2 Este indicador debe desaparecer después de guardar exitosamente.  
11.3 Puede mostrarse como icono, asterisco (*) o mensaje "Hay cambios sin guardar".

### 12. Guardado automático opcional
12.1 Opcionalmente, el sistema puede implementar guardado automático periódico (cada X minutos).  
12.2 El guardado automático debe ser silencioso (sin diálogo de confirmación).  
12.3 Debe mostrar un indicador discreto: "Guardado automáticamente a las [HH:MM]".

### 13. Listado de borradores
13.1 Las acciones guardadas como borrador deben aparecer en el listado de acciones del usuario.  
13.2 Deben tener un indicador visual de estado "Borrador".  
13.3 El usuario debe poder:
- Editar el borrador (continuar editando)
- Eliminar el borrador (si no ha sido enviado)
- Ver información básica del borrador

### 14. Auditoría de guardados
14.1 El sistema debe registrar en logs cada guardado de borrador:
- Usuario que guarda
- Fecha y hora
- Acción guardada (ID)
- Tipo de operación (create/update)

14.2 Esta información es útil para auditoría y análisis de uso.

### 15. Manejo de errores
15.1 Si ocurre un error al guardar (ej: problema de conexión), el sistema debe:
- Mostrar mensaje de error claro
- Mantener los datos en el formulario
- Permitir reintentar el guardado
- Opcionalmente, guardar en localStorage como respaldo

---

### Resultado esperado

Una **acción guardada como borrador** en la tabla accion con un evento asociado de tipo create o update sin fecha de envío, que permanece completamente editable para el usuario y puede ser completada y enviada a validación posteriormente.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-145.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-145.png)

