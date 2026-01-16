# HU-PIGCCT-SYM-234
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Carga inicial del visor

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                 
> **Quiero:** que el visor geográfico del PIGCCT se cargue automáticamente con una vista inicial centrada en el departamento del PIGCCT activo.                     
> **Para:** contextualizar territorialmente la información del plan, facilitar su análisis espacial y asegurar que el usuario visualice desde el inicio el ámbito geográfico correspondiente al PIGCCT seleccionado.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al visor geográfico

1.1 El sistema debe permitir el acceso al visor geográfico del PIGCCT.                     
1.2 El visor debe estar disponible desde los módulos relacionados con:

- Estructuración del PIGCCT.
- Seguimiento y monitoreo.
- Consulta geográfica del plan.

1.3 Al acceder al visor, el sistema debe identificar automáticamente el PIGCCT activo en sesión.

### 2. Inicialización del visor geográfico

2.1 Al cargar el visor, el sistema debe inicializar el mapa sin requerir interacción previa del usuario.                     
2.2 El visor debe utilizar una proyección cartográfica estándar definida por el sistema.                   

### 3. Carga inicial del visor

3.1 El sistema debe cargar automáticamente una vista inicial centrada en el departamento asociado al PIGCCT activo.                             
3.2 El área visible del mapa debe: I
- Incluir la totalidad del departamento.
- Ajustar el nivel de zoom para permitir una visualización clara del territorio.                                      

3.3 El límite departamental debe cargarse desde una fuente cartográfica oficial o capa base institucional.

### 4. Contextualización territorial

4.1 El visor debe resaltar visualmente el departamento del PIGCCT activo frente a otros territorios (por ejemplo, mediante color, borde o sombreado).                      
4.2 El sistema puede mostrar información básica del territorio, como:

- Nombre del departamento.
- Código DANE (si aplica).

4.3 Esta contextualización debe permitir al usuario comprender claramente el alcance territorial del PIGCCT desde la vista inicial.

### 5. Manejo de errores y validaciones

5.1 Si no existe un PIGCCT activo, el sistema debe:

- Bloquear la carga del visor.
- Mostrar un mensaje indicando que no hay un PIGCCT activo seleccionado.

5.2 Si ocurre un error en la carga de la capa geográfica del departamento, el sistema debe:

- Informar claramente el problema al usuario.
- Mantener la interfaz activa para reintentar la carga.

### 6. Usabilidad y experiencia de usuario

6.1 La carga inicial del visor debe realizarse en un tiempo razonable, sin afectar el rendimiento general del sistema.                        
6.2 El usuario debe poder:

- Desplazarse por el mapa.
-Ajustar el zoom.
- Activar o desactivar capas adicionales (si existen).
6.3 El visor debe mantener coherencia visual con el diseño general del sistema.

---

### Resultado esperado

Un visor geográfico correctamente inicializado, con una vista inicial centrada en el departamento del PIGCCT activo, que permita al usuario comprender de forma inmediata el contexto territorial del plan y facilite el análisis, seguimiento y gestión espacial del cambio climático territorial.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-234.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-234.png)