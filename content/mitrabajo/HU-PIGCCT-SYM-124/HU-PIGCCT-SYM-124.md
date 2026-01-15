# HU-PIGCCT-SYM-124  
## Épica: Gestión de eventos y validación de información del PIGCCT  
### Condicionar visualización por validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión del PIGCCT.  
> **Quiero:** mostrar los registros solo si sus eventos están completamente aprobados.  
> **Para:** garantizar que únicamente información validada por la entidad y la CAR sea utilizada en reportes, consultas y análisis del sistema.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Condición de visibilidad completa
1.1 El sistema debe aplicar la siguiente regla para determinar si un registro es visible y usable:
```
validado_por_entidad = true AND validado_por_car = true
```

1.2 Solo los registros que cumplan esta condición deben estar disponibles para:
- Consultas generales
- Reportes oficiales
- Análisis y estadísticas
- Exportaciones de datos
- Visualizaciones en mapas o dashboards

### 2. Aplicación en tablas principales
2.1 La regla de visibilidad debe aplicarse a las siguientes tablas:
- **acción**: Solo acciones con eventos completamente validados deben mostrarse.
- **indicador_accion**: Solo indicadores con eventos validados.
- **indicador_accion_valor**: Solo valores con eventos validados.
- **adjuntos**: Solo adjuntos con eventos validados.

2.2 La validación debe propagarse desde el evento asociado hacia el registro en cada tabla.

### 3. Implementación en consultas
3.1 Todas las consultas SELECT que recuperen información de estas tablas deben incluir automáticamente un JOIN o filtro con la tabla **evento** para verificar:
```sql
WHERE evento.validado_por_entidad = true 
  AND evento.validado_por_car = true
```

3.2 Esta condición debe aplicarse de manera consistente en toda la aplicación.

### 4. Excepciones por rol de usuario
4.1 El sistema debe permitir excepciones a la regla de visibilidad según el rol del usuario:
- **Administradores**: Pueden ver todos los registros independientemente de su estado de validación.
- **Usuario que registra**: Puede ver sus propios registros pendientes (ver HU-125).
- **Validadores**: Pueden ver registros en proceso de validación según su nivel (ver HU-122 y HU-123).

4.2 La lógica de filtrado debe considerar el contexto del usuario autenticado.

### 5. Indicador visual de estado de validación
5.1 En las interfaces donde los administradores o usuarios con permisos especiales vean registros no completamente validados, el sistema debe mostrar claramente el estado:
- **Pendiente de envío**
- **En validación por entidad**
- **Validado por entidad - pendiente CAR**
- **Rechazado por entidad**
- **Rechazado por CAR**
- **Completamente validado** (badge verde o indicador positivo)

5.2 Los registros completamente validados deben distinguirse visualmente de los demás.

### 6. Impacto en relaciones entre tablas
6.1 Si una **acción** no está completamente validada, entonces:
- Sus **indicador_accion** asociados no deben mostrarse.
- Sus **adjuntos** asociados no deben mostrarse.
- Sus **indicador_accion_valor** asociados no deben mostrarse.

6.2 La visibilidad debe ser jerárquica desde la acción hacia sus dependencias.

### 7. Reportes y exportaciones
7.1 Los reportes oficiales del sistema deben:
- Incluir **únicamente** registros completamente validados.
- Mostrar un disclaimer indicando que solo se incluyen datos validados.
- Opcionalmente, mostrar la fecha del último evento validado incluido en el reporte.

7.2 Las exportaciones a formatos externos (Excel, CSV, GeoJSON) deben aplicar el mismo filtro de validación.

### 8. APIs y servicios web
8.1 Si el sistema expone APIs o servicios web, estos deben:
- Por defecto, retornar únicamente registros completamente validados.
- Opcionalmente, permitir un parámetro especial (requiriendo autenticación y permisos) para incluir registros no validados.

### 9. Notificación de registros ocultos
9.1 Si un usuario busca un registro específico que existe pero no está completamente validado, el sistema debe:
- No mostrar el registro en resultados de búsqueda general.
- Si el usuario es el creador, permitirle verlo en su sección de "Mis registros pendientes".
- Opcionalmente, mostrar un mensaje genérico como "El registro está en proceso de validación".

### 10. Consistencia en toda la aplicación
10.1 La regla de visibilidad debe aplicarse consistentemente en:
- Listas y tablas de datos
- Formularios de selección (dropdowns, autocomplete)
- Gráficos y visualizaciones
- Mapas interactivos
- Búsquedas y filtros
- Contadores y estadísticas

10.2 No debe haber ninguna parte del sistema donde se muestren registros no validados a usuarios sin permisos especiales.

### 11. Performance y optimización
11.1 La implementación de esta regla debe estar optimizada para no afectar el rendimiento del sistema.  
11.2 Se recomienda:
- Crear índices en los campos validado_por_entidad y validado_por_car de la tabla evento.
- Considerar el uso de vistas materializadas para consultas frecuentes.
- Implementar caché para las consultas de registros validados.

### 12. Auditoría de acceso
12.1 El sistema debe registrar en logs cuando usuarios con permisos especiales accedan a registros no completamente validados.  
12.2 El log debe incluir:
- Usuario que accede
- Registro accedido
- Estado de validación del registro
- Fecha y hora de acceso
- Acción realizada (consulta, edición, etc.)

### 13. Documentación técnica
13.1 Debe existir documentación técnica clara sobre:
- La regla de visibilidad y su implementación.
- Cómo agregar la condición en nuevas consultas.
- Excepciones por rol y cómo implementarlas.
- Ejemplos de código para consultas correctas.

---

### Resultado esperado

Un **sistema que muestra consistentemente** solo registros con validado_por_entidad = true AND validado_por_car = true en todas las consultas, reportes y visualizaciones públicas, garantizando la calidad e integridad de la información utilizada, con excepciones controladas por roles para usuarios que necesiten ver registros en proceso de validación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-124.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-124.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-124.png)
