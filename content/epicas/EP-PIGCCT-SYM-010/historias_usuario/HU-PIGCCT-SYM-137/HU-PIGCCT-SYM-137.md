# HU-PIGCCT-SYM-137  
## Épica: Autenticación, gestión de usuarios, y control de acceso del sistema PIGCCT  
### Restringir acceso por rol

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de control de acceso.  
> **Quiero:** controlar el acceso a funcionalidades según el rol del usuario.  
> **Para:** garantizar segregación de funciones y que cada usuario solo pueda realizar operaciones correspondientes a su rol.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Control de acceso basado en roles
1.1 El sistema debe implementar **RBAC (Role-Based Access Control)** en todos los niveles:
- Frontend: Ocultar/deshabilitar funcionalidades no permitidas
- Backend: Validar permisos antes de ejecutar operaciones
- Base de datos: Aplicar filtros de seguridad en consultas

1.2 Ningún usuario debe poder acceder a funcionalidades fuera de su rol, ni mediante interfaz ni mediante API directa.

### 2. Restricciones para Usuario Registrador

#### 2.1 Funcionalidades permitidas:
- **Crear acciones**: Puede crear nuevas acciones del PIGCCT para su entidad
- **Editar acciones**: Puede editar acciones propias o de su entidad (genera evento update)
- **Registrar indicadores**: Puede crear y actualizar indicadores asociados a acciones
- **Cargar adjuntos**: Puede subir documentos y archivos soporte
- **Enviar a validación**: Puede enviar sus eventos pendientes a validación
- **Consultar propios**: Puede ver sus registros en cualquier estado
- **Consultar validados**: Puede ver registros completamente validados de su entidad

#### 2.2 Funcionalidades restringidas:
- **No puede validar eventos**: Ni suyos ni de otros usuarios
- **No puede aprobar/rechazar**: No tiene acceso a módulo de validación
- **No puede acceder a otras entidades**: Solo ve información de su entidad
- **No puede administrar usuarios**: No tiene acceso a gestión de usuarios
- **No puede modificar catálogos**: No puede editar tablas maestras del sistema

#### 2.3 Implementación técnica:
```javascript
// Ejemplo de validación en backend
if (userRole === 'registrador') {
  // Permitir crear acción
  if (action === 'createAccion' && accion.entidad_id === user.entidad_id) {
    return allowed;
  }
  // Bloquear validación
  if (action === 'validarEvento') {
    return forbidden('Los registradores no pueden validar eventos');
  }
}
```

---

### 3. Restricciones para Usuario Validador de Entidad

#### 3.1 Funcionalidades permitidas:
- **Validar eventos**: Puede aprobar o rechazar eventos de su entidad
- **Agregar observaciones**: Puede comentar sobre eventos revisados
- **Consultar eventos pendientes**: Ve lista de eventos en validación de su entidad
- **Consultar historial**: Puede ver eventos que ha validado
- **Consultar validados**: Puede ver información completamente validada de su entidad
- **Exportar reportes**: Puede generar reportes de su entidad

#### 3.2 Funcionalidades restringidas:
- **No puede crear acciones**: No tiene acceso a formularios de creación
- **No puede editar registros**: No puede modificar acciones directamente
- **No puede validar propios registros**: Si él creó un registro, no puede validarlo
- **No puede validar nivel CAR**: Solo realiza validación de primer nivel
- **No puede acceder a otras entidades**: Solo valida de su propia entidad

#### 3.3 Regla especial - Auto-validación:
```javascript
// El validador no puede validar eventos que él mismo generó
if (userRole === 'validador_entidad') {
  if (evento.creado_por === user.id) {
    return forbidden('No puedes validar tus propios registros');
  }
}
```

---

### 4. Restricciones para Usuario Validador CAR

#### 4.1 Funcionalidades permitidas:
- **Validar eventos aprobados**: Puede validar eventos con validado_por_entidad = true
- **Revisión regional**: Valida información de múltiples entidades bajo su jurisdicción
- **Consultar multi-entidad**: Ve información de todas las entidades de su región
- **Generar reportes regionales**: Puede exportar consolidados regionales
- **Agregar observaciones**: Puede comentar validaciones

#### 4.2 Funcionalidades restringidas:
- **No puede crear acciones**: No tiene acceso a formularios de registro
- **No puede validar sin aprobación previa**: Solo valida eventos ya aprobados por entidad
- **No puede saltar validación entidad**: Debe verificar validado_por_entidad = true
- **No puede administrar usuarios**: No gestiona cuentas de usuario

#### 4.3 Validación de condición previa:
```javascript
// Solo puede validar si ya fue validado por entidad
if (userRole === 'validador_car') {
  if (!evento.validado_por_entidad) {
    return forbidden('Este evento debe ser validado primero por la entidad');
  }
}
```

