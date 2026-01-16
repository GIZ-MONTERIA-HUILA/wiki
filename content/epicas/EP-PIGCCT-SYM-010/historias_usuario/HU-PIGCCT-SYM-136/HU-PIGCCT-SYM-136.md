# HU-PIGCCT-SYM-136  
## Épica: Autenticación, gestión de usuarios, y control de acceso del sistema PIGCCT  
### Definir roles del sistema

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** arquitecto del sistema.  
> **Quiero:** definir claramente los roles del sistema PIGCCT y sus responsabilidades.  
> **Para:** establecer un modelo de control de acceso que garantice segregación de funciones, seguridad de la información y flujos de trabajo apropiados.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Roles por entidad

El sistema debe implementar los siguientes roles específicos para usuarios de entidades territoriales:

#### 1.1 Usuario Registrador

**Descripción**: Usuario encargado de crear y actualizar información del PIGCCT en su entidad.

**Responsabilidades**:
- Crear acciones del PIGCCT de su entidad
- Actualizar acciones existentes (propias o de su entidad)
- Registrar indicadores asociados a las acciones
- Registrar valores de indicadores
- Cargar adjuntos y documentos soporte
- Generar eventos de validación al crear o modificar registros
- Consultar información validada de su entidad

**Restricciones**:
- No puede validar eventos (ni propios ni de otros)
- Solo puede ver y editar información de su propia entidad
- No puede acceder a información de otras entidades
- No puede modificar catálogos del sistema
- No puede administrar usuarios

**Permisos técnicos**:
- CREATE en tablas: accion, indicador_accion, indicador_accion_valor, adjuntos
- UPDATE en registros propios o de su entidad (genera evento)
- READ en información validada de su entidad
- No tiene permisos de DELETE (solo marca como inactivo)

---

#### 1.2 Usuario Validador de Entidad

**Descripción**: Usuario encargado de validar la información registrada por usuarios de su misma entidad.

**Responsabilidades**:
- Revisar eventos pendientes de validación de su entidad
- Aprobar o rechazar eventos con observaciones
- Validar que la información cumpla con criterios técnicos y de calidad
- Comunicar observaciones a los registradores
- Consultar historial de eventos validados

**Restricciones**:
- No puede crear nuevas acciones o registros
- No puede validar sus propios registros (si él mismo los creó)
- Solo valida información de su propia entidad
- No puede modificar registros directamente
- No puede realizar validación de segundo nivel (CAR)

**Permisos técnicos**:
- READ en eventos con estado "en validación por entidad" de su entidad
- UPDATE en tabla evento: campos validado_por_entidad, fch_validacion_entidad, observacion, estado_registro
- No tiene permisos de CREATE ni DELETE en tablas principales

**Regla especial**: 
- Si un validador es también registrador, no puede validar eventos que él mismo generó

---

### 2. Roles transversales

#### 2.1 Usuario Validador CAR

**Descripción**: Usuario de una Corporación Autónoma Regional encargado de validar información ya aprobada por las entidades territoriales.

**Responsabilidades**:
- Revisar eventos ya validados por entidades bajo su jurisdicción regional
- Realizar validación de segundo nivel (control regional)
- Aprobar o rechazar eventos previamente validados por entidades
- Garantizar coherencia regional de la información del PIGCCT
- Generar reportes consolidados regionales

**Restricciones**:
- Solo puede validar eventos que cumplan: validado_por_entidad = true
- No puede crear acciones directamente
- No puede validar sin aprobación previa de la entidad
- No puede modificar información directamente

**Permisos técnicos**:
- READ en eventos con estado "validado por entidad - pendiente CAR" de su región
- UPDATE en tabla evento: campos validado_por_car, fch_validacion_car, observacion, estado_registro
- READ en información de todas las entidades bajo su jurisdicción
- No tiene permisos de CREATE ni DELETE en tablas principales

**Ámbito**: 
- Puede ver y validar información de múltiples entidades territoriales (municipios, departamentos) dentro de su región

---

#### 2.2 Administrador del Sistema

**Descripción**: Usuario con máximos privilegios para administrar y configurar el sistema PIGCCT.

**Responsabilidades**:
- Crear, editar y eliminar usuarios del sistema
- Asignar roles y permisos a usuarios
- Administrar catálogos maestros (entidades, tipos, dominios)
- Configurar parámetros del sistema
- Gestionar copias de seguridad
- Revisar logs de auditoría y seguridad
- Desbloquear cuentas de usuario
- Realizar mantenimiento del sistema

