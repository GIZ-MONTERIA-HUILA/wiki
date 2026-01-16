# HU-PIGCCT-SYM-238
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Visualizar capa de acciones del PIGCCT

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                            
> **Quiero:** visualizar las acciones del PIGCCT como una capa geográfica en el visor.                       
> **Para:** analizar su distribución territorial, identificar el alcance municipal o departamental de las acciones y apoyar el seguimiento y la toma de decisiones del Plan Integral de Gestión del Cambio Climático Territorial.

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la capa de acciones

1.1 El sistema debe permitir la visualización de la capa geográfica de acciones del PIGCCT a los usuarios con permisos de acceso al visor geográfico.                      
1.2 La activación o desactivación de la capa debe realizarse desde el panel de capas del visor.                         
1.3 La capa de acciones debe estar disponible únicamente cuando exista un PIGCCT activo.

### 2. Fuente y alcance de la información

2.1 El sistema debe cargar las acciones asociadas exclusivamente al PIGCCT activo.                          
2.2 Cada acción debe estar georreferenciada según su alcance territorial, el cual puede ser:

- Municipal (asociada a uno o varios municipios).
- Departamental (cobertura total del departamento).

2.3 La información geográfica debe provenir de los registros oficiales del sistema.

### 3. Representación geográfica de las acciones

3.1 Las acciones con alcance municipal deben representarse sobre el territorio correspondiente a cada municipio.                      
3.2 Las acciones con alcance departamental deben representarse sobre la totalidad del departamento del PIGCCT activo.                     
3.3 El sistema debe utilizar una simbología diferenciada para distinguir el tipo de cobertura de las acciones (municipal vs. departamental).

### 4. Visualización y simbología

4.1 La capa de acciones debe ser claramente visible sobre la capa base seleccionada.                       
4.2 La simbología debe ser consistente con los lineamientos gráficos del sistema y permitir:

- Diferenciar acciones por tipo, estado o eje estratégico (si aplica).
- Identificar fácilmente la cobertura territorial.

4.3 El sistema debe incluir una leyenda dinámica asociada a la capa de acciones.

### 5. Interacción con la capa de acciones

5.1 El sistema debe permitir la interacción con las acciones visualizadas, tales como:

- Seleccionar una acción en el mapa.
- Visualizar un popup o panel con información básica de la acción.

5.2 La información mínima a mostrar debe incluir:

- Nombre de la acción.
- Municipio(s) o cobertura territorial.
- Estado de la acción.

### 6. Comportamiento frente al cambio de PIGCCT activo

6.1 Al cambiar el PIGCCT activo, la capa de acciones debe actualizarse automáticamente.                         
6.2 El sistema debe eliminar del visor las acciones correspondientes al PIGCCT previamente activo.                        
6.3 La actualización debe realizarse sin recargar completamente el visor geográfico.

### 7. Manejo de errores y validaciones

7.1 Si no existen acciones registradas para el PIGCCT activo, el sistema debe:

- Mostrar un mensaje informativo al usuario.
- Mantener operativas las demás capas del visor.

7.2 Si ocurre un error en la carga de la capa, el sistema debe notificar claramente el problema.

### 8. Usabilidad y experiencia de usuario

8.1 La carga de la capa de acciones debe realizarse en un tiempo razonable, sin afectar el rendimiento del visor.                  
8.2 El usuario debe poder activar o desactivar la capa sin perder la configuración actual del mapa.                        
8.3 La visualización debe permitir una lectura clara del territorio incluso con múltiples capas activas.

---

### Resultado esperado

Un visor geográfico con la capa de acciones del PIGCCT correctamente visualizada, representando su cobertura municipal o departamental, que permita analizar su distribución territorial y facilite el seguimiento integral del plan de cambio climático.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-238.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-238.png)