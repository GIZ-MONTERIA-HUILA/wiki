# HU-PIGCCT-SYM-237
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Visualizar capa de municipios

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                       
> **Quiero:** visualizar la capa geográfica de municipios correspondiente al departamento del PIGCCT activo.                               
> **Para:** contar con una referencia territorial detallada que facilite la ubicación, análisis y contextualización espacial de la información asociada al PIGCCT.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la capa de municipios

1.1 El sistema debe permitir la visualización de la capa de municipios a los usuarios con permisos de acceso al visor geográfico.                   
1.2 La opción para activar o desactivar la capa debe estar disponible en el panel de capas del visor.                       
1.3 La activación de la capa debe ser independiente de la selección de la capa base.

### 2. Alcance territorial de la capa

2.1 El sistema debe mostrar únicamente los municipios pertenecientes al departamento del PIGCCT activo.                                 
2.2 Los límites municipales deben cargarse desde una fuente cartográfica oficial o institucional.                          
2.3 La capa no debe mostrar municipios de otros departamentos distintos al PIGCCT activo.

### 3. Visualización y simbología

3.1 Los límites municipales deben representarse mediante una simbología clara y diferenciable (líneas, colores o patrones).                    
3.2 La visualización de la capa debe permitir distinguir claramente:

- Límites municipales.
- Límites departamentales (si están activos).

3.3 La simbología debe ser coherente con los lineamientos visuales del sistema.

### 4. Interacción con la capa de municipios

4.1 El sistema debe permitir la interacción básica con la capa, como:

- Activar y desactivar la capa.
- Visualizar el nombre del municipio al pasar el cursor o seleccionar el elemento (popup).

4.2 El sistema puede mostrar información básica del municipio, como:

- Nombre.
- Código DANE (si aplica).

### 5. Comportamiento frente al PIGCCT activo

5.1 Al cambiar el PIGCCT activo, la capa de municipios debe actualizarse automáticamente según el nuevo departamento seleccionado.                       
5.2 La actualización debe realizarse sin recargar completamente el visor geográfico.                        
5.3 La capa debe mantenerse sincronizada con la selección del PIGCCT activo durante toda la sesión del usuario.

### 6. Manejo de errores y validaciones

6.1 Si la capa de municipios no puede cargarse, el sistema debe:

- Mostrar un mensaje informativo indicando el error.
- Mantener operativas las demás capas del visor.

6.2 El sistema debe prevenir inconsistencias entre el departamento del PIGCCT activo y la capa de municipios mostrada.

### 7. Usabilidad y experiencia de usuario

7.1 La capa de municipios debe cargarse en un tiempo razonable, sin afectar el rendimiento del visor.                      
7.2 El usuario debe poder activar o desactivar la capa sin perder la configuración actual del mapa (zoom y posición).                            
7.3 La visualización debe facilitar la lectura del territorio incluso con otras capas activas.

---

### Resultado esperado

Un visor geográfico con la capa de municipios correctamente visualizada, limitada al departamento del PIGCCT activo, que sirva como referencia territorial clara para el análisis, seguimiento y gestión del Plan Integral de Gestión del Cambio Climático Territorial.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-237.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-237.png)