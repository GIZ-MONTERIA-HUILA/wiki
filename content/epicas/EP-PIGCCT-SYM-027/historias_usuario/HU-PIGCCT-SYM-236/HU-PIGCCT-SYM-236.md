# HU-PIGCCT-SYM-236
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Visualizar capas base

---
 
## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                         
> **Quiero:** seleccionar y cambiar las capas base del visor geográfico (cartográfica, satelital e híbrida).                        
> **Para:** mejorar la interpretación territorial del PIGCCT, facilitando el análisis espacial según el tipo de información que se requiera visualizar.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de capas base

1.1 El sistema debe permitir el acceso a la selección de capas base a todos los usuarios con permisos de visualización del visor geográfico.                    
1.2 La opción de selección de capas base debe estar disponible dentro del visor, mediante un control visible y accesible tipo panel lateral.                   
1.3 La funcionalidad debe estar disponible sin importar el módulo desde el cual se acceda al visor.

### 2. Tipos de capas base disponibles

2.1 El sistema debe permitir seleccionar como mínimo las siguientes capas base:

- Cartográfica (mapa base con límites administrativos, vías y topónimos).
- Satelital (imágenes satelitales).
- Híbrida (combinación de imagen satelital con etiquetas cartográficas).

2.2 Las capas base deben provenir de fuentes oficiales o servicios cartográficos configurados por el sistema.                      
2.3 El nombre de cada capa base debe mostrarse de forma clara y comprensible para el usuario.

### 3. Selección y visualización de capas base

3.1 El sistema debe permitir cambiar la capa base en tiempo real, sin recargar el visor completo.                        
3.2 Al seleccionar una capa base, esta debe:

- Reemplazar la capa base actualmente activa.
- Mantener visibles las capas temáticas del PIGCCT cargadas.

3.3 El cambio de capa base no debe afectar la información asociada al PIGCCT activo.

### 4. Comportamiento del visor

4.1 El visor debe conservar:

- El nivel de zoom actual.
- La posición del mapa.
- El PIGCCT activo seleccionado.

4.2 El sistema debe garantizar una correcta superposición entre la capa base y las capas temáticas del PIGCCT.                           
4.3 Las capas base deben ajustarse automáticamente a la proyección cartográfica definida por el sistema.

### 5. Manejo de errores y validaciones

5.1 Si una capa base no puede cargarse, el sistema debe:

- Mantener la última capa base activa.
- Mostrar un mensaje informativo indicando el inconveniente.

5.2 El sistema debe prevenir la selección simultánea de más de una capa base.

### 6. Usabilidad y experiencia de usuario

6.1 El selector de capas base debe ser intuitivo y fácil de usar.           
6.2 El sistema debe permitir al usuario identificar claramente cuál capa base se encuentra activa.                       
6.3 El cambio de capas base debe realizarse en un tiempo razonable, sin afectar el rendimiento del visor.

---

### Resultado esperado

Un visor geográfico con capas base seleccionables, que permita alternar entre vistas cartográfica, satelital e híbrida, mejorando la comprensión espacial del territorio y apoyando la toma de decisiones en la gestión del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-236.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-236.png)