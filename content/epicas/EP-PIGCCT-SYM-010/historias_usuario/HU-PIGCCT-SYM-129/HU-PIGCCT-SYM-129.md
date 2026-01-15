# HU-PIGCCT-SYM-129  
## Épica: Autenticación, gestión de usuarios, y control de acceso del sistema PIGCCT  
### Validar credenciales de acceso

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de autenticación.  
> **Quiero:** validar que el usuario y contraseña sean correctos.  
> **Para:** garantizar acceso seguro al sistema PIGCCT y proteger la información institucional.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Validación de credenciales
1.1 El sistema debe validar las credenciales (usuario y contraseña) contra la base de datos de **Strapi**.  
1.2 La validación debe ejecutarse cada vez que un usuario intenta iniciar sesión.  
1.3 El sistema **nunca debe almacenar ni transmitir la contraseña en texto plano**.

### 2. Uso de mecanismo de hash
2.1 El sistema debe utilizar el mecanismo de **hash y validación propio de Strapi** para verificar contraseñas.  
2.2 Las contraseñas deben estar almacenadas en la base de datos con un hash seguro (bcrypt o similar).  
2.3 La comparación de contraseñas debe realizarse mediante la función de verificación de hash de Strapi.

### 3. Respuesta en caso de credenciales válidas
3.1 Si las credenciales son correctas, el sistema debe:
- Generar un **token JWT** válido
- Retornar el token al cliente
- Incluir información básica del usuario (ID, nombre, correo, rol, entidad)
- Registrar el evento de inicio de sesión exitoso en logs de auditoría

3.2 El token JWT debe tener un tiempo de expiración configurable (recomendado: 8-24 horas).

### 4. Respuesta en caso de credenciales inválidas
4.1 Si las credenciales son incorrectas, el sistema debe:
- **No revelar** si el usuario existe o si la contraseña es incorrecta
- Retornar un mensaje genérico como: "Usuario o contraseña incorrectos"
- **No proporcionar información** que ayude a identificar usuarios válidos

4.2 El sistema debe responder en un tiempo similar tanto para credenciales válidas como inválidas (prevenir timing attacks).

### 5. Transmisión segura
5.1 Todas las credenciales deben transmitirse únicamente a través de **HTTPS**.  
5.2 El sistema debe rechazar intentos de autenticación a través de conexiones no cifradas (HTTP).  
5.3 El token JWT retornado debe transmitirse de forma segura.

### 6. Validación de formato
6.1 Antes de enviar las credenciales a Strapi, el sistema debe validar:
- El campo usuario/correo no esté vacío
- El campo contraseña no esté vacío
- El formato de correo electrónico sea válido (si se usa correo como usuario)
- Los campos no contengan caracteres peligrosos (prevenir inyección)

### 7. Integración con Strapi
7.1 El sistema debe utilizar el endpoint de autenticación de Strapi:
```
POST /api/auth/local
Body: { "identifier": "usuario", "password": "contraseña" }
```

7.2 El sistema debe manejar correctamente las respuestas de Strapi:
- 200: Autenticación exitosa → procesar token
- 400: Credenciales inválidas → mostrar mensaje genérico
- 429: Demasiados intentos → bloquear temporalmente
- 500: Error del servidor → mensaje de error técnico

### 8. Validación de usuario confirmado
8.1 Si Strapi requiere confirmación de correo (campo `confirmed: false`), el sistema debe:
- Rechazar el inicio de sesión
- Mostrar mensaje: "Debes confirmar tu cuenta. Revisa tu correo electrónico"
- Ofrecer opción para reenviar correo de confirmación

### 9. Tiempo de respuesta
9.1 La validación de credenciales debe completarse en un tiempo razonable (< 2 segundos en condiciones normales).  
9.2 Si la validación tarda más del tiempo esperado, el sistema debe:
- Mostrar indicador de carga al usuario
- Implementar timeout para evitar bloqueos indefinidos

### 10. Mensajes de error genéricos
10.1 Los mensajes de error **nunca deben revelar**:
- Si el usuario existe
- Si la contraseña es incorrecta
- Detalles técnicos del sistema

10.2 Usar siempre mensajes genéricos de seguridad.

### 11. Auditoría de seguridad
11.1 Todos los intentos de autenticación deben registrarse en logs de seguridad con nivel de detalle apropiado.  
11.2 Los logs deben incluir información para investigaciones de seguridad sin exponer contraseñas.

### 12. Compatibilidad con autenticación de dos factores (2FA)
12.1 El sistema debe estar preparado para integración futura con autenticación de dos factores.  
12.2 La arquitectura debe permitir agregar pasos adicionales de validación después de verificar usuario/contraseña.

---

### Resultado esperado

Un **proceso de validación de credenciales seguro** que utiliza el mecanismo de hash de Strapi, nunca expone contraseñas en texto plano, responde con mensajes genéricos apropiados, registra intentos para auditoría, y genera tokens JWT válidos para usuarios autenticados correctamente.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-129.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-129.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-129.png)
