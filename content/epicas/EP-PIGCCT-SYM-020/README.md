# Épica: Navegación y acceso al sistema

## Descripción general
Esta épica define la estructura de navegación y acceso al sistema PIGCCT, garantizando una experiencia de usuario coherente, segura y adaptada a los distintos roles. Incluye el menú principal, el dashboard inicial y el acceso a los módulos funcionales del sistema.

---

## Navegación principal

### Visualizar navegación principal  
[**HU-PIGCCT-SYM-169**](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-169/HU-PIGCCT-SYM-169.md)      
El sistema debe permitir a un usuario autenticado visualizar un menú principal persistente, para acceder rápidamente a las funcionalidades permitidas según el rol.  
El menú es visible en todo momento, se adapta según rol y permisos, y muestra únicamente opciones autorizadas.

### Navegación basada en roles  
[**HU-PIGCCT-SYM-170**](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-170/HU-PIGCCT-SYM-170.md)   
El sistema debe permitir mostrar u ocultar opciones del menú según el rol, garantizando control de acceso.

**Roles considerados:**
- Usuario registrador  
- Usuario validador entidad  
- Usuario validador CAR  
- Usuario administrador  
- Usuario consulta  

### Navegación contextual  
[**HU-PIGCCT-SYM-171**](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-171/HU-PIGCCT-SYM-171.md)   
El sistema debe permitir que el menú se adapte al contexto del módulo activo, reduciendo el ruido visual y mejorando la experiencia de usuario.

### Propuesta de mapa de navegación  
[**HU-PIGCCT-SYM-172**](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-172/HU-PIGCCT-SYM-172.md) 

**Modelo:** Sidebar híbrido + panel contextual  

**Componentes principales:**
1. Sidebar fijo (izquierdo)  
2. Panel contextual dinámico  
3. Breadcrumb inteligente  
4. Accesos rápidos por estado  

**Estructura del sidebar (nivel 1):**
- Sidebar siempre visible (íconos + texto)  
- Al contraerse: solo íconos con tooltips informativos  

---

## Inicio (Dashboard)

### Acceder al dashboard  
[**HU-PIGCCT-SYM-173**](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-173/HU-PIGCCT-SYM-173.md)   
El sistema debe permitir al usuario autenticado acceder a un panel de inicio para visualizar el estado general de las acciones y validaciones.

**Contenido mínimo:**
- Acciones en borrador  
- Acciones en validación  
- Acciones validadas  
- Alertas de seguimiento  

### Propósito del dashboard
Brindar una vista sintética y priorizada del estado del PIGCCT, adaptada al rol del usuario.

### Visualizar dashboard inicial  
[**HU-PIGCCT-SYM-174**](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-174/HU-PIGCCT-SYM-174.md)   
El sistema debe permitir visualizar un panel de inicio con indicadores clave del estado de las acciones e indicadores, orientando la gestión diaria del usuario.

### Contenido mínimo del dashboard  
[**HU-PIGCCT-SYM-175**](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-175/HU-PIGCCT-SYM-175.md) 
- Número de acciones:
  - En borrador  
  - En validación  
  - Validadas  
  - Rechazadas  
- Alertas por acciones pendientes  
- Indicadores con retraso  
- Últimas validaciones realizadas  

### Dashboard adaptado por rol  
[**HU-PIGCCT-SYM-176**](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-176/HU-PIGCCT-SYM-176.md)   
El sistema debe adaptar el contenido del dashboard según el rol del usuario.

**Ejemplos:**
- Registrador: acciones propias  
- Validador: acciones pendientes de validar  
- Administrador: vista consolidada  
- Consulta: solo información validada  

---

## Acciones

### Propósito
Gestionar el ciclo de vida completo de las acciones del PIGCCT.

- [**HU-PIGCCT-SYM-177** – Listar acciones.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-177/HU-PIGCCT-SYM-177.md)      
- [**HU-PIGCCT-SYM-178** – Crear acción.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-178/HU-PIGCCT-SYM-178.md)   
- [**HU-PIGCCT-SYM-179** – Editar acción.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-179/HU-PIGCCT-SYM-179.md)   
- [**HU-PIGCCT-SYM-180** – Enviar acción a validación.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-180/HU-PIGCCT-SYM-180.md)   
- [**HU-PIGCCT-SYM-181** – Visualizar acciones en el visor geográfico.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-181/HU-PIGCCT-SYM-181.md)   

---

## Validaciones

### Propósito
Soportar el flujo formal de revisión y aprobación institucional.

- [**HU-PIGCCT-SYM-182** – Listar acciones pendientes de validación.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-182/HU-PIGCCT-SYM-182.md)   
- [**HU-PIGCCT-SYM-183** – Validar acción.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-183/HU-PIGCCT-SYM-183.md)   
- [**HU-PIGCCT-SYM-184** – Rechazar acción con observaciones.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-184/HU-PIGCCT-SYM-184.md)   
- [**HU-PIGCCT-SYM-185** – Flujo de doble validación (Entidad → CAR).](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-185/HU-PIGCCT-SYM-185.md)   

---

## Reportes

### Propósito
Generar salidas analíticas y normativas para la toma de decisiones y rendición de cuentas.

- [**HU-PIGCCT-SYM-186** – Acceder al módulo de reportes.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-186/HU-PIGCCT-SYM-186.md)   
- [**HU-PIGCCT-SYM-187** – Reporte general del PIGCCT.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-187/HU-PIGCCT-SYM-187.md)   
- [**HU-PIGCCT-SYM-188** – Reportes territoriales.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-188/HU-PIGCCT-SYM-188.md)   
- [**HU-PIGCCT-SYM-189** – Reportes por componente.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-189/HU-PIGCCT-SYM-189.md)   
- [**HU-PIGCCT-SYM-190** – Exportar reportes (PDF / Excel).](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-190/HU-PIGCCT-SYM-190.md)   

---

## Administración

### Propósito
Configurar y gobernar el sistema.

- [**HU-PIGCCT-SYM-191** – Gestionar usuarios.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-191/HU-PIGCCT-SYM-191.md)   
- [**HU-PIGCCT-SYM-192** – Configurar flujos de validación.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-192/HU-PIGCCT-SYM-192.md)   
- [**HU-PIGCCT-SYM-193** – Parametrizar el sistema.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-193/HU-PIGCCT-SYM-193.md)   

---

## Catálogos

### Propósito
Mantener la consistencia semántica y estructural del PIGCCT.

- [**HU-PIGCCT-SYM-194** – Gestionar ejes estratégicos.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-194/HU-PIGCCT-SYM-194.md)   
- [**HU-PIGCCT-SYM-195** – Gestionar medidas.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-195/HU-PIGCCT-SYM-195.md)   
- [**HU-PIGCCT-SYM-196** – Gestionar indicadores.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-196/HU-PIGCCT-SYM-196.md)   
- [**HU-PIGCCT-SYM-197** – Catálogos territoriales.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-197/HU-PIGCCT-SYM-197.md)   

---

## Mi perfil

### Propósito
Permitir la autogestión del usuario.

- [**HU-PIGCCT-SYM-198** – Visualizar perfil.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-198/HU-PIGCCT-SYM-198.md)   
- [**HU-PIGCCT-SYM-199** – Actualizar información personal.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-199/HU-PIGCCT-SYM-199.md)   
- [**HU-PIGCCT-SYM-200** – Cambiar contraseña.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-200/HU-PIGCCT-SYM-200.md)   
- [**HU-PIGCCT-SYM-201** – Cerrar sesión de forma segura.](/content/epicas/EP-PIGCCT-SYM-020/historias_usuario/HU-PIGCCT-SYM-201/HU-PIGCCT-SYM-201.md)   

## Estado y seguimiento
- **Estado actual**: En definición .
- **Indicadores de seguimiento**:
  - Tiempo promedio de diligenciamiento de una acción.
  - Porcentaje de acciones completadas sin errores.
  - Número de correcciones requeridas antes del envío a validación.