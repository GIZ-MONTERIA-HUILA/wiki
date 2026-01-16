# HU-PIGCCT-SYM-169  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Visualizar navegación principal

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** visualizar un menú principal persistente dentro del sistema.  
> **Para:** acceder de forma rápida y clara a las funcionalidades disponibles según mi rol y permisos.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al menú principal
1.1 El sistema debe mostrar el **menú principal** a todo usuario que se encuentre **autenticado**.  
1.2 El menú debe estar disponible desde cualquier módulo o vista del sistema.  
1.3 El sistema no debe mostrar el menú a usuarios no autenticados.


### 2. Persistencia del menú
2.1 El menú principal debe ser **visible en todo momento** durante la navegación por el sistema.  
2.2 El menú no debe ocultarse al cambiar entre módulos, vistas o funcionalidades.  
2.3 La navegación entre opciones del menú no debe provocar la pérdida de información no guardada sin previa advertencia.


### 3. Adaptación por rol y permisos
3.1 El sistema debe adaptar automáticamente las opciones del menú según:
- El **rol del usuario**.
- Los **permisos** asociados a dicho rol.

3.2 El menú debe mostrar **únicamente las opciones autorizadas** para el usuario autenticado.  
3.3 Las opciones no permitidas:
- No deben ser visibles.
- No deben ser accesibles por navegación directa mediante URL.


### 4. Estructura y presentación
4.1 El menú debe presentar una estructura clara y jerárquica que facilite la identificación de los módulos principales del sistema.  
4.2 Cada opción del menú debe contar con:
- Etiqueta textual.
- Ícono representativo (si aplica).
- Indicador visual de opción activa.

4.3 En caso de menú contraído:
- El sistema debe mostrar únicamente íconos.
- Debe desplegar **tooltips informativos** al pasar el cursor sobre cada opción.


### 5. Comportamiento dinámico
5.1 El sistema debe actualizar el contenido del menú dinámicamente cuando:
- Cambie el rol del usuario.
- Se modifiquen los permisos asociados al usuario.

5.2 Los cambios deben reflejarse sin requerir cierre de sesión, cuando aplique.


### 6. Seguridad y control de acceso
6.1 El menú debe actuar como una **primera capa de control de acceso**, ocultando opciones no autorizadas.  
6.2 El sistema debe implementar validaciones adicionales en la capa de backend para impedir el acceso a funcionalidades no permitidas, aun cuando se intente acceder por rutas directas.


### 7. Usabilidad y experiencia de usuario
7.1 El menú debe ser:
- Claro.
- Consistente.
- Fácil de usar.

7.2 El usuario debe poder identificar rápidamente:
- Las funcionalidades disponibles.
- Su ubicación actual dentro del sistema.

7.3 El diseño del menú debe ser coherente con el estilo visual general del sistema PIGCCT.

---

### Resultado esperado

El usuario autenticado puede **visualizar y utilizar un menú principal persistente**, adaptado a su rol y permisos, que muestra únicamente las opciones autorizadas, facilitando una navegación segura, clara y eficiente por las funcionalidades del sistema PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-169.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-169.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-169.png)