**Privilegios especiales**:
- Acceso completo a todas las entidades y sus datos
- Puede ver información en cualquier estado de validación
- Puede editar registros validados en casos excepcionales (con auditoría)
- Puede ejecutar operaciones masivas
- Acceso a panel de administración de Strapi

**Restricciones**:
- Debe justificar ediciones directas de registros validados
- Sus acciones son registradas exhaustivamente en auditoría
- Idealmente no debe participar en validación de contenido (separación de funciones)

**Permisos técnicos**:
- CREATE, READ, UPDATE, DELETE en todas las tablas
- Acceso completo a configuración de Strapi
- Ejecución de scripts y mantenimiento de base de datos

---

#### 2.3 Usuario Consulta

**Descripción**: Usuario con acceso de solo lectura para consultar información validada del PIGCCT.

**Responsabilidades**:
- Consultar información completamente validada
- Generar reportes y exportaciones
- Visualizar dashboards y estadísticas
- Acceder a información pública del PIGCCT

**Restricciones**:
- No puede crear, editar ni eliminar ninguna información
- No puede validar eventos
- Solo ve información completamente validada (validado_por_entidad = true AND validado_por_car = true)
- No accede a información en proceso de validación
- No ve información rechazada ni pendiente

**Permisos técnicos**:
- READ ONLY en todas las tablas con filtro de validación completa
- Puede exportar reportes (Excel, PDF, CSV)
- No tiene permisos de CREATE, UPDATE ni DELETE

**Casos de uso**:
- Ciudadanos consultando información pública
- Investigadores accediendo a datos del PIGCCT
- Entidades consultoras realizando análisis
- Medios de comunicación accediendo a información oficial

---

### 3. Matriz de permisos por rol

El sistema debe implementar la siguiente matriz de permisos:

| Funcionalidad | Registrador | Validador Entidad | Validador CAR | Administrador | Consulta |
|--------------|-------------|-------------------|---------------|---------------|----------|
| Crear acción | ✓ | ✗ | ✗ | ✓ | ✗ |
| Editar acción | ✓ (propia) | ✗ | ✗ | ✓ | ✗ |
| Ver acción validada | ✓ | ✓ | ✓ | ✓ | ✓ |
| Ver acción pendiente | ✓ (propia) | ✓ | ✗ | ✓ | ✗ |
| Enviar a validación | ✓ | ✗ | ✗ | ✓ | ✗ |
| Validar (entidad) | ✗ | ✓ | ✗ | ✓ | ✗ |
| Validar (CAR) | ✗ | ✗ | ✓ | ✓ | ✗ |
| Administrar usuarios | ✗ | ✗ | ✗ | ✓ | ✗ |
| Ver logs auditoría | ✗ | ✗ | ✗ | ✓ | ✗ |
| Exportar reportes | ✗ | ✓ | ✓ | ✓ | ✓ |
| Administrar catálogos | ✗ | ✗ | ✗ | ✓ | ✗ |

---

### 4. Configuración en Strapi

4.1 Cada rol debe estar definido en Strapi con:
- **Name**: Nombre descriptivo del rol
- **Description**: Descripción detallada de responsabilidades
- **Type**: Identificador único del rol (ej: "registrador", "validador_entidad")
- **Permissions**: Permisos específicos sobre endpoints de la API

4.2 Los permisos en Strapi deben configurarse por:
- Controller/Action
- Content-Type
- Campos específicos (fine-grained permissions)

---

### 5. Segregación de funciones

5.1 El sistema debe garantizar **segregación de funciones**:
- Quien registra no puede validar
- Quien valida no puede crear directamente
- La validación requiere dos niveles (entidad + CAR)

5.2 Esto previene conflictos de interés y garantiza calidad de la información.

---

### 6. Documentación de roles

6.1 El sistema debe incluir documentación completa de cada rol accesible desde:
- Manual de usuario
- Sistema de ayuda integrado
- Página de perfil de usuario (mostrando su rol y permisos)

---

### Resultado esperado

Un **sistema de roles claramente definido** con responsabilidades, permisos y restricciones específicas para cada tipo de usuario, implementado en Strapi, validado en backend, y aplicado consistentemente en toda la aplicación, garantizando segregación de funciones apropiada y control de acceso basado en roles.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-136.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-136.png)
