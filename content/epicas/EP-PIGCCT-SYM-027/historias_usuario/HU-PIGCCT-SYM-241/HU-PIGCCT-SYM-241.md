# HU-PIGCCT-SYM-241
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Simbología por eje o medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                        
> **Quiero:** cambiar la simbología de las acciones del PIGCCT en el visor geográfico según el eje estratégico o la medida seleccionada.                        
> **Para:** analizar visualmente la distribución territorial de las acciones por componente del plan, facilitando la interpretación, comparación y seguimiento del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la configuración de simbología

1.1 El sistema debe permitir la configuración de la simbología por eje o medida a los usuarios con permisos de acceso al visor geográfico.                 
1.2 La opción debe estar disponible desde el panel de configuración o simbología del visor.                        
1.3 La funcionalidad debe estar disponible únicamente cuando la capa de acciones esté activa.

### 2. Opciones de simbología disponibles

2.1 El sistema debe permitir seleccionar como criterio de simbología:

- Eje estratégico del PIGCCT.
- Medida asociada a la acción.

2.2 El sistema debe cargar automáticamente los ejes y medidas asociados al PIGCCT activo.                     
2.3 Las opciones deben presentarse de forma clara y comprensible para el usuario.

### 3. Aplicación de la simbología

3.1 Al seleccionar un eje o una medida, el sistema debe aplicar automáticamente una simbología diferenciada a las acciones visibles en el visor.                        
3.2 Cada eje o medida debe representarse mediante una simbología visual distinta, que puede incluir:

- Color.
- Forma.
- Estilo o patrón.

3.3 La aplicación de la simbología debe realizarse en tiempo real, sin recargar el visor completo.

### 4. Comportamiento del visor

4.1 El sistema debe mantener:

- El nivel de zoom.
- La posición del mapa.
- El PIGCCT activo.

4.2 El cambio de simbología no debe afectar la visibilidad ni la interacción con las acciones.                     
4.3 El sistema debe garantizar coherencia visual entre la simbología aplicada y la información mostrada.

### 5. Leyenda dinámica

5.1 El visor debe mostrar una leyenda dinámica que refleje la simbología aplicada por eje o medida.                
5.2 La leyenda debe actualizarse automáticamente al cambiar el criterio de simbología.                   
5.3 El usuario debe poder consultar la leyenda en cualquier momento.

### 6. Interacción con las acciones

6.1 Al seleccionar una acción en el mapa, el sistema debe mostrar información detallada, incluyendo:

- Nombre de la acción.
- Eje estratégico.
- Medida asociada.

6.2 La simbología debe facilitar la identificación del eje o medida correspondiente.

### 7. Manejo de errores y validaciones

7.1 Si una acción no tiene eje o medida asociada, el sistema debe:

- Aplicar una simbología por defecto.
- Informar la situación mediante un indicador visual.

7.2 El sistema debe prevenir inconsistencias entre la información registrada y la simbología mostrada.

### 8. Usabilidad y experiencia de usuario

8.1 El cambio de simbología debe ser intuitivo y fácil de usar.                  
8.2 El usuario debe poder comparar visualmente la distribución territorial de las acciones por eje o medida.                       
8.3 La visualización debe mantenerse clara en diferentes niveles de zoom.

---

### Resultado esperado

Un visor geográfico que permita cambiar dinámicamente la simbología de las acciones del PIGCCT según eje estratégico o medida, facilitando el análisis territorial, la comparación visual y el seguimiento efectivo del plan de cambio climático.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-241.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-241.png)