# HU-PIGCCT-SYM-127  
## Épica: Gestión de eventos y validación de información del PIGCCT  
### Consultar historial de eventos

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** consultar el historial completo de eventos asociados a una acción.  
> **Para:** realizar auditoría, trazabilidad y conocer todos los cambios realizados a lo largo del tiempo en un registro del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de historial
1.1 El sistema debe proporcionar una opción para consultar el historial de eventos desde:
- La vista de detalle de una acción
- Un módulo específico de auditoría/historial
- El panel de administración del sistema

1.2 Los usuarios con permisos apropiados deben poder acceder al historial.

### 2. Permisos de consulta de historial
2.1 Los siguientes roles deben poder consultar el historial de eventos:
- **Administradores**: Historial completo de todas las acciones
- **Validadores de entidad**: Historial de acciones de su entidad
- **Validadores CAR**: Historial de acciones de su región
- **Usuario que registra**: Historial de sus propias acciones

2.2 El sistema debe filtrar automáticamente el historial según los permisos del usuario.

### 3. Selección de acción para consultar
3.1 El usuario debe poder seleccionar una acción específica mediante:
- Búsqueda por identificador de acción
- Selección desde una lista de acciones
- Navegación desde la vista de detalle de la acción

3.2 El sistema debe validar que el usuario tenga permisos para consultar el historial de esa acción.

### 4. Visualización del historial completo
4.1 El sistema debe mostrar todos los eventos asociados a la acción seleccionada, incluyendo:
- Eventos sobre la tabla **acción** directamente
- Eventos sobre tablas relacionadas: **indicador_accion**, **indicador_accion_valor**, **adjuntos**

4.2 Los eventos deben mostrarse en orden cronológico (del más antiguo al más reciente, o viceversa según preferencia del usuario).

### 5. Información mostrada por evento
5.1 Para cada evento en el historial, el sistema debe mostrar:
- **Identificador del evento**
- **Fecha y hora de creación**
- **Tipo de afectación**: create, update, delete
- **Tabla afectada**: acción, indicador_accion, indicador_accion_valor, adjuntos
- **ID del objeto relacionado** (si aplica)
- **Usuario que creó el registro**
- **Estado del evento**: pendiente, en validación, validado, rechazado
- **Fecha de envío** (si aplica)
- **Validador de entidad y fecha** (si aplica)
- **Validador CAR y fecha** (si aplica)
- **Observaciones** de validadores

5.2 La información debe presentarse de manera clara y organizada, preferiblemente en formato de línea de tiempo.

### 6. Diferenciación visual por tipo de evento
6.1 El sistema debe usar códigos de color, iconos o badges para diferenciar:
- **Create** (Creación): Verde - Icono de "+"
- **Update** (Actualización): Azul - Icono de "editar"
- **Delete** (Eliminación): Rojo - Icono de "x" o "papelera"

6.2 También debe diferenciarse el estado de validación:
- Pendiente: Amarillo/Naranja
- Validado: Verde
- Rechazado: Rojo

### 7. Detalle de evento individual
7.1 El usuario debe poder hacer clic en un evento específico para ver su información completa.  
7.2 El detalle debe incluir:
- Todos los metadatos del evento
- **Para eventos create**: El valor_nuevo completo
- **Para eventos update**: Comparación entre valor_anterior y valor_nuevo (ver HU-128)
- Historial de validaciones
- Todas las observaciones registradas

### 8. Filtrado del historial
8.1 El sistema debe permitir filtrar el historial por:
- **Tipo de evento**: create, update, delete
- **Tabla**: acción, indicador_accion, indicador_accion_valor, adjuntos
- **Estado de validación**: pendiente, validado, rechazado
- **Rango de fechas**
- **Usuario que creó**

8.2 Los filtros deben ser combinables y actualizarse dinámicamente.

### 9. Búsqueda dentro del historial
9.1 El usuario debe poder buscar eventos específicos mediante:
- Búsqueda por texto en observaciones
- Búsqueda por nombre de validador
- Búsqueda por contenido de valores (en valor_anterior o valor_nuevo)

9.2 Los resultados de búsqueda deben resaltarse en el historial.

### 10. Exportación del historial
10.1 El sistema debe permitir exportar el historial completo o filtrado a formatos:
- **PDF**: Para documentación formal y auditorías
- **Excel/CSV**: Para análisis de datos
- **JSON**: Para procesamiento automatizado

10.2 La exportación debe incluir toda la información visible en la interfaz, con marca de agua indicando usuario que exportó y fecha.

### 11. Visualización de contexto
11.1 Para eventos en tablas relacionadas, el sistema debe mostrar el contexto:
- Si es un evento sobre **indicador_accion**, mostrar qué acción padre está asociada
- Si es un evento sobre **adjunto**, indicar a qué registro pertenece

11.2 Debe poder navegarse desde el evento hijo a la información del padre.

### 12. Estadísticas del historial
12.1 El sistema debe mostrar un resumen con estadísticas:
- Total de eventos en el historial
- Cantidad por tipo (create, update, delete)
- Cantidad por estado de validación
- Cantidad de eventos rechazados
- Tiempo promedio de validación

12.2 Las estadísticas pueden presentarse en formato de cards, gráficos o tabla resumen.

### 13. Línea de tiempo visual
13.1 Opcionalmente, el sistema puede presentar el historial como una línea de tiempo gráfica.  
13.2 La línea de tiempo debe:
- Mostrar eventos en orden cronológico
- Usar íconos y colores para diferenciar tipos
- Permitir hacer clic en eventos para ver detalles
- Mostrar hitos importantes (primera validación, validación completa, rechazos)

### 14. Comparación entre versiones
14.1 Para eventos tipo update, el usuario debe poder comparar fácilmente diferentes versiones del registro.  
14.2 El sistema debe resaltar los campos que cambiaron entre una versión y otra (ver HU-128).

### 15. Auditoría completa
15.1 El historial debe servir como herramienta de auditoría completa, permitiendo:
- Reconstruir el estado del registro en cualquier momento del tiempo
- Identificar quién hizo qué cambio y cuándo
- Ver qué cambios fueron aprobados o rechazados y por quién
- Detectar patrones de cambios o problemas recurrentes

### 16. Performance con historiales extensos
16.1 Si una acción tiene muchos eventos, el sistema debe:
- Implementar paginación para evitar cargas pesadas
- Permitir cargar eventos en lotes (ej: mostrar los últimos 20, opción para cargar más)
- Mantener rendimiento óptimo incluso con cientos de eventos

### 17. Eventos relacionados en cascada
17.1 Si se consulta el historial de una acción, el sistema debe mostrar opcionalmente:
- Solo eventos directos sobre la acción
- Eventos sobre la acción y todas sus tablas dependientes (opción por defecto)

17.2 Debe haber un toggle o filtro para alternar entre estas vistas.

---

### Resultado esperado

Un **módulo de consulta de historial** completo y funcional que permita a usuarios autorizados visualizar todos los eventos asociados a una acción, con información detallada de cada cambio, estados de validación, usuarios involucrados y observaciones, facilitando la auditoría, trazabilidad y comprensión completa del ciclo de vida de la información del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-127.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-127.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-127.png)
