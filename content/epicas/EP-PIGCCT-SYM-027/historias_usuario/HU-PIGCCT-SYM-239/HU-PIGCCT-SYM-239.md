# HU-PIGCCT-SYM-239
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Control de visibilidad de capas

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                        
> **Quiero:** activar o desactivar las capas disponibles en el visor geográfico del PIGCCT.                       
> **Para:** personalizar la visualización del mapa según mis necesidades de análisis, mejorando la comprensión territorial y evitando la saturación de información.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al control de capas

1.1 El sistema debe permitir el control de visibilidad de las capas a los usuarios con permisos de acceso al visor geográfico.                 
1.2 El control de capas debe estar disponible en un panel de capas visible y accesible dentro del visor.                   
1.3 El panel debe listar todas las capas disponibles según el contexto del PIGCCT activo.

### 2. Capas gestionables

2.1 El sistema debe permitir activar o desactivar como mínimo las siguientes capas:

- Capas base.
- Límites departamentales.
- Capa de municipios.
- Capa de acciones del PIGCCT.
- Otras capas temáticas configuradas en el sistema.

2.2 Las capas deben agruparse de forma lógica (base, administrativas, temáticas).

### 3. Comportamiento de activación y desactivación

3.1 Al activar una capa, esta debe visualizarse inmediatamente en el visor.                          
3.2 Al desactivar una capa, esta debe ocultarse sin afectar las demás capas activas.                      
3.3 La activación o desactivación de capas debe realizarse sin recargar completamente el visor.

### 4. Consistencia y dependencias

4.1 El sistema debe prevenir inconsistencias visuales al activar múltiples capas simultáneamente.                     
4.2 El control de visibilidad no debe modificar el PIGCCT activo.

### 5. Persistencia de la configuración

5.1 El sistema puede mantener la configuración de capas activas durante la sesión del usuario.                      
5.2 Al cambiar el PIGCCT activo, el sistema debe:

- Mantener las capas activas cuando sea posible.
- Actualizar su contenido según el nuevo PIGCCT seleccionado.

### 6. Manejo de errores y validaciones

6.1 Si una capa no puede cargarse, el sistema debe:

- Mostrar un mensaje informativo.
- Mantener operativas las demás capas del visor.

6.2 El sistema debe evitar la activación de capas no disponibles para el PIGCCT activo.

### 7. Usabilidad y experiencia de usuario

7.1 El panel de capas debe ser intuitivo y fácil de usar.
7.2 El usuario debe poder identificar claramente qué capas están activas o inactivas.
7.3 El control de capas debe permitir una visualización fluida y ordenada del visor.

---

### Resultado esperado

Un visor geográfico con control completo de visibilidad de capas, que permita al usuario personalizar la visualización del mapa de forma flexible, clara y coherente con el PIGCCT activo.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-239.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-239.png)