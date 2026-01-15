# HU-PIGCCT-SYM-140  
## Épica: Autenticación, gestión de usuarios, y control de acceso del sistema PIGCCT  
### Consideraciones técnicas de Strapi

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** equipo de desarrollo del sistema PIGCCT.  
> **Quiero:** documentar las consideraciones técnicas de integración con Strapi.  
> **Para:** establecer claramente la arquitectura de autenticación, roles, permisos y comunicación entre Strapi y el backend propio del sistema.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Arquitectura general

1.1 El sistema PIGCCT utiliza **Strapi como sistema de autenticación y gestión de usuarios**.  
1.2 La arquitectura consta de tres capas principales:
- **Strapi**: Gestión de usuarios, autenticación, roles y permisos
- **Backend propio**: Lógica de negocio, validaciones del PIGCCT, eventos
- **Frontend**: Aplicación web que consume ambos backends

```
┌─────────────┐
│  Frontend   │
└──────┬──────┘
       │
   ┌───┴────────────┐
   │                │
┌──▼───┐      ┌────▼────┐
│Strapi│◄────►│ Backend │
└──────┘      │  PIGCCT │
              └─────────┘
```

---

### 2. Gestión de usuarios en Strapi

2.1 Strapi gestiona la colección **users** con los siguientes campos estándar:
- `username`: Nombre de usuario único
- `email`: Correo electrónico único
- `password`: Contraseña hasheada (bcrypt)
- `confirmed`: Indica si el correo fue confirmado
- `blocked`: Indica si el usuario está bloqueado
- `role`: Referencia al rol asignado

2.2 Se deben agregar campos personalizados:
- `entidad_id`: Referencia a la entidad del usuario
- `nombre_completo`: Nombre completo del usuario
- `telefono`: Teléfono de contacto
- `cargo`: Cargo en la entidad
- `fecha_creacion`: Fecha de creación del usuario
- `ultimo_acceso`: Fecha del último inicio de sesión

---

### 3. Gestión de roles en Strapi

3.1 Los roles se definen en Strapi usando el plugin **Users & Permissions**.

3.2 Cada rol tiene configuración de:
- **Name**: Nombre descriptivo
- **Description**: Descripción del rol
- **Type**: Identificador único (ej: `registrador`, `validador_entidad`)
- **Permissions**: Permisos sobre endpoints de API

3.3 Los roles del sistema PIGCCT (ver HU-136) deben crearse en Strapi:
- Usuario Registrador
- Usuario Validador de Entidad
- Usuario Validador CAR
- Administrador del Sistema
- Usuario Consulta

---

### 4. Autenticación y generación de tokens

4.1 El proceso de autenticación utiliza el endpoint de Strapi:

**Request**:
```http
POST /api/auth/local
Content-Type: application/json

{
  "identifier": "usuario@entidad.gov.co",
  "password": "contraseña"
}
```

**Response exitosa**:
```json
{
  "jwt": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": 1,
    "username": "usuario",
    "email": "usuario@entidad.gov.co",
    "role": {
      "id": 2,
      "name": "Usuario Registrador",
      "type": "registrador"
    },
    "entidad_id": 5,
    "blocked": false,
    "confirmed": true
  }
}
```

---

### 5. Token JWT

5.1 Strapi genera un **token JWT** con la siguiente estructura:

```javascript
{
  "id": 1,  // ID del usuario
  "iat": 1673614245,  // Issued at (timestamp)
  "exp": 1676206245   // Expiration (timestamp)
}
```

5.2 El token debe incluirse en todas las peticiones subsiguientes:
```http
Authorization: Bearer [JWT_TOKEN]
```

5.3 El tiempo de expiración del token es configurable en Strapi (recomendado: 24 horas).

---

### 6. Validación de tokens en el backend

6.1 El **backend propio del PIGCCT** debe validar el token JWT en cada petición:

```javascript
// Middleware de validación
async function validateJWT(req, res, next) {
  const token = req.headers.authorization?.replace('Bearer ', '');
  
  if (!token) {
    return res.status(401).json({ error: 'Token no proporcionado' });
  }
  
  try {
    // Verificar el token usando la clave secreta de Strapi
    const decoded = jwt.verify(token, process.env.STRAPI_JWT_SECRET);
    
    // Consultar información del usuario desde Strapi
    const user = await fetchUserFromStrapi(decoded.id, token);
    
    // Agregar usuario al contexto de la petición
    req.user = user;
    next();
  } catch (error) {
    return res.status(401).json({ error: 'Token inválido o expirado' });
  }
}
```

---

### 7. Consulta de información del usuario

7.1 El backend PIGCCT debe consultar información completa del usuario desde Strapi:

```http
GET /api/users/me
Authorization: Bearer [JWT_TOKEN]
```

**Response**:
```json
{
  "id": 1,
  "username": "usuario",
  "email": "usuario@entidad.gov.co",
  "role": {
    "id": 2,
    "name": "Usuario Registrador",
    "type": "registrador",
    "permissions": {
      "api::accion.accion": {
        "create": true,
        "update": true,
        "delete": false
      }
    }
  },
  "entidad_id": 5,
  "nombre_completo": "Juan Pérez"
}
```

---

### 8. Permisos en Strapi

8.1 Strapi maneja permisos granulares por:
- **Controller**: Controlador de la API
- **Action**: Acción específica (find, findOne, create, update, delete)
- **Role**: Rol que tiene el permiso

8.2 Ejemplo de configuración de permisos en Strapi:

```javascript
// Registrador puede crear acciones
{
  "controller": "accion",
  "action": "create",
  "enabled": true,
  "policy": "",
  "role": "registrador"
}

// Validador NO puede crear acciones
{
  "controller": "accion",
  "action": "create",
  "enabled": false,
  "role": "validador_entidad"
}
```

---

### 9. Reglas de negocio en el backend PIGCCT

9.1 El **backend propio** implementa reglas de negocio adicionales que Strapi no maneja:

- **Filtrado por entidad**: Solo mostrar información de la entidad del usuario
- **Validación de eventos**: Lógica de generación y validación de eventos
- **Flujo de aprobación**: Validación entidad → Validación CAR
- **Auto-validación**: Impedir que usuarios validen sus propios registros
- **Visibilidad por estado**: Mostrar solo información validada según rol

9.2 Estas reglas se validan después de verificar el token y permisos de Strapi.

---

### 10. Flujo de autenticación completo

```
1. Usuario envía credenciales al frontend
2. Frontend envía credenciales a Strapi
3. Strapi valida y retorna JWT + info usuario
4. Frontend almacena JWT (localStorage/sessionStorage)
5. Frontend incluye JWT en todas las peticiones
6. Backend PIGCCT valida JWT con clave de Strapi
7. Backend consulta info completa del usuario (si es necesario)
8. Backend aplica reglas de negocio propias
9. Backend retorna respuesta al frontend
```

---

### 11. Sincronización de datos

11.1 Mantener sincronización entre:
- **Usuarios en Strapi**: Fuente de verdad para autenticación
- **Información adicional en BD propia**: Entidad, datos de contacto, metadata

11.2 Al crear usuario:
```javascript
// 1. Crear en Strapi
const strapiUser = await strapi.createUser({...});

// 2. Guardar info adicional en BD propia
await db.user_metadata.create({
  user_id: strapiUser.id,
  entidad_id: entidad,
  cargo: cargo,
  // ...
});
```

---

### 12. Configuración de Strapi

12.1 Variables de entorno necesarias:

```env
# Strapi
STRAPI_URL=https://strapi.pigcct.gov.co
STRAPI_API_TOKEN=token_admin_strapi
STRAPI_JWT_SECRET=secret_para_validar_jwt

# Backend PIGCCT
DATABASE_URL=postgres://...
JWT_EXPIRATION=24h
```

---

### 13. Endpoints consumidos de Strapi

El backend PIGCCT consume los siguientes endpoints de Strapi:

- `POST /api/auth/local` - Autenticación
- `POST /api/auth/forgot-password` - Recuperación de contraseña
- `POST /api/auth/reset-password` - Restablecer contraseña
- `GET /api/users/me` - Información del usuario autenticado
- `GET /api/users/:id` - Información de un usuario específico
- `PUT /api/users/:id` - Actualizar usuario
- `GET /api/users-permissions/roles` - Listar roles

---

### 14. Manejo de errores de Strapi

14.1 El backend debe manejar errores comunes de Strapi:

```javascript
try {
  const response = await strapi.authenticate(credentials);
} catch (error) {
  if (error.response?.status === 400) {
    // Credenciales inválidas
    return 'Usuario o contraseña incorrectos';
  } else if (error.response?.status === 429) {
    // Demasiados intentos
    return 'Demasiados intentos. Intenta más tarde';
  } else {
    // Error del servidor
    return 'Error de conexión. Intenta nuevamente';
  }
}
```

---

### 15. Webhooks de Strapi

15.1 Opcionalmente, configurar webhooks en Strapi para notificar al backend PIGCCT cuando:
- Se crea un usuario
- Se actualiza un usuario
- Se elimina un usuario
- Se cambia el rol de un usuario

15.2 Esto permite mantener sincronización en tiempo real.

---

### 16. Testing de integración

16.1 Implementar tests que verifiquen:
- Autenticación exitosa con Strapi
- Validación correcta de tokens JWT
- Consulta de información de usuario
- Manejo de tokens expirados
- Manejo de usuarios bloqueados

---

### 17. Documentación técnica

17.1 Mantener documentación actualizada sobre:
- Arquitectura de autenticación
- Flujo de tokens
- Configuración de roles en Strapi
- Endpoints disponibles
- Reglas de negocio adicionales del backend

---

### 18. Migración y respaldos

18.1 Implementar proceso de respaldo de:
- Usuarios de Strapi
- Configuración de roles y permisos
- Metadata adicional de BD propia

18.2 Proceso de migración para actualizar usuarios en masa si es necesario.

---

### Resultado esperado

Una **arquitectura clara y documentada** de integración con Strapi que establece cómo se gestionan usuarios, autenticación, roles y permisos mediante Strapi, cómo el backend propio consume y valida tokens JWT, cómo se aplican reglas de negocio adicionales, y cómo se mantiene sincronización entre ambos sistemas para garantizar seguridad y funcionalidad completa del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-140.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-140.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-140.png)
