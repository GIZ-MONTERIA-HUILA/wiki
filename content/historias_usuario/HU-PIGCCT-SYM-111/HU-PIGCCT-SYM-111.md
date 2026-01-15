# HU-PIGCCT-SYM-111  
## Épica: Gestión de adjuntos y evidencias del PIGCCT  
### Activar o inactivar adjunto

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** activar o inactivar archivos adjuntos asociados a registros del PIGCCT.  
> **Para:** gestionar la vigencia y disponibilidad de la documentación sin perder información histórica, permitiendo ocultar adjuntos obsoletos o incorrectos mientras se mantiene la trazabilidad completa para auditorías futuras.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Campo de estado en la tabla de adjuntos
1.1 La tabla `adjuntos` debe incluir un campo **`activo`** (boolean o equivalente).  
1.2 Los valores permitidos son:
- `true` o `1`: Adjunto activo (visible y disponible).
- `false` o `0`: Adjunto inactivo (oculto en vistas normales).

1.3 El valor por defecto al crear un adjunto debe ser `activo = true`.

### 2. Acceso a la funcionalidad
2.1 La opción de **"Activar/Inactivar adjunto"** debe estar disponible desde la lista de adjuntos.  
2.2 Solo usuarios con rol de **administrador** o **gestor del registro** deben poder cambiar el estado.  
2.3 Usuarios sin permisos no deben ver la opción o debe estar deshabilitada.

### 3. Cambio de estado: Inactivar adjunto
3.1 El sistema debe permitir inactivar un adjunto activo mediante una acción clara (botón, ícono, opción de menú).  
3.2 Al seleccionar inactivar, el sistema debe mostrar un diálogo de confirmación.  
3.3 Ejemplo de confirmación:  
_"¿Está seguro de inactivar este adjunto? El archivo no se eliminará pero ya no será visible para usuarios estándar."_

3.4 Al confirmar, el sistema debe:
- Actualizar el campo `activo = false`.
- Actualizar el campo `updatedat` con la fecha y hora actual.
- Mantener el archivo físico almacenado sin eliminarlo.

### 4. Cambio de estado: Activar adjunto
4.1 El sistema debe permitir reactivar un adjunto inactivo.  
4.2 Solo administradores deben poder ver adjuntos inactivos y reactivarlos.  
4.3 Al seleccionar activar, el sistema debe:
- Actualizar el campo `activo = true`.
- Actualizar el campo `updatedat` con la fecha y hora actual.
- Hacer el adjunto visible nuevamente en las vistas estándar.

### 5. Conservación de información histórica
5.1 La inactivación es un **borrado lógico**, no físico.  
5.2 Toda la información del adjunto debe conservarse:
- Archivo físico en el almacenamiento.
- Registro completo en la tabla `adjuntos`.
- Metadatos, referencias, fechas de creación y modificación.

5.3 Esta conservación permite:
- Auditorías posteriores.
- Reactivación si fue error.
- Cumplimiento de normativas de retención documental.

### 6. Filtrado en consultas y vistas
6.1 Las vistas estándar del sistema deben mostrar **solo adjuntos activos** por defecto.  
6.2 Las consultas deben incluir filtro `WHERE activo = true` automáticamente.  
6.3 Los adjuntos inactivos no deben aparecer en:
- Lista de adjuntos de un registro.
- Resultados de búsqueda.
- Contadores de documentos.

### 7. Vista de adjuntos inactivos para administradores
7.1 Los administradores deben tener acceso a una vista que muestre **todos los adjuntos**, incluyendo inactivos.  
7.2 Los adjuntos inactivos deben marcarse visualmente (ej: color gris, etiqueta "Inactivo", tachado).  
7.3 Desde esta vista, los administradores pueden reactivar adjuntos.

### 8. Registro de auditoría
8.1 Cada cambio de estado debe registrarse en el log de auditoría:
- Usuario que realizó el cambio.
- Fecha y hora del cambio.
- Estado anterior y nuevo estado.
- Adjunto afectado (ID, nombre).
- Motivo (opcional, si el sistema lo solicita).

8.2 Esta información debe ser inmutable y consultable.

### 9. Validación de permisos
9.1 El sistema debe validar que el usuario tenga permisos antes de permitir el cambio de estado.  
9.2 Si el usuario no es administrador o gestor autorizado, el sistema debe:
- Bloquear la operación.
- Mostrar mensaje: _"No tiene permisos para modificar el estado de este adjunto."_

### 10. Restricciones de negocio
10.1 El sistema puede implementar reglas adicionales según necesidades institucionales:
- Adjuntos asociados a registros cerrados pueden no permitir cambios de estado.
- Puede requerirse justificación escrita para inactivar.
- Puede limitarse la cantidad de veces que un adjunto puede reactivarse.

10.2 Estas reglas deben documentarse claramente.

### 11. Mensajes de retroalimentación
11.1 Al inactivar exitosamente, el sistema debe mostrar:  
_"Adjunto inactivado correctamente."_

11.2 Al activar exitosamente:  
_"Adjunto reactivado correctamente."_

11.3 En caso de error, informar claramente la causa.

### 12. Impacto en reportes y estadísticas
12.1 Los reportes y estadísticas deben considerar solo adjuntos activos por defecto.  
12.2 Debe existir la opción de generar reportes incluyendo adjuntos inactivos si se requiere para auditorías.  
12.3 Los indicadores de "cantidad de evidencias" deben reflejar solo adjuntos activos.

### 13. Eliminación física vs inactivación
13.1 La eliminación física de adjuntos debe ser una operación separada, más restrictiva y controlada.  
13.2 La inactivación es el método recomendado para gestión rutinaria.  
13.3 Solo en casos excepcionales (orden legal, datos sensibles) debe permitirse eliminación física.

### 14. Usabilidad y experiencia de usuario
14.1 El cambio de estado debe ser rápido y no interrumpir el flujo de trabajo.  
14.2 La interfaz debe indicar claramente el estado actual del adjunto.  
14.3 El sistema debe prevenir cambios accidentales mediante confirmaciones apropiadas.

---

### Resultado esperado

Un **sistema de gestión de estados** que permite activar e inactivar adjuntos de manera controlada, preservando toda la información histórica sin eliminación física, con registro completo de auditoría y restricción de acceso basada en roles, facilitando la administración de evidencia documental vigente en el PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-111.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-111.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-111.png)
