# HU-PIGCCT-SYM-151  
## Épica: Envío a validación  
### Enviar acción completa a validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** enviar la acción completa a validación.  
> **Para:** iniciar el proceso de revisión institucional y obtener aprobación formal de la información registrada.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de envío
1.1 El sistema debe proporcionar un botón **"Enviar a validación"** visible en el formulario de la acción.  
1.2 El botón debe estar disponible en todas las pestañas del formulario (ver HU-144).  
1.3 Solo usuarios con rol de registrador deben poder enviar acciones a validación.

### 2. Validación de campos obligatorios
2.1 Antes de permitir el envío, el sistema debe validar que todos los campos obligatorios estén completos:
- **Información general**: Nombre, descripción, tipo de acción, responsable
- **Territorio**: Departamento, municipio, cobertura territorial
- **Articulación con el plan**: Eje estratégico, medida asociada, objetivos
- **Programación y seguimiento**: Fecha de inicio, presupuesto, cronograma

2.2 Si faltan campos obligatorios, el sistema debe:
- Bloquear el envío
- Mostrar mensaje claro: "No se puede enviar a validación. Completa los campos obligatorios"
- Listar los campos faltantes y en qué pestaña se encuentran
- Resaltar visualmente las pestañas con errores

### 3. Validación de indicadores asociados
3.1 El sistema debe validar que exista **al menos un indicador asociado** a la acción.  
3.2 Si no hay indicadores asociados, debe:
- Bloquear el envío
- Mostrar mensaje: "Debes asociar al menos un indicador antes de enviar a validación"
- Ofrecer opción para ir directamente a la pestaña "Indicadores asociados"

3.3 Los indicadores obligatorios (si existen) deben estar completos con su información mínima.

### 4. Validación de valores proyectados
4.1 Para cada indicador asociado, el sistema debe validar que los **valores proyectados** (metas) estén diligenciados.  
4.2 Si faltan valores proyectados en algún indicador:
- Bloquear el envío
- Mostrar mensaje: "Completa los valores proyectados de todos los indicadores"
- Indicar cuáles indicadores tienen información incompleta

4.3 Los valores proyectados incluyen: meta, unidad de medida, fecha objetivo.

### 5. Validación de adjuntos (opcional)
5.1 El sistema puede verificar si existen adjuntos cargados, pero esto puede ser opcional.  
5.2 Si no hay adjuntos, puede mostrar advertencia pero permitir el envío si el usuario confirma.  
5.3 Ciertos tipos de acciones pueden requerir adjuntos obligatorios (configurable).

### 6. Confirmación antes de enviar
6.1 Si todas las validaciones son exitosas, el sistema debe mostrar un diálogo de confirmación:
```
"¿Estás seguro de que deseas enviar esta acción a validación?"

Una vez enviada:
- No podrás editarla hasta que sea revisada
- Los validadores recibirán notificación
- Podrás consultar el estado de validación

¿Deseas continuar?
```

6.2 Opciones: "Confirmar envío", "Cancelar".

### 7. Cambio de estado de la acción
7.1 Al confirmar el envío, el sistema debe actualizar el estado de la acción:
- `estado_accion`: Cambiar de "BORRADOR" a "EN_VALIDACION"
- `fch_envio_validacion`: Establecer fecha y hora actual
- `enviado_por`: Registrar ID del usuario que envía

7.2 Estos campos quedan registrados en la tabla `accion`.

### 8. Envío de eventos asociados
8.1 El sistema debe enviar a validación todos los eventos relacionados con la acción (ver HU-152).  
8.2 Esto incluye eventos de:
- La acción principal
- Indicadores asociados
- Valores de seguimiento
- Adjuntos

8.3 Todos los eventos deben marcarse como enviados simultáneamente.

### 9. Actualización de eventos
9.1 Para todos los eventos relacionados con la acción, el sistema debe actualizar (ver HU-153):
- `fch_envio_validacion`: Fecha y hora del envío
- `usuario_envio`: ID del usuario que envía
- `estado_registro`: Cambiar a "en_validacion_entidad"

9.2 Esto se realiza mediante el campo `accion_id_principal` que agrupa todos los eventos.

### 10. Notificaciones a validadores
10.1 Al enviar exitosamente, el sistema debe generar notificaciones a:
- **Validadores de la entidad**: Usuarios con rol "validador_entidad" de la misma entidad
- Mensaje: "Nueva acción enviada a validación: [Nombre de la acción]"
- Incluir enlace directo a la acción para revisión

10.2 Las notificaciones pueden ser por correo electrónico, en el sistema, o ambos.

### 11. Bloqueo de edición
11.1 Después de enviar, la acción debe quedar **bloqueada para edición** por el registrador.  
11.2 Los campos del formulario deben mostrarse como solo lectura.  
11.3 El usuario puede consultar la acción pero no modificarla.  
11.4 El botón "Guardar borrador" debe desaparecer o deshabilitarse.

### 12. Cambio en botones del formulario
12.1 Después del envío, el formulario debe mostrar:
- Botón "Enviar a validación": Deshabilitado o oculto
- Botón "Consultar estado": Para ver el estado de validación
- Indicador visual: "Estado: En validación por entidad"

12.2 El usuario no debe poder reenviar la acción que ya está en validación.

### 13. Feedback al usuario
13.1 Al completar el envío exitosamente, mostrar mensaje:
```
"Acción enviada a validación exitosamente"
"Los validadores de tu entidad han sido notificados"
"Recibirás una notificación cuando sea revisada"
```

13.2 Si ocurre un error durante el envío:
- Mostrar mensaje de error específico
- Mantener la acción en estado borrador
- Permitir al usuario corregir e intentar nuevamente

### 14. Registro en auditoría
14.1 El envío a validación debe registrarse en logs de auditoría con:
- Usuario que envió
- Fecha y hora del envío
- ID de la acción enviada
- Validadores notificados
- Cantidad de eventos enviados

14.2 Esta información es útil para seguimiento y análisis.

### 15. Listado de acciones
15.1 En el listado de acciones del usuario, la acción enviada debe:
- Cambiar su indicador de estado a "En validación"
- Mostrar fecha de envío
- Indicar con badge o color diferente
- Permitir consulta pero no edición

15.2 El usuario puede filtrar acciones por estado: "Borradores", "En validación", "Validadas", etc.

### 16. Reversión del envío (opcional)
16.1 Opcionalmente, el sistema puede permitir **cancelar el envío** antes de que un validador revise la acción.  
16.2 Esto devolvería la acción a estado borrador.  
16.3 Debe requerir confirmación y registrarse en auditoría.  
16.4 Esta funcionalidad depende de las reglas de negocio del proyecto.

### 17. Métricas de envío
17.1 El sistema puede registrar métricas sobre envíos:
- Tiempo promedio desde creación hasta envío
- Número de intentos fallidos (por validaciones incompletas)
- Porcentaje de acciones enviadas vs borradores

17.2 Estas métricas ayudan a identificar problemas en el proceso de registro.

---

### Resultado esperado

Una **acción enviada exitosamente a validación** que pasa de estado borrador a en validación, con todos sus eventos marcados con fecha de envío, notificaciones generadas a los validadores correspondientes, y la acción bloqueada para edición por el registrador hasta que sea revisada.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-151.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-151.png)


