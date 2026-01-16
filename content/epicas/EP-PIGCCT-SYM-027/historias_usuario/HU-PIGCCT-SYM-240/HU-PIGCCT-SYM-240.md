# HU-PIGCCT-SYM-240
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Simbología por estado de validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                          
> **Quiero:** que las acciones del PIGCCT se representen en el visor geográfico con una simbología diferenciada según su estado de validación.                       
> **Para:** identificar visualmente el nivel de avance y validación de las acciones, facilitando el análisis, seguimiento y control territorial del Plan Integral de Gestión del Cambio Climático Territorial.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la simbología por estado

1.1 El sistema debe aplicar la simbología por estado de validación a las acciones visibles en el visor geográfico.                  
1.2 Esta simbología debe activarse automáticamente al visualizar la capa de acciones del PIGCCT.                         
1.3 La funcionalidad debe estar disponible únicamente cuando exista un PIGCCT activo.

## 2. Estados de validación soportados

2.1 El sistema debe soportar como mínimo los siguientes estados de validación de las acciones:

- Borrador.
- En validación.
- Validada.
- Rechazada (si aplica).

2.2 Los estados deben corresponder a los definidos en los catálogos oficiales del sistema.

### 3. Definición de la simbología

3.1 Cada estado de validación debe representarse mediante una simbología visual diferenciada, que puede incluir:

- Color.
- Forma.
- Patrón o estilo.

3.2 La simbología debe ser consistente en todo el sistema y cumplir con los lineamientos gráficos institucionales.                          
3.3 El sistema debe garantizar la accesibilidad visual (contraste y legibilidad).

### 4. Visualización en el visor geográfico

4.1 Las acciones deben visualizarse en el mapa utilizando la simbología correspondiente a su estado actual de validación.                        
4.2 La simbología debe actualizarse automáticamente cuando cambie el estado de validación de una acción.                      
4.3 La actualización debe realizarse sin recargar completamente el visor geográfico.

### 5. Leyenda y referencia visual

5.1 El visor debe mostrar una leyenda dinámica que explique claramente la simbología utilizada para cada estado de validación.                   
5.2 La leyenda debe actualizarse automáticamente según las capas activas y la simbología aplicada.                        
5.3 El usuario debe poder consultar la leyenda en cualquier momento durante la navegación del visor.

### 6. Interacción con las acciones

6.1 Al seleccionar una acción en el mapa, el sistema debe mostrar información detallada, incluyendo:

- Nombre de la acción.
- Estado de validación actual.
- Municipio(s) o cobertura territorial.

6.2 La simbología no debe interferir con la interacción o selección de las acciones.

### 7. Manejo de errores y validaciones

7.1 Si una acción no tiene estado de validación definido, el sistema debe:

- Aplicar una simbología por defecto.
- Informar la situación mediante un mensaje o indicador visual.

7.2 El sistema debe prevenir inconsistencias entre el estado registrado y la simbología mostrada.

### 8. Usabilidad y experiencia de usuario

8.1 La simbología debe facilitar la lectura e interpretación del mapa, incluso con múltiples capas activas.                       
8.2 El sistema debe permitir identificar rápidamente acciones según su estado de validación.                        
8.3 La visualización debe mantenerse clara en diferentes niveles de zoom.

---

### Resultado esperado

Un visor geográfico que represente las acciones del PIGCCT con simbología diferenciada según su estado de validación, permitiendo un análisis visual claro, consistente y orientado al seguimiento y control del plan de cambio climático territorial.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-240.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-240.png)