# HU-PIGCCT-SYM-245
## Épica: Detalle funcional del visor geográfico del PIGCCT
## Panel de detalle territorial

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                 
> **Quiero:** expandir un panel lateral desde el visor geográfico con el detalle territorial del municipio o acción seleccionada.                      
> **Para:** consultar información ampliada, estructurada y contextualizada del PIGCCT, sin perder la referencia espacial en el mapa.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al panel de detalle territorial

1.1 El sistema debe permitir la apertura de un panel lateral de detalle al seleccionar un municipio o una acción en el mapa.
1.2 El panel debe poder abrirse mediante una acción explícita del usuario (botón).                      
1.3 La funcionalidad debe estar disponible únicamente cuando exista una entidad seleccionada.

### 2. Entidades soportadas

2.1 El panel debe mostrar información detallada para:

- Municipios del departamento del PIGCCT activo.
- Acciones asociadas al PIGCCT activo.

2.2 El sistema debe identificar el tipo de entidad seleccionada para cargar el contenido correspondiente.

### 3. Contenido del panel – Municipio

3.1 Para un municipio, el panel debe mostrar como mínimo:

- Información general (nombre, código DANE).
- Resumen de acciones asociadas.
- Indicadores territoriales del PIGCCT (si aplica).
- Mapas o gráficos resumidos (opcional).

3.2 La información debe corresponder exclusivamente al PIGCCT activo.

### 4. Contenido del panel – Acción

4.1 Para una acción, el panel debe mostrar como mínimo:

- Nombre y descripción de la acción.
- Eje estratégico y medida asociada.
- Estado de validación.
- Cobertura territorial (municipal o departamental).
- Indicadores de avance y seguimiento (si aplica).

### 5. Comportamiento del panel

5.1 El panel lateral debe:

- Expandirse sin recargar el visor geográfico.
- Mantener visible el mapa en segundo plano.

5.2 El usuario debe poder:

- Cerrar el panel.
- Cambiar la entidad seleccionada y actualizar el contenido del panel.

5.3 Solo debe existir un panel de detalle activo a la vez.

### 6. Sincronización con el visor

6.1 Al abrir el panel, el sistema debe mantener resaltada la entidad seleccionada en el mapa.                
6.2 Si el usuario selecciona otra entidad, el panel debe actualizarse automáticamente.                   
6.3 El panel no debe alterar la configuración de capas ni el PIGCCT activo.

### 7. Manejo de errores y validaciones

7.1 Si no es posible cargar la información detallada, el sistema debe:

- Mostrar un mensaje informativo en el panel.
- Mantener operativa la navegación del visor.

7.2 El sistema debe prevenir inconsistencias entre la entidad seleccionada y la información mostrada.

### 8. Usabilidad y experiencia de usuario

8.1 El panel debe ser claro, organizado y fácil de navegar.                      
8.2 La información debe presentarse por secciones o pestañas, si aplica.                      
8.3 El diseño debe ser consistente con la interfaz general del sistema.

---

### Resultado esperado

Un visor geográfico con panel lateral de detalle territorial, que permita consultar información ampliada y estructurada de municipios o acciones del PIGCCT, manteniendo la referencia espacial y mejorando la experiencia de análisis y seguimiento territorial.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-245.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-245.png)