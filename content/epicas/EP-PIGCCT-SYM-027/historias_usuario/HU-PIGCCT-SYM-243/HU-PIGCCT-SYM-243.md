# HU-PIGCCT-SYM-243
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Interacción con el mapa – Seleccionar entidad geográfica

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                    
> **Quiero:** seleccionar una entidad geográfica (municipio o acción) directamente en el mapa del visor geográfico.                
> **Para:** visualizar su información asociada de forma inmediata, facilitando el análisis territorial y el acceso contextual a los datos del PIGCCT.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de selección

1.1 El sistema debe permitir la selección de entidades geográficas a todos los usuarios con permisos de acceso al visor geográfico.               
1.2 La funcionalidad debe estar disponible siempre que existan capas interactivas activas en el visor.                       
1.3 El sistema debe identificar automáticamente el tipo de entidad seleccionada (municipio o acción).

### 2. Entidades seleccionables

2.1 El sistema debe permitir seleccionar como mínimo las siguientes entidades:

- Municipios (cuando la capa de municipios esté activa).
- Acciones del PIGCCT (cuando la capa de acciones esté activa).

2.2 La selección debe corresponder únicamente a entidades asociadas al PIGCCT activo.

### 3. Comportamiento de la selección

3.1 Al seleccionar una entidad en el mapa, el sistema debe:

- Resaltar visualmente la entidad seleccionada.
- Desactivar el resaltado de selecciones previas.

3.2 La selección debe realizarse mediante interacción directa (clic o toque, según el dispositivo).                                  
3.3 El sistema debe mantener la selección visible incluso al cambiar el nivel de zoom.

### 4. Visualización de la información asociada

4.1 Al seleccionar un municipio, el sistema debe mostrar información básica asociada, como:
- Nombre del municipio.
- Código DANE (si aplica).
- Indicadores resumidos del PIGCCT en el municipio.

4.2 Al seleccionar una acción, el sistema debe mostrar información como:

- Nombre de la acción.
- Eje estratégico y medida asociada.
- Estado de validación.
- Cobertura territorial.

4.3 La información debe mostrarse mediante un popup o ficha informativa.

### 5. Interacción con otras funcionalidades

5.1 La selección de una entidad no debe afectar el PIGCCT activo ni la configuración de capas del visor.                             
5.2 El sistema debe permitir cambiar de entidad seleccionada sin recargar el visor.                      
5.3 La información mostrada debe actualizarse automáticamente al seleccionar una nueva entidad.

### 6. Manejo de errores y validaciones

6.1 Si no es posible obtener la información de la entidad seleccionada, el sistema debe:

- Mostrar un mensaje informativo.
- Mantener la entidad resaltada.

6.2 El sistema debe prevenir la selección de entidades no visibles o no activas.

### 7. Usabilidad y experiencia de usuario

7.1 La selección de entidades debe ser intuitiva y precisa.                        
7.2 El usuario debe poder identificar claramente la entidad seleccionada en el mapa.                      
7.3 La información asociada debe ser clara, concisa y legible.

---

### Resultado esperado

Un visor geográfico interactivo que permita seleccionar municipios o acciones, mostrando de manera inmediata su información asociada, fortaleciendo el análisis territorial y la gestión integral del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-243.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-243.png)