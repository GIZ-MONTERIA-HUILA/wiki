# HU-PIGCCT-SYM-199  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Actualizar información personal

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** actualizar mi información personal no crítica en el sistema.  
> **Para:** mantener mis datos de contacto actualizados sin afectar la seguridad ni los permisos de acceso.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la actualización de información personal
1.1 El sistema debe permitir al usuario acceder a la opción **“Actualizar información personal”** desde el módulo **Mi perfil**.  
1.2 El acceso debe estar disponible únicamente para usuarios autenticados.

### 2. Datos personales actualizables
2.1 El sistema debe permitir modificar únicamente datos personales **no críticos**, tales como:
- Teléfono de contacto.
- Información adicional de perfil.
- Datos complementarios definidos por el sistema.

2.2 Los campos críticos no deben ser editables por el usuario, tales como:
- Correo electrónico.
- Rol.
- Estado de la cuenta.

### 3. Validaciones de la información
3.1 El sistema debe validar el formato de los datos ingresados.  
3.2 El sistema debe impedir el guardado de información incompleta o inválida.

### 4. Guardado de cambios
4.1 El sistema debe permitir guardar los cambios realizados en la información personal.  
4.2 Al guardar, el sistema debe mostrar un mensaje de confirmación exitoso.

### 5. Persistencia de la información
5.1 Los cambios deben almacenarse inmediatamente en el sistema.  
5.2 La información actualizada debe reflejarse automáticamente en el perfil del usuario.

### 6. Seguridad y control
6.1 El usuario solo debe poder actualizar su propia información personal.  
6.2 No debe ser posible modificar información de otros usuarios por navegación directa.

### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar:
- Usuario que realizó la actualización.
- Fecha y hora del cambio.
- Campos modificados.

7.2 Esta información debe estar disponible para fines de auditoría.

### 8. Usabilidad y experiencia de usuario
8.1 El proceso de actualización debe ser claro y sencillo.  
8.2 El sistema debe mostrar mensajes claros ante errores de validación.  
8.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario puede **actualizar correctamente su información personal no crítica**, manteniendo sus datos de contacto vigentes, sin afectar la seguridad, el rol ni el control de acceso dentro del sistema PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-199.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-199.png)


