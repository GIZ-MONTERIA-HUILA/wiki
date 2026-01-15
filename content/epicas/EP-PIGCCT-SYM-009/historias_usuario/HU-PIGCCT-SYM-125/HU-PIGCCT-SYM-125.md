# HU-PIGCCT-SYM-125  
## Épica: Gestión de eventos y validación de información del PIGCCT  
### Visualizar registros en estado pendiente

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario que registra información y usuario validador.  
> **Quiero:** visualizar mis propios registros pendientes de validación.  
> **Para:** hacer seguimiento al proceso de validación y conocer el estado de mis registros.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a registros pendientes para usuario que registra
1.1 El sistema debe proporcionar una sección o módulo específico llamado **"Mis registros pendientes"** o similar.  
1.2 El usuario que creó un registro debe poder ver sus propios registros independientemente del estado de validación.  
1.3 Esta vista debe estar disponible desde el menú principal o dashboard del usuario.

### 2. Visualización de registros propios en cualquier estado
2.1 Un usuario que registra información debe poder ver todos sus registros, incluyendo aquellos que están:
- Pendientes de envío a validación
- Enviados a validación por entidad
- Validados por entidad - pendientes de CAR
- Rechazados por entidad
- Rechazados por CAR
- Completamente validados

2.2 La lista debe mostrar claramente el estado actual de cada registro.

### 3. Filtrado por estado
3.1 El sistema debe permitir al usuario filtrar sus registros por estado:
- **Todos**
- **Pendientes de envío**
- **En validación**
- **Rechazados**
- **Validados completamente**

3.2 Los filtros deben actualizarse dinámicamente la lista de registros mostrados.

### 4. Información mostrada por registro
4.1 Para cada registro pendiente, el sistema debe mostrar:
- Identificador del registro
- Tabla (acción, indicador_accion, indicador_accion_valor, adjunto)
- Tipo de operación (create/update)
- Fecha de creación
- Fecha de envío a validación (si aplica)
- Estado actual del evento
- Observaciones (si existen)

4.2 La información debe presentarse de manera clara y organizada.

### 5. Detalle del registro pendiente
5.1 El usuario debe poder hacer clic en un registro para ver su información detallada.  
5.2 El detalle debe incluir:
- Todos los campos del registro
- Historial de estados del evento
- Observaciones de validadores (si existen)
- Fechas clave del proceso
- Próximo paso en el flujo de validación

### 6. Acceso para validadores
6.1 Los usuarios con rol de **validador de entidad** deben poder ver:
- Todos los registros enviados a validación de su entidad
- Registros que ellos han validado (aprobados o rechazados)
- Estado actual de cada registro

6.2 Los usuarios con rol de **validador CAR** deben poder ver:
- Todos los registros validados por entidades y pendientes de validación CAR
- Registros que ellos han validado
- Estado actual de cada registro

### 7. Panel de estadísticas
7.1 El sistema debe mostrar un panel con estadísticas rápidas:
- Total de registros pendientes de envío
- Total en validación por entidad
- Total en validación por CAR
- Total rechazados
- Total validados completamente

7.2 Las estadísticas deben ser específicas para cada usuario según su rol.

### 8. Acciones disponibles según estado
8.1 Según el estado del registro, el sistema debe permitir al usuario realizar acciones específicas:
- **Pendiente de envío**: Botón para enviar a validación
- **En validación**: Solo visualización, sin edición
- **Rechazado**: Opción para corregir (generando nuevo evento)
- **Validado**: Solo visualización

8.2 Las acciones disponibles deben estar claramente indicadas en la interfaz.

### 9. Notificaciones y alertas
9.1 El usuario debe recibir notificaciones cuando:
- Un registro es validado (por entidad o CAR)
- Un registro es rechazado
- Se requiere una acción de su parte

9.2 Las notificaciones deben incluir un enlace directo al registro afectado.

### 10. Búsqueda y ordenamiento
10.1 El sistema debe permitir buscar dentro de los registros pendientes por:
- Identificador
- Fecha
- Tabla
- Estado

10.2 El usuario debe poder ordenar la lista por:
- Fecha de creación (más reciente/antigua)
- Estado
- Tabla afectada

### 11. Diferenciación visual por estado
11.1 El sistema debe usar códigos de color o iconos para diferenciar visualmente los estados:
- **Pendiente de envío**: Amarillo/Naranja - Requiere acción
- **En validación**: Azul - En proceso
- **Rechazado**: Rojo - Requiere corrección
- **Validado**: Verde - Completado exitosamente

11.2 Los colores/iconos deben ser consistentes en toda la aplicación.

### 12. Exportación de registros pendientes
12.1 El usuario debe poder exportar la lista de sus registros pendientes a formato Excel o CSV.  
12.2 La exportación debe incluir toda la información relevante del estado de cada registro.

### 13. Restricciones de visualización
13.1 Un usuario **no debe poder ver** registros pendientes de otros usuarios, a menos que tenga rol de validador o administrador.  
13.2 Los validadores solo deben ver registros de su ámbito de responsabilidad (su entidad o región).

### 14. Actualización en tiempo real
14.1 La lista de registros pendientes debe actualizarse automáticamente cuando:
- Cambia el estado de un registro
- Se reciben nuevas validaciones
- Se agregan nuevos registros

14.2 Opcionalmente, implementar actualización mediante polling o websockets.

### 15. Historial de cambios
15.1 Para cada registro pendiente, el usuario debe poder ver un historial cronológico de:
- Creación del registro
- Envío a validación
- Validaciones realizadas (aprobaciones/rechazos)
- Correcciones aplicadas

15.2 El historial debe mostrar fechas, usuarios involucrados y acciones realizadas.

---

### Resultado esperado

Un **módulo de visualización** que permite a usuarios que registran información y a validadores ver sus registros pendientes de validación con información clara del estado actual, acciones disponibles, observaciones de validadores, y estadísticas de seguimiento, facilitando el control y gestión del proceso de validación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-125.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-125.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-125.png)
