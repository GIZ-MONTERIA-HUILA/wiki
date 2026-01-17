# HU-PIGCCT-SYM-201  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Cerrar sesión

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** cerrar mi sesión en el sistema de forma segura.  
> **Para:** proteger mi información y evitar accesos no autorizados cuando finalizo el uso del sistema PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la opción de cierre de sesión
1.1 El sistema debe permitir al usuario acceder a la opción **“Cerrar sesión”** desde el menú principal o el área de perfil.  
1.2 La opción debe estar visible únicamente cuando el usuario tenga una sesión activa.

### 2. Proceso de cierre de sesión
2.1 Al seleccionar **“Cerrar sesión”**, el sistema debe finalizar correctamente la sesión activa del usuario.  
2.2 El sistema debe invalidar el token o credenciales de sesión.

### 3. Confirmación del cierre
3.1 El sistema debe solicitar confirmación antes de cerrar la sesión, si así se define en la experiencia de usuario.  
3.2 El usuario debe poder cancelar la acción antes de finalizar la sesión.

### 4. Redirección posterior
4.1 Una vez cerrada la sesión, el sistema debe redirigir al usuario a la pantalla de inicio de sesión.  
4.2 El sistema no debe permitir el acceso a vistas internas mediante el botón “atrás” del navegador.

### 5. Seguridad de la sesión
5.1 El sistema debe garantizar que, tras el cierre de sesión:
- No sea posible acceder a información protegida.
- Se limpien los datos temporales de sesión.

5.2 El sistema debe prevenir el uso indebido de sesiones caducadas.

### 6. Manejo de sesiones activas
6.1 El sistema debe manejar correctamente sesiones concurrentes, si están permitidas.  
6.2 El cierre de sesión debe afectar únicamente la sesión activa.

### 7. Usabilidad y experiencia de usuario
7.1 El proceso de cierre de sesión debe ser rápido y sencillo.  
7.2 El sistema debe mostrar un mensaje confirmando el cierre exitoso.  
7.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario puede **cerrar su sesión de forma segura**, garantizando la finalización correcta del acceso al sistema, la protección de su información y la prevención de accesos no autorizados al PIGCCT.


---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-201.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-201.png)


