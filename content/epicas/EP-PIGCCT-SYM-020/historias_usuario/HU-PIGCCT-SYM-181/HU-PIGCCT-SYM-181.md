# HU-PIGCCT-SYM-181  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Visualizar acciones en el visor geográfico

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** visualizar las acciones del PIGCCT en un visor geográfico.  
> **Para:** analizar su distribución territorial y apoyar la toma de decisiones con base espacial.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al visor geográfico
1.1 El sistema debe permitir el acceso al **visor geográfico** a usuarios autenticados según su rol y permisos.  
1.2 El acceso al visor debe estar disponible desde:
- El menú principal.
- El módulo de acciones, cuando aplique.

1.3 El sistema no debe permitir el acceso a usuarios no autorizados.

### 2. Visualización de acciones en el mapa
2.1 El sistema debe mostrar en el visor geográfico las **acciones del PIGCCT** con información territorial asociada.  
2.2 Las acciones deben representarse mediante elementos geográficos adecuados, tales como:
- Puntos.
- Polígonos.
- Áreas de cobertura departamental o municipal.

2.3 La visualización debe reflejar correctamente la cobertura territorial definida para cada acción.

### 3. Filtrado y control de capas
3.1 El sistema debe permitir filtrar las acciones visualizadas en el mapa por criterios como:
- Estado de la acción.
- PIGCCT.
- Eje o medida.
- Territorio.

3.2 El usuario debe poder activar o desactivar capas de acciones según sus necesidades de análisis.

### 4. Información asociada a las acciones
4.1 Al seleccionar una acción en el visor, el sistema debe mostrar información básica, como:
- Nombre de la acción.
- Estado.
- Eje y medida asociados.
- Territorio de intervención.

4.2 El usuario debe poder acceder al detalle de la acción desde el visor, según permisos.

### 5. Comportamiento por rol y permisos
5.1 El visor geográfico debe mostrar únicamente las acciones que el usuario esté autorizado a visualizar.  
5.2 El sistema no debe permitir el acceso a información geográfica restringida.

### 6. Actualización de la información
6.1 La información geográfica debe mantenerse **actualizada** conforme cambien los estados o atributos de las acciones.  
6.2 Los cambios en una acción deben reflejarse automáticamente en el visor.

### 7. Usabilidad y experiencia de usuario
7.1 El visor geográfico debe ser claro, interactivo y fácil de usar.  
7.2 El sistema debe permitir una navegación fluida en el mapa (zoom, desplazamiento).  
7.3 La simbología y colores deben ser consistentes y facilitar la interpretación territorial.

---

## Resultado esperado

El usuario puede **visualizar las acciones del PIGCCT en un visor geográfico**, analizando su distribución territorial mediante una representación clara, interactiva y actualizada, que respeta los permisos del usuario y apoya el análisis espacial y la toma de decisiones.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-181.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-181.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-181.png)
