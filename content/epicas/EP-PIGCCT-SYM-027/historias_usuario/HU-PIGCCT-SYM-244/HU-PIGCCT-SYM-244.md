# HU-PIGCCT-SYM-244
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Popup informativo

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                     
> **Quiero:** que al seleccionar un elemento del mapa se muestre un popup informativo con datos resumidos.                        
> **Para:** acceder de forma rápida y contextual a la información clave de municipios o acciones del PIGCCT, sin salir del visor geográfico.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Activación del popup informativo

1.1 El sistema debe mostrar automáticamente un popup informativo al seleccionar un elemento del mapa.                       
1.2 El popup debe activarse únicamente cuando se seleccione una entidad válida y visible.              
1.3 La funcionalidad debe estar disponible para todos los usuarios con permisos de acceso al visor geográfico.

### 2. Elementos soportados

2.1 El popup debe mostrarse al seleccionar como mínimo los siguientes elementos:

- Municipios.
- Acciones del PIGCCT.

2.2 El sistema debe identificar el tipo de elemento seleccionado para mostrar la información correspondiente.

### 3. Contenido del popup

3.1 Para municipios, el popup debe mostrar información resumida como:

- Nombre del municipio.
- Código DANE (si aplica).
- Indicadores básicos asociados al PIGCCT.

3.2 Para acciones, el popup debe mostrar como mínimo:

- Nombre de la acción.
- Eje estratégico y medida asociada.
- Estado de validación.
- Cobertura territorial (municipal o departamental).

3.3 El contenido debe ser claro, conciso y relevante para el análisis rápido.

### 4. Comportamiento del popup

4.1 El popup debe ubicarse de forma automática cerca del elemento seleccionado, sin ocultar información crítica del mapa.               
4.2 El sistema debe permitir:

- Cerrar el popup manualmente.
- Cambiar de selección, actualizando el contenido del popup.

4.3 Solo debe existir un popup activo a la vez.

### 5. Integración con otras funcionalidades

5.1 El popup no debe interferir con:

- El control de capas.
- La selección del PIGCCT activo.
- La navegación del visor.

5.2 El popup puede incluir accesos rápidos a información detallada o vistas ampliadas, si aplica.

### 6. Manejo de errores y validaciones

6.1 Si no es posible cargar la información del elemento seleccionado, el sistema debe:

- Mostrar un mensaje informativo en el popup.
- Mantener operativa la interfaz del visor.

6.2 El sistema debe prevenir la visualización de información inconsistente o incompleta.

### 7. Usabilidad y experiencia de usuario

7.1 El popup debe ser visualmente claro y legible.              
7.2 La información debe adaptarse a diferentes tamaños de pantalla.                 
7.3 El usuario debe poder interactuar con el mapa sin que el popup afecte negativamente la experiencia.

---

### Resultado esperado

Un visor geográfico que muestre popups informativos claros y concisos al seleccionar municipios o acciones, permitiendo al usuario acceder rápidamente a la información clave del PIGCCT sin abandonar el contexto espacial del mapa.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-244.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-244.png)