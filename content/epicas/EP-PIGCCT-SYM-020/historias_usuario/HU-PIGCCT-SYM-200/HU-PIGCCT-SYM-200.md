# HU-PIGCCT-SYM-200  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Cambiar contraseña

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** cambiar mi contraseña de acceso al sistema.  
> **Para:** mantener la seguridad de mi cuenta cumpliendo las políticas establecidas por el sistema PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al cambio de contraseña
1.1 El sistema debe permitir al usuario acceder a la opción **“Cambiar contraseña”** desde el módulo **Mi perfil**.  
1.2 El acceso debe estar disponible únicamente para usuarios autenticados.

### 2. Ingreso de credenciales
2.1 El sistema debe solicitar obligatoriamente:
- Contraseña actual.
- Nueva contraseña.
- Confirmación de la nueva contraseña.

2.2 El sistema debe validar que la contraseña actual sea correcta antes de permitir el cambio.

### 3. Políticas de seguridad
3.1 La nueva contraseña debe cumplir con las **políticas de seguridad**, tales como:
- Longitud mínima definida.
- Combinación de letras mayúsculas y minúsculas.
- Inclusión de números y/o caracteres especiales.
- No reutilización de contraseñas anteriores, si aplica.

3.2 El sistema debe mostrar mensajes claros cuando la contraseña no cumpla las políticas.

### 4. Confirmación del cambio
4.1 El sistema debe validar que la nueva contraseña y su confirmación coincidan.  
4.2 El sistema no debe permitir guardar si existe inconsistencia.

### 5. Actualización de la contraseña
5.1 Al confirmar el cambio, el sistema debe actualizar la contraseña de forma segura.  
5.2 El sistema debe cifrar la contraseña según los estándares de seguridad definidos.

### 6. Notificación del cambio
6.1 El sistema debe mostrar un mensaje de confirmación exitoso tras el cambio.  
6.2 Opcionalmente, el sistema puede notificar al usuario por correo electrónico.

### 7. Seguridad y control
7.1 El usuario solo debe poder cambiar su propia contraseña.  
7.2 El sistema debe bloquear intentos repetidos fallidos según las políticas de seguridad.

### 8. Auditoría y trazabilidad
8.1 El sistema debe registrar:
- Usuario que realizó el cambio.
- Fecha y hora del evento.

8.2 No debe almacenarse la contraseña en texto plano.

### 9. Usabilidad y experiencia de usuario
9.1 El proceso de cambio de contraseña debe ser claro y guiado.  
9.2 El sistema debe mostrar mensajes claros de error o éxito.  
9.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario puede **cambiar su contraseña de forma segura**, cumpliendo las políticas definidas por el sistema, fortaleciendo la protección de su cuenta y garantizando la confidencialidad del acceso al PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-200.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-200.png)


