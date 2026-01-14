# HU-PIGCCT-SYM-118  
## Épica: Gestión de eventos y validación de información del PIGCCT  
### Generar evento al actualizar un registro

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario no administrador del sistema.  
> **Quiero:** que el sistema genere automáticamente un evento cuando actualizo un registro.  
> **Para:** registrar los cambios realizados y someterlos al proceso de validación institucional.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Generación automática de evento en actualización
1.1 El sistema debe generar automáticamente un evento cuando un usuario **no administrador** actualiza un registro en alguna de las siguientes tablas:
- acción
- indicador_accion
- indicador_accion_valor
- adjuntos

1.2 La generación del evento debe ser transparente para el usuario, ejecutándose automáticamente al confirmar la actualización.

### 2. Registro del evento tipo update
2.1 El sistema debe crear un nuevo registro en la tabla **evento** con el campo:
- **tipo_afectacion_enm**: Debe establecerse con el valor **"update"**.

2.2 Además de los campos comunes de evento, el sistema debe diligenciar específicamente:
- **valor_anterior**: Contenido JSON o representación del registro antes de la actualización.
- **valor_nuevo**: Contenido JSON o representación del registro después de la actualización.
- **modificado_por**: ID del usuario que realiza la actualización.
- **fch_modificacion**: Fecha y hora de la modificación del registro.

### 3. Captura del valor anterior
3.1 El sistema debe capturar el estado completo del registro **antes** de aplicar la actualización.  
3.2 El valor anterior debe almacenarse en el campo **valor_anterior** en formato JSON.  
3.3 La captura debe incluir todos los campos relevantes del registro para permitir comparaciones completas.

### 4. Captura del valor nuevo
4.1 El sistema debe capturar el estado completo del registro **después** de aplicar la actualización.  
4.2 El valor nuevo debe almacenarse en el campo **valor_nuevo** en formato JSON.  
4.3 La estructura del valor nuevo debe ser coherente con el valor anterior para facilitar la comparación.

### 5. Registro de información de auditoría
5.1 El sistema debe registrar automáticamente:
- **id_usuario_fk**: ID del usuario que modifica el registro.
- **esquema_principal**: Esquema de la base de datos.
- **tabla_principal**: Nombre de la tabla actualizada.
- **id_objeto_principal**: ID del registro actualizado.
- **modificado_por**: ID del usuario modificador.
- **fch_modificacion**: Fecha y hora exacta de la modificación.

### 6. Validación de tipo de usuario
6.1 El sistema debe validar que el usuario que actualiza el registro **no tenga rol de administrador**.  
6.2 Los administradores pueden actualizar registros sin generar eventos de validación.

### 7. Comparación de valores
7.1 El sistema debe permitir identificar claramente qué campos fueron modificados mediante la comparación entre **valor_anterior** y **valor_nuevo**.  
7.2 Esta información debe estar disponible para los validadores durante el proceso de aprobación.

### 8. Estado inicial del evento
8.1 El evento generado debe tener un estado inicial que indique que está **pendiente de envío a validación**.  
8.2 El campo **estado_registro** debe reflejar este estado.

### 9. Manejo de actualizaciones múltiples
9.1 Si un usuario realiza múltiples actualizaciones consecutivas sobre el mismo registro antes de enviar a validación, el sistema debe:
- Opción A: Generar un evento por cada actualización (recomendado para trazabilidad completa).
- Opción B: Consolidar cambios en un solo evento con el valor anterior inicial y el valor nuevo final.

9.2 La estrategia elegida debe estar claramente documentada y ser consistente en todo el sistema.

### 10. Integridad transaccional
10.1 La actualización del registro y la generación del evento deben ejecutarse en una **transacción atómica**.  
10.2 Si la generación del evento falla, el sistema debe:
- Revertir la actualización del registro, o
- Registrar el error y notificar al administrador.

10.3 El sistema debe garantizar coherencia entre el registro actualizado y el evento generado.

### 11. Rendimiento del sistema
11.1 La generación del evento no debe afectar significativamente el tiempo de respuesta de la operación de actualización.  
11.2 El proceso debe estar optimizado para mantener la experiencia de usuario fluida.

---

### Resultado esperado

Un **evento registrado automáticamente** con tipo_afectacion_enm = "update", capturando los valores anterior y nuevo del registro, el usuario modificador y la fecha de modificación, iniciando el proceso de validación de los cambios realizados y garantizando la trazabilidad completa de las modificaciones.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-118.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-118.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-118.png)