# HU-PIGCCT-SYM-138  
## Épica: Autenticación, gestión de usuarios, y control de acceso del sistema PIGCCT  
### Controlar visibilidad de información

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión de información.  
> **Quiero:** mostrar información según el estado de validación y rol del usuario.  
> **Para:** garantizar que solo se utilice información validada y que cada usuario vea solo lo que corresponde a su ámbito de responsabilidad.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Principio de visibilidad por validación

1.1 El sistema debe aplicar el principio fundamental:
```
Información visible públicamente = validado_por_entidad = true AND validado_por_car = true
```

1.2 Esta regla se aplica a todos los usuarios excepto en casos específicos según su rol.

---

### 2. Visibilidad para Usuario Registrador

#### 2.1 Información que PUEDE ver:
- **Sus propios registros**: En cualquier estado (pendiente, en validación, rechazado, validado)
- **Registros de su entidad validados**: Información completamente validada de su entidad
- **Eventos propios**: Historial completo de sus eventos y su estado

#### 2.2 Información que NO PUEDE ver:
- Registros pendientes de otros usuarios de su entidad
- Registros en validación de otros usuarios
- Registros rechazados de otros usuarios
- Información de otras entidades
- Observaciones privadas de validadores (solo las dirigidas a él)

#### 2.3 Filtro aplicado:
```sql
-- Registros propios en cualquier estado
WHERE creado_por = [user_id]
OR
-- Registros validados de su entidad
(entidad_id = [user_entidad] 
 AND validado_por_entidad = true 
 AND validado_por_car = true)
```

---

### 3. Visibilidad para Usuario Validador de Entidad

#### 3.1 Información que PUEDE ver:
- **Eventos pendientes de validación**: De su entidad, en estado "en validación por entidad"
- **Eventos que ha validado**: Historial de sus validaciones (aprobados y rechazados)
- **Registros validados de su entidad**: Información completamente validada
- **Registros asociados a eventos**: Para contexto de validación

#### 3.2 Información que NO PUEDE ver:
- Eventos pendientes de envío (aún no enviados a validación)
- Eventos de otras entidades
- Validaciones de otros validadores (solo resultados finales)
- Información de otras entidades

#### 3.3 Filtro aplicado:
```sql
-- Eventos pendientes de su entidad
WHERE evento.entidad_id = [user_entidad]
  AND evento.estado_registro = 'en_validacion_entidad'
OR
-- Eventos ya validados por él
evento.validado_por_entidad_user_id = [user_id]
OR
-- Registros completamente validados de su entidad
(registro.entidad_id = [user_entidad]
 AND registro.validado_por_entidad = true
 AND registro.validado_por_car = true)
```

---

### 4. Visibilidad para Usuario Validador CAR

#### 4.1 Información que PUEDE ver:
- **Eventos validados por entidades**: En estado "validado por entidad - pendiente CAR"
- **Multi-entidad**: De todas las entidades bajo su jurisdicción regional
- **Eventos que ha validado**: Historial completo de sus validaciones CAR
- **Información consolidada regional**: Datos de múltiples entidades

#### 4.2 Información que NO PUEDE ver:
- Eventos que no han sido validados por la entidad
- Eventos en estado inicial o rechazados por entidad
- Información de regiones fuera de su jurisdicción

#### 4.3 Filtro aplicado:
```sql
-- Eventos pendientes de validación CAR en su región
WHERE evento.region_car = [user_region]
  AND evento.validado_por_entidad = true
  AND evento.estado_registro = 'pendiente_validacion_car'
OR
-- Eventos validados por él
evento.validado_por_car_user_id = [user_id]
OR
-- Información completamente validada de su región
(registro.region_car = [user_region]
 AND registro.validado_por_car = true)
```

---

### 5. Visibilidad para Administrador del Sistema

#### 5.1 Información que PUEDE ver:
- **Todo**: Información en cualquier estado de validación
- **Todas las entidades**: Sin restricción de entidad
- **Todos los eventos**: Pendientes, en proceso, validados, rechazados
- **Logs completos**: Auditoría y seguridad
- **Configuraciones**: Parámetros del sistema

#### 5.2 Indicadores visuales:
- El sistema debe mostrar claramente el estado de cada registro al administrador
- Usar colores/badges para diferenciar estados
- Advertir al administrador cuando está viendo información no validada

---

### 6. Visibilidad para Usuario Consulta

#### 6.1 Información que PUEDE ver:
- **Solo información completamente validada**: validado_por_entidad = true AND validado_por_car = true
- **Todas las entidades**: Sin restricción de entidad (información pública)
- **Reportes y estadísticas**: Basados en información validada

