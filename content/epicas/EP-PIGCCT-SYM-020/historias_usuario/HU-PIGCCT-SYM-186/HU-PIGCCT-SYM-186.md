# HU-PIGCCT-SYM-186  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Acceder al módulo de reportes

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** acceder al módulo de reportes del sistema.  
> **Para:** seleccionar y consultar los tipos de reportes disponibles según mi rol, apoyando la toma de decisiones y la rendición de cuentas del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al módulo de reportes
1.1 El sistema debe permitir el acceso al **módulo de reportes** únicamente a usuarios autenticados.  
1.2 El acceso debe estar disponible desde el menú principal, según el rol y permisos del usuario.  
1.3 El sistema no debe permitir el acceso a usuarios no autorizados.

### 2. Visualización de tipos de reporte
2.1 Al ingresar al módulo, el sistema debe mostrar los **tipos de reportes disponibles** para el usuario.  
2.2 La disponibilidad de reportes debe depender del:
- Rol del usuario.
- Permisos asignados.

2.3 El sistema no debe mostrar reportes que el usuario no esté autorizado a consultar.

### 3. Clasificación de reportes
3.1 El sistema debe organizar los reportes por categorías, tales como:
- Reportes generales.
- Reportes territoriales.
- Reportes por componente.

3.2 La clasificación debe facilitar la identificación del tipo de reporte requerido.

### 4. Control de acceso por rol
4.1 El sistema debe aplicar reglas de acceso específicas para cada rol.  
4.2 Los usuarios solo deben poder visualizar y generar los reportes permitidos según su perfil.

### 5. Navegación dentro del módulo
5.1 El usuario debe poder navegar entre los diferentes tipos de reportes de forma clara y ordenada.  
5.2 El sistema debe permitir regresar al dashboard o a otros módulos sin pérdida de información.

### 6. Seguridad y confidencialidad
6.1 El sistema debe garantizar que la información presentada en los reportes respete las políticas de acceso y confidencialidad.  
6.2 El acceso a reportes por navegación directa sin permisos debe estar bloqueado.

### 7. Usabilidad y experiencia de usuario
7.1 El módulo de reportes debe ser claro, intuitivo y fácil de usar.  
7.2 El sistema debe orientar al usuario en la selección del tipo de reporte.  
7.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario puede **acceder al módulo de reportes del PIGCCT**, visualizar los tipos de reportes disponibles según su rol y permisos, y navegar de forma segura y ordenada para apoyar la toma de decisiones y los procesos de rendición de cuentas.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-186.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-186.png)