---

### 5. Restricciones para Administrador del Sistema

#### 5.1 Funcionalidades permitidas:
- **Acceso completo**: Puede realizar cualquier operación del sistema
- **Administrar usuarios**: Crear, editar, bloquear, desbloquear usuarios
- **Configurar sistema**: Modificar parámetros y configuraciones
- **Ver todas las entidades**: Acceso a información de todas las entidades
- **Editar validados**: Puede modificar registros validados (con justificación)
- **Revisar auditoría**: Acceso completo a logs y auditoría

#### 5.2 Responsabilidades especiales:
- Debe justificar ediciones de registros validados
- Sus acciones son auditadas exhaustivamente
- Debe usar permisos responsablemente

---

### 6. Restricciones para Usuario Consulta

#### 6.1 Funcionalidades permitidas:
- **Consultar información validada**: Solo registros con validación completa
- **Exportar reportes**: Puede generar y descargar reportes
- **Ver dashboards**: Acceso a visualizaciones y estadísticas públicas
- **Buscar y filtrar**: Puede usar funciones de búsqueda

#### 6.2 Funcionalidades restringidas:
- **No puede crear nada**: Sin acceso a formularios de creación
- **No puede editar nada**: Sin acceso a edición
- **No puede validar**: Sin acceso a módulos de validación
- **No ve información pendiente**: Solo ve información completamente validada
- **No puede eliminar**: Sin permisos de eliminación

#### 6.3 Filtro automático:
```sql
-- Automáticamente aplicado en todas las consultas
WHERE validado_por_entidad = true 
  AND validado_por_car = true
```

---

### 7. Control en el Frontend

7.1 El frontend debe **adaptar la interfaz** según el rol:
- Ocultar opciones de menú no disponibles
- Deshabilitar botones de acciones restringidas
- No mostrar formularios sin permisos
- Mostrar mensajes informativos si intenta acceder a función restringida

7.2 Ejemplo de menú adaptativo:
```javascript
// Usuario Registrador ve:
- Mis Acciones
- Crear Acción
- Mis Eventos Pendientes
- Información Validada

// Usuario Validador ve:
- Eventos por Validar
- Mis Validaciones
- Historial
- Información Validada

// Usuario Consulta ve:
- Consultar Información
- Reportes
- Estadísticas
```

---

### 8. Control en el Backend

8.1 El backend debe validar permisos en cada petición:
- Verificar rol del usuario en el token JWT
- Validar que el endpoint/acción está permitida para ese rol
- Aplicar filtros de entidad y validación según corresponda
- Rechazar operaciones no autorizadas con HTTP 403

8.2 Middleware de validación de permisos:
```javascript
function checkPermission(requiredRole) {
  return (req, res, next) => {
    if (!req.user || req.user.role !== requiredRole) {
      return res.status(403).json({
        error: 'No tienes permisos para esta operación'
      });
    }
    next();
  };
}
```

---

### 9. Mensajes de error apropiados

9.1 Cuando un usuario intenta acceder a funcionalidad restringida, mostrar mensajes claros:
- **Registrador intenta validar**: "Los usuarios registradores no pueden validar eventos. Contacta a un validador de tu entidad."
- **Validador intenta crear**: "Los validadores no pueden crear acciones directamente. Contacta a un registrador."
- **Consulta intenta editar**: "Tu cuenta de consulta es de solo lectura. Contacta al administrador si necesitas permisos adicionales."

---

### 10. Registro de intentos de acceso no autorizado

10.1 El sistema debe registrar en logs de seguridad:
- Usuario que intentó la acción
- Acción denegada
- Rol del usuario
- Fecha y hora
- IP de origen

10.2 Múltiples intentos de acceso no autorizado deben generar alertas de seguridad.

---

### 11. Testing de restricciones

11.1 El sistema debe incluir tests automatizados que verifiquen:
- Cada rol solo puede acceder a sus funciones permitidas
- Intentos de acceso no autorizado son bloqueados
- Mensajes de error son apropiados
- Logs de seguridad se generan correctamente

---

### 12. Excepciones documentadas

12.1 Cualquier excepción a las restricciones estándar debe estar:
- Documentada claramente
- Aprobada por el equipo de seguridad
- Implementada con controles adicionales
- Registrada exhaustivamente en auditoría

---

### Resultado esperado

Un **sistema con control de acceso robusto** que restringe funcionalidades según el rol del usuario, implementado en frontend (UI adaptativa), backend (validación de permisos) y base de datos (filtros de seguridad), con mensajes de error apropiados, registro de intentos no autorizados, y garantía de segregación de funciones.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-137.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-137.png)
