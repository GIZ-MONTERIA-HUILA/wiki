# HU-PIGCCT-SYM-147  
## Épica: Asociación de indicadores y adjuntos  
### Asociar indicadores solo después de guardar la acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** poder asociar indicadores únicamente cuando la acción ya está guardada.  
> **Para:** asegurar consistencia en las relaciones de base de datos y evitar errores de integridad referencial.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Requisito previo: acción guardada
1.1 El sistema debe requerir que la acción tenga un identificador único (`accion_id`) antes de permitir asociar indicadores.  
1.2 Una acción sin guardar (nueva) no tiene `accion_id` válido, por lo tanto no puede tener indicadores asociados.  
1.3 Este requisito garantiza la integridad referencial en la tabla `indicador_accion`.

### 2. Deshabilitación de pestaña de indicadores
2.1 Para acciones nuevas (sin guardar), la pestaña **"Indicadores asociados"** debe estar deshabilitada (ver HU-142).  
2.2 Al intentar acceder, debe mostrarse mensaje:
```
"Guarda la acción primero para poder asociar indicadores"
```

2.3 La pestaña debe tener apariencia visual de deshabilitada (atenuada, con candado).

### 3. Habilitación después del primer guardado
3.1 Una vez que la acción se guarda por primera vez y obtiene un `accion_id`, el sistema debe:
- Habilitar automáticamente la pestaña "Indicadores asociados"
- Actualizar la interfaz sin recargar la página
- Mostrar mensaje informativo: "Ahora puedes agregar indicadores a esta acción"

3.2 Esta habilitación ocurre inmediatamente después del guardado exitoso (ver HU-143).

### 4. Acceso a la pestaña de indicadores
4.1 Al acceder a la pestaña "Indicadores asociados" de una acción guardada, el sistema debe mostrar:
- Lista de indicadores ya asociados (si existen)
- Botón para "Agregar nuevo indicador"
- Información del total de indicadores asociados

4.2 Inicialmente, para una acción recién creada, la lista estará vacía.

### 5. Opciones para asociar indicadores
5.1 El sistema debe permitir dos formas de asociar indicadores:
- **Asociar indicador existente**: Seleccionar de catálogo de indicadores del PIGCCT
- **Crear nuevo indicador**: Crear y asociar un indicador específico para esta acción

5.2 Ambas opciones deben guardar la relación en la tabla `indicador_accion`.

### 6. Estructura de la relación acción-indicador
6.1 La tabla `indicador_accion` debe almacenar:
- `id`: Identificador único de la relación
- `accion_id`: **Clave foránea obligatoria** hacia tabla accion
- `indicador_id`: Clave foránea hacia catálogo de indicadores
- Campos adicionales: meta, valor actual, unidad, fecha, etc.
- Metadatos: usuario creador, fecha de creación

6.2 El campo `accion_id` no puede ser nulo, de ahí el requisito de guardar primero la acción.

### 7. Validación de accion_id
7.1 Antes de crear cualquier relación en `indicador_accion`, el sistema debe validar:
- Que `accion_id` exista y sea válido
- Que la acción esté en estado editable (borrador)
- Que el usuario tenga permisos sobre esa acción

7.2 Si alguna validación falla, debe rechazar la operación y mostrar error.

### 8. Creación de nuevo indicador asociado
8.1 Al crear un nuevo indicador asociado, el sistema debe:
- Mostrar formulario con campos del indicador
- Requerir información mínima: nombre, descripción, unidad de medida
- Guardar el indicador con referencia al `accion_id`
- Generar evento de tipo create para el indicador (ver HU-150)

8.2 El indicador queda inmediatamente asociado a la acción.

### 9. Asociación de indicador existente
9.1 Al asociar un indicador del catálogo, el sistema debe:
- Mostrar lista o buscador de indicadores disponibles
- Permitir seleccionar uno o varios indicadores
- Crear registros en `indicador_accion` para cada asociación
- Generar eventos correspondientes

9.2 Puede requerirse información adicional específica para la acción (ej: meta particular).

### 10. Visualización de indicadores asociados
10.1 La pestaña debe mostrar una lista clara de indicadores asociados con:
- Nombre del indicador
- Descripción breve
- Meta definida
- Valor actual
- Unidad de medida
- Estado (pendiente, en progreso, completado)

10.2 Debe permitir ordenar y filtrar la lista si hay muchos indicadores.

### 11. Edición de indicadores asociados
11.1 Para acciones en estado borrador, el usuario debe poder:
- Editar información del indicador asociado
- Cambiar metas o valores
- Eliminar la asociación (si el indicador no es obligatorio)

11.2 Cada modificación debe generar un evento de tipo update.

### 12. Restricciones en estados no editables
12.1 Si la acción está en validación o validada, la asociación de indicadores puede estar restringida.  
12.2 El sistema debe comunicar claramente cuándo no es posible agregar o modificar indicadores.  
12.3 Puede requerirse generar un nuevo evento de actualización para modificar indicadores de acciones validadas.

### 13. Dependencias entre indicadores y acción
13.1 Los indicadores asociados dependen de la existencia de la acción.  
13.2 Si se elimina una acción en borrador, los indicadores asociados deben:
- Eliminarse en cascada (si son específicos de la acción)
- O desasociarse (si son del catálogo general)

13.3 El sistema debe manejar esta dependencia correctamente.

### 14. Mensajes informativos
14.1 Al guardar la acción por primera vez, el sistema puede mostrar:
```
"Acción guardada. Ve a la pestaña 'Indicadores asociados' para agregar indicadores de seguimiento."
```

14.2 En la pestaña de indicadores vacía, mostrar mensaje orientador:
```
"Aún no has asociado indicadores. Haz clic en 'Agregar indicador' para comenzar."
```

### 15. Consistencia de datos
15.1 Al asociar indicadores, el sistema debe garantizar:
- Integridad referencial con la tabla accion
- No permitir duplicados (misma acción + mismo indicador)
- Validar que los datos del indicador sean coherentes

15.2 Cualquier error debe reportarse claramente al usuario.

---

### Resultado esperado

Un **sistema que permite asociar indicadores solo a acciones guardadas** que tienen un identificador válido, garantizando la integridad referencial de la base de datos, con la pestaña de indicadores deshabilitada para acciones nuevas y habilitada automáticamente después del primer guardado.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-147.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-147.png)