#### 6.2 Información que NO PUEDE ver:
- Eventos en cualquier estado
- Información pendiente de validación
- Información rechazada
- Observaciones de validadores
- Logs de auditoría

#### 6.3 Filtro aplicado:
```sql
-- Solo información completamente validada
WHERE validado_por_entidad = true
  AND validado_por_car = true
```

---

### 7. Visibilidad en cascada (tablas relacionadas)

7.1 Si una **acción** no cumple con el criterio de visibilidad del usuario:
- Sus **indicadores** asociados tampoco son visibles
- Sus **valores de indicadores** tampoco son visibles
- Sus **adjuntos** tampoco son visibles

7.2 La visibilidad se propaga jerárquicamente desde la acción hacia sus dependencias.

---

### 8. Implementación en consultas

8.1 Todas las consultas SELECT del sistema deben incluir automáticamente filtros según:
- Rol del usuario
- Entidad del usuario
- Estado de validación requerido para ese rol

8.2 Ejemplo de implementación en ORM:
```javascript
// Función helper que aplica filtros automáticos
function applyVisibilityFilter(query, user) {
  if (user.role === 'consulta') {
    query.where('validado_por_entidad', true)
         .where('validado_por_car', true);
  } else if (user.role === 'registrador') {
    query.where(function() {
      this.where('creado_por', user.id)
          .orWhere(function() {
            this.where('entidad_id', user.entidad_id)
                .where('validado_por_entidad', true)
                .where('validado_por_car', true);
          });
    });
  }
  // ... otros roles
  return query;
}
```

---

### 9. Contadores y estadísticas

9.1 Los contadores mostrados deben respetar las reglas de visibilidad:
- "Total de acciones" → Solo cuenta las visibles para ese usuario
- "Acciones pendientes" → Solo las pendientes visibles según rol
- "Eventos por validar" → Solo los que el usuario puede validar

9.2 No mostrar contadores de información no accesible para el usuario.

---

### 10. Búsquedas y filtros

10.1 Las funciones de búsqueda deben aplicar automáticamente filtros de visibilidad.  
10.2 Si un usuario busca un registro específico que existe pero no es visible para él:
- No mostrarlo en resultados
- No revelar su existencia
- Mostrar "No se encontraron resultados"

---

### 11. URLs directas y deep linking

11.1 Si un usuario intenta acceder a un registro mediante URL directa (ej: /accion/123):
- Validar que tiene permisos para ver ese registro
- Si no tiene permisos: mostrar error 403 o 404 (no revelar existencia)
- Registrar el intento en logs de seguridad

---

### 12. Exportaciones y reportes

12.1 Al exportar datos, aplicar los mismos filtros de visibilidad.  
12.2 El reporte debe incluir disclaimer indicando:
- Rol del usuario que genera el reporte
- Ámbito de información incluida (entidad, región, etc.)
- Fecha de generación

---

### 13. APIs y servicios web

13.1 Los endpoints de API deben aplicar filtros de visibilidad en el backend.  
13.2 Usar el token JWT para determinar rol y entidad del usuario.  
13.3 Nunca confiar en filtros del frontend para control de acceso.

---

### 14. Caché y performance

14.1 El sistema puede cachear resultados de consultas, pero debe:
- Cachear por usuario/rol para evitar fugas de información
- Invalidar caché al cambiar estado de validación
- No compartir caché entre usuarios con diferentes permisos

---

### 15. Indicadores visuales de estado

15.1 Para usuarios que ven información en múltiples estados (ej: administrador), mostrar claramente:
- Badge "Validado" (verde) para información completamente validada
- Badge "En validación" (amarillo) para información en proceso
- Badge "Pendiente" (naranja) para información sin enviar
- Badge "Rechazado" (rojo) para información rechazada

---

### 16. Mensajes informativos

16.1 Si un usuario no ve cierta información debido a filtros de visibilidad, opcionalmente mostrar:
- "Mostrando solo información validada" (para usuario consulta)
- "Mostrando solo registros de tu entidad" (para registrador)
- "X registros adicionales pendientes de validación" (para validador)

---

### 17. Testing de visibilidad

17.1 Implementar tests automatizados que verifiquen:
- Cada rol solo ve la información permitida
- Filtros de visibilidad se aplican correctamente
- No hay fugas de información entre usuarios
- URLs directas respetan restricciones

---

### Resultado esperado

Un **sistema que controla estrictamente la visibilidad de información** según el rol del usuario y el estado de validación de los datos, aplicando filtros automáticos en todas las consultas, protegiendo información pendiente o rechazada de usuarios sin permisos, y garantizando que solo información validada esté disponible públicamente.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-138.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-138.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-138.png)
