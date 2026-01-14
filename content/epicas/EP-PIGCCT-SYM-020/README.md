# Épica: Navegación y acceso al sistema

## Descripción general
Esta épica define la estructura de navegación y acceso al sistema PIGCCT, garantizando una experiencia de usuario coherente, segura y adaptada a los distintos roles. Incluye el menú principal, el dashboard inicial y el acceso a los módulos funcionales del sistema.

---

## Navegación principal

### Visualizar navegación principal  
**HU-PIGCCT-SYM-169**  
El sistema debe permitir a un usuario autenticado visualizar un menú principal persistente, para acceder rápidamente a las funcionalidades permitidas según el rol.  
El menú es visible en todo momento, se adapta según rol y permisos, y muestra únicamente opciones autorizadas.

### Navegación basada en roles  
**HU-PIGCCT-SYM-170**  
El sistema debe permitir mostrar u ocultar opciones del menú según el rol, garantizando control de acceso.

**Roles considerados:**
- Usuario registrador  
- Usuario validador entidad  
- Usuario validador CAR  
- Usuario administrador  
- Usuario consulta  

### Navegación contextual  
**HU-PIGCCT-SYM-171**  
El sistema debe permitir que el menú se adapte al contexto del módulo activo, reduciendo el ruido visual y mejorando la experiencia de usuario.

### Propuesta de mapa de navegación  
**HU-PIGCCT-SYM-172**

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
**HU-PIGCCT-SYM-173**  
El sistema debe permitir al usuario autenticado acceder a un panel de inicio para visualizar el estado general de las acciones y validaciones.

**Contenido mínimo:**
- Acciones en borrador  
- Acciones en validación  
- Acciones validadas  
- Alertas de seguimiento  

### Propósito del dashboard
Brindar una vista sintética y priorizada del estado del PIGCCT, adaptada al rol del usuario.

### Visualizar dashboard inicial  
**HU-PIGCCT-SYM-174**  
El sistema debe permitir visualizar un panel de inicio con indicadores clave del estado de las acciones e indicadores, orientando la gestión diaria del usuario.

### Contenido mínimo del dashboard  
**HU-PIGCCT-SYM-175**
- Número de acciones:
  - En borrador  
  - En validación  
  - Validadas  
  - Rechazadas  
- Alertas por acciones pendientes  
- Indicadores con retraso  
- Últimas validaciones realizadas  

### Dashboard adaptado por rol  
**HU-PIGCCT-SYM-176**  
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

- **HU-PIGCCT-SYM-177** – Listar acciones  
- **HU-PIGCCT-SYM-178** – Crear acción  
- **HU-PIGCCT-SYM-179** – Editar acción  
- **HU-PIGCCT-SYM-180** – Enviar acción a validación  
- **HU-PIGCCT-SYM-181** – Visualizar acciones en el visor geográfico  

---

## Validaciones

### Propósito
Soportar el flujo formal de revisión y aprobación institucional.

- **HU-PIGCCT-SYM-182** – Listar acciones pendientes de validación  
- **HU-PIGCCT-SYM-183** – Validar acción  
- **HU-PIGCCT-SYM-184** – Rechazar acción con observaciones  
- **HU-PIGCCT-SYM-185** – Flujo de doble validación (Entidad → CAR)  

---

## Reportes

### Propósito
Generar salidas analíticas y normativas para la toma de decisiones y rendición de cuentas.

- **HU-PIGCCT-SYM-186** – Acceder al módulo de reportes  
- **HU-PIGCCT-SYM-187** – Reporte general del PIGCCT  
- **HU-PIGCCT-SYM-188** – Reportes territoriales  
- **HU-PIGCCT-SYM-189** – Reportes por componente  
- **HU-PIGCCT-SYM-190** – Exportar reportes (PDF / Excel)  

---

## Administración

### Propósito
Configurar y gobernar el sistema.

- **HU-PIGCCT-SYM-191** – Gestionar usuarios  
- **HU-PIGCCT-SYM-192** – Configurar flujos de validación  
- **HU-PIGCCT-SYM-193** – Parametrizar el sistema  

---

## Catálogos

### Propósito
Mantener la consistencia semántica y estructural del PIGCCT.

- **HU-PIGCCT-SYM-194** – Gestionar ejes estratégicos  
- **HU-PIGCCT-SYM-195** – Gestionar medidas  
- **HU-PIGCCT-SYM-196** – Gestionar indicadores  
- **HU-PIGCCT-SYM-197** – Catálogos territoriales  

---

## Mi perfil

### Propósito
Permitir la autogestión del usuario.

- **HU-PIGCCT-SYM-198** – Visualizar perfil  
- **HU-PIGCCT-SYM-199** – Actualizar información personal  
- **HU-PIGCCT-SYM-200** – Cambiar contraseña  
- **HU-PIGCCT-SYM-201** – Cerrar sesión de forma segura  

## Estado y seguimiento
- **Estado actual**: En definición .
- **Indicadores de seguimiento**:
  - Tiempo promedio de diligenciamiento de una acción.
  - Porcentaje de acciones completadas sin errores.
  - Número de correcciones requeridas antes del envío a validación.