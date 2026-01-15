# HU-PIGCCT-SYM-141  
## Épica: Estructura y navegación del formulario de acciones  
### Visualizar formulario guiado por pestañas

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** visualizar el formulario de acciones organizado por pestañas.  
> **Para:** diligenciar la información de manera clara y ordenada, donde solo se muestran las pestañas permitidas según el estado de la acción.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al formulario de acciones
1.1 El sistema debe permitir el acceso al formulario de acciones a usuarios con rol de **registrador**.  
1.2 El formulario debe estar disponible desde el módulo de **Registro de acciones** o **Gestión de acciones del PIGCCT**.  
1.3 Al acceder, el sistema debe mostrar un formulario estructurado por pestañas.

### 2. Organización por pestañas
2.1 El formulario de acciones debe estar organizado en pestañas temáticas que agrupan información relacionada.  
2.2 Las pestañas disponibles en el formulario completo son:
- **Información general**: Datos básicos de la acción (nombre, descripción, responsables)
- **Territorio**: Información geográfica y de cobertura territorial
- **Articulación con el plan**: Relación con ejes, medidas y objetivos del PIGCCT
- **Programación y seguimiento**: Cronograma, presupuesto y avances
- **Indicadores asociados**: Indicadores de monitoreo de la acción
- **Adjuntos**: Documentos soporte y evidencias
- **Estado y validación**: Información del flujo de validación

### 3. Navegación entre pestañas
3.1 El sistema debe permitir navegar libremente entre las pestañas habilitadas mediante clics en el encabezado de cada pestaña.  
3.2 El sistema debe indicar visualmente cuál es la pestaña actualmente activa.  
3.3 El sistema debe mantener la información ingresada en cada pestaña al cambiar de una a otra sin necesidad de guardar.

### 4. Indicadores visuales de estado
4.1 El sistema debe mostrar indicadores visuales en cada pestaña que informen:
- Si la pestaña está habilitada o deshabilitada
- Si la información de la pestaña está completa o pendiente
- Si existen errores de validación en la pestaña

4.2 Las pestañas deshabilitadas deben tener una apariencia visual distinta (atenuada o con indicador de bloqueo).

### 5. Visibilidad condicional de pestañas
5.1 El sistema debe mostrar u ocultar pestañas según el estado de la acción:
- **Acción nueva (sin guardar)**: Solo se muestran pestañas de información básica
- **Acción guardada**: Se habilitan todas las pestañas de relaciones y adjuntos

5.2 Las pestañas no disponibles no deben ser accesibles mediante ningún medio (clic, teclado, etc.).

### 6. Mensajes informativos
6.1 Al intentar acceder a una pestaña deshabilitada, el sistema debe mostrar un mensaje informativo explicando:
- Por qué la pestaña no está disponible
- Qué acción debe realizar el usuario para habilitarla (ej: "Guarda la acción primero para acceder a esta sección")

### 7. Validación por pestaña
7.1 El sistema debe validar los campos obligatorios de cada pestaña antes de permitir guardar la acción.  
7.2 Si existen errores en alguna pestaña, el sistema debe:
- Indicar visualmente cuál pestaña tiene errores
- Mostrar un resumen de errores
- Permitir navegar directamente a la pestaña con errores

### 8. Guardado de información
8.1 El sistema debe permitir guardar la información en cualquier momento desde cualquier pestaña activa.  
8.2 Al guardar, el sistema debe validar todos los campos obligatorios de todas las pestañas habilitadas.  
8.3 El botón de guardar debe estar visible y accesible desde todas las pestañas.

### 9. Consistencia de diseño
9.1 El diseño de las pestañas debe ser consistente con el resto del sistema.  
9.2 Los encabezados de las pestañas deben ser descriptivos y claros.  
9.3 El contenido de cada pestaña debe estar organizado de forma lógica con secciones y campos agrupados.

### 10. Comportamiento responsivo
10.1 En dispositivos con pantallas pequeñas, el sistema debe adaptar la visualización de las pestañas.  
10.2 Puede usar menú desplegable o lista vertical si es necesario para mejorar la usabilidad en dispositivos móviles.

### 11. Accesibilidad
11.1 El sistema debe permitir navegación por teclado entre pestañas (ej: Tab, flechas).  
11.2 Las pestañas deben tener atributos ARIA apropiados para lectores de pantalla.  
11.3 Los indicadores visuales no deben depender únicamente del color.

### 12. Auditoría de navegación
12.1 El sistema puede registrar en logs la navegación del usuario entre pestañas para análisis de usabilidad.  
12.2 Esta información puede ayudar a identificar secciones problemáticas del formulario.

---

### Resultado esperado

Un **formulario de acciones organizado por pestañas** que permite al usuario registrador visualizar y navegar de manera clara entre las diferentes secciones de información, con indicadores visuales apropiados, validación por pestaña, y visibilidad condicional según el estado de la acción.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-141.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-141.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-141.png)
