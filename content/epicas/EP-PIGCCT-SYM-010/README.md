# Épica: Autenticación, gestión de usuarios y control de acceso del sistema PIGCCT

## 1. Descripción general
Esta épica aborda la **autenticación de usuarios, la gestión de cuentas y el control de acceso al sistema PIGCCT**, garantizando que solo usuarios autorizados puedan acceder a la información y funcionalidades, de acuerdo con su rol y entidad. Se apoya en los mecanismos de autenticación, roles y permisos de **Strapi**, complementados con reglas de negocio propias del sistema.

La épica establece las bases de seguridad, segregación de funciones, trazabilidad de accesos y control institucional de la información.

## 2. Objetivo
Permitir al sistema autenticar usuarios de forma segura, administrar usuarios y roles, controlar el acceso a funcionalidades e información según perfiles definidos, y registrar auditoría de accesos, garantizando seguridad, integridad y uso adecuado de los datos del PIGCCT.

## 3. Justificación / Valor de negocio
La gestión de usuarios y accesos:
- Garantiza la seguridad del sistema y de la información sensible.
- Asegura la segregación de funciones entre registro, validación y consulta.
- Permite control institucional y trazabilidad de responsabilidades.
- Reduce riesgos de accesos no autorizados o modificaciones indebidas.
- Cumple buenas prácticas de gobierno de datos y seguridad de la información.

## 4. Alcance
Incluye:
- Autenticación de usuarios mediante usuario y contraseña.
- Validación segura de credenciales usando mecanismos propios de Strapi.
- Bloqueo de usuarios por múltiples intentos fallidos.
- Recuperación y restablecimiento de contraseña mediante enlaces seguros.
- Creación y administración de usuarios del sistema.
- Asignación obligatoria de entidad a cada usuario.
- Asignación y gestión de roles y permisos.
- Definición de roles por entidad y roles transversales.
- Restricción de acceso a funcionalidades según rol.
- Control de visibilidad de la información según rol y estado de validación.
- Registro de auditoría de accesos y eventos de autenticación.
- Integración técnica con Strapi mediante JWT.

No incluye:
- Autenticación federada externa (SSO, LDAP, etc.).
- Gestión avanzada de identidades fuera de Strapi.
- Políticas de seguridad de infraestructura.

## 5. Actores / Roles
- **Usuario del sistema**: Accede al sistema según su rol asignado.
- **Usuario registrador**: Crea y actualiza información.
- **Usuario validador de entidad**: Valida información de su entidad.
- **Usuario validador CAR**: Realiza validación regional.
- **Administrador del sistema**: Administra usuarios, roles, catálogos y parámetros.
- **Usuario consulta**: Accede solo a información validada.
- **Sistema (Strapi + backend)**: Autentica, controla accesos y aplica reglas de negocio.

## 6. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-129**: Validar credenciales de acceso.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-129/HU-PIGCCT-SYM-129.md)   
- [**HU-PIGCCT-SYM-130**: Bloquear usuario por intentos fallidos.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-130/HU-PIGCCT-SYM-130.md)     
- [**HU-PIGCCT-SYM-131**: Recuperar contraseña.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-131/HU-PIGCCT-SYM-131.md)     
- [**HU-PIGCCT-SYM-132**: Restablecer contraseña.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-132/HU-PIGCCT-SYM-132.md)     
- [**HU-PIGCCT-SYM-133**: Crear usuario del sistema.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-133/HU-PIGCCT-SYM-133.md)     
- [**HU-PIGCCT-SYM-134**: Asignar entidad al usuario.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-134/HU-PIGCCT-SYM-134.md)     
- [**HU-PIGCCT-SYM-135**: Asignar roles al usuario.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-135/HU-PIGCCT-SYM-135.md)     
- [**HU-PIGCCT-SYM-136**: Definir roles del sistema.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-136/HU-PIGCCT-SYM-136.md)       
- [**HU-PIGCCT-SYM-137**: Restringir acceso por rol.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-137/HU-PIGCCT-SYM-137.md)       
- [**HU-PIGCCT-SYM-138**: Controlar visibilidad de información.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-138/HU-PIGCCT-SYM-138.md)       
- [**HU-PIGCCT-SYM-139**: Registrar auditoría de acceso.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-139/HU-PIGCCT-SYM-139.md)       
- [**HU-PIGCCT-SYM-140**: Consideraciones técnicas de Strapi.](/content/epicas/EP-PIGCCT-SYM-010/historias_usuario/HU-PIGCCT-SYM-140/HU-PIGCCT-SYM-140.md)     

## 7. Criterios de éxito
- Los usuarios solo acceden a funcionalidades permitidas por su rol.
- Las credenciales se gestionan de forma segura sin exposición de contraseñas.
- Los usuarios quedan bloqueados tras superar el número de intentos fallidos.
- La recuperación de contraseña se realiza mediante enlaces seguros y temporales.
- Toda acción de autenticación queda registrada para auditoría.
- La información visible corresponde al rol y estado de validación del usuario.

## 8. Dependencias y supuestos
**Dependencias**
- Configuración correcta de Strapi (roles, permisos, autenticación).
- Definición institucional de entidades y roles.
- Integración correcta entre Strapi y el backend propio.

**Supuestos**
- Los usuarios utilizan credenciales personales e intransferibles.
- Los administradores gestionan adecuadamente usuarios y roles.
- El token JWT es confiable para validar sesiones y contexto de usuario.

## 9. Riesgos
- Configuración incorrecta de roles que exponga funcionalidades sensibles.
- Mala gestión de usuarios inactivos o bloqueados.
- Uso compartido de credenciales por parte de usuarios.
- Dependencia excesiva de la configuración de Strapi sin controles adicionales.
- Falta de monitoreo de eventos de auditoría.

## 10. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de usuarios activos por rol y entidad.
  - Cantidad de intentos fallidos y usuarios bloqueados.
  - Eventos de autenticación registrados.
  - Porcentaje de usuarios con roles correctamente asignados.
