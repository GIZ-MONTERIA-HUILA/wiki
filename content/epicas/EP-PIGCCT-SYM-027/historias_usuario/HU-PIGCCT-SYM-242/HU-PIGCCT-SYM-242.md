# HU-PIGCCT-SYM-242
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Mapas coropléticos por municipio

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                                 
> **Quiero:** visualizar mapas coropléticos por municipio en el visor geográfico del PIGCCT.                 
> **Para:** representar visualmente la intensidad de las acciones, el nivel de inversión o el grado de avance del plan a nivel municipal, facilitando el análisis comparativo y la toma de decisiones territoriales.

## CRITERIOS DE ACEPTACIÓN
### 1. Acceso a mapas coropléticos

1.1 El sistema debe permitir la visualización de mapas coropléticos a los usuarios con permisos de acceso al visor geográfico.                    
1.2 La opción debe estar disponible desde el panel de visualización o análisis del visor.              
1.3 La funcionalidad debe estar disponible únicamente cuando exista un PIGCCT activo y la capa de municipios esté habilitada.

### 2. Variables representables

2.1 El sistema debe permitir generar mapas coropléticos por municipio para al menos las siguientes variables:

- Cantidad de acciones.
- Valor de inversión (si la información está disponible).
- Nivel de avance del PIGCCT (porcentaje o categoría).

2.2 Las variables deben calcularse a partir de la información registrada y asociada al PIGCCT activo.                      
2.3 El sistema debe validar la disponibilidad de datos antes de generar el mapa.

### 3. Clasificación y rangos

3.1 El sistema debe permitir definir rangos de clasificación para el mapa coroplético, tales como:

- Intervalos iguales.
- Cuantiles.
- Clasificación definida por el sistema.

3.2 El número de clases debe ser configurable o definido por defecto por el sistema.                  
3.3 Los rangos deben recalcularse automáticamente al cambiar la variable seleccionada.

### 4. Simbología y visualización

4.1 Cada municipio debe representarse mediante una escala de color gradual acorde a la variable seleccionada.                        
4.2 La simbología debe cumplir criterios de:

- Claridad visual.
- Contraste adecuado.
- Accesibilidad (evitar combinaciones confusas).             

4.3 El mapa coroplético debe coexistir con las capas base y administrativas del visor.

### 5. Leyenda y valores

5.1 El visor debe mostrar una leyenda dinámica que indique:

- Variable representada.
- Rangos de valores.
- Escala de colores utilizada.

5.2 Al interactuar con un municipio, el sistema debe mostrar el valor específico de la variable representada.

### 6. Interacción y comportamiento del visor

6.1 El usuario debe poder:

- Activar y desactivar el mapa coroplético.

- Cambiar la variable representada sin recargar el visor.

6.2 El sistema debe mantener:

- Nivel de zoom.

- Posición del mapa.

- PIGCCT activo.

### 7. Manejo de errores y validaciones

7.1 Si no existen datos suficientes para generar el mapa coroplético, el sistema debe:

- Mostrar un mensaje informativo.

- No aplicar la simbología coroplética.

7.2 El sistema debe prevenir la visualización de datos inconsistentes o incompletos.

### 8. Usabilidad y experiencia de usuario

8.1 El mapa coroplético debe cargarse en un tiempo razonable, sin afectar el rendimiento del visor.                        
8.2 El usuario debe poder comparar visualmente municipios con facilidad.                          
8.3 La visualización debe mantenerse clara en diferentes niveles de zoom.

---

### Resultado esperado

Un visor geográfico con mapas coropléticos por municipio, que permita representar de forma clara e intuitiva la intensidad de acciones, inversión o avance del PIGCCT, apoyando el análisis territorial y la toma de decisiones estratégicas.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-242.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-242.png)