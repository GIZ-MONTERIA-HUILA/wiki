# HU-PIGCCT-SYM-206
## Épica: Visor geográfico del PIGCCT 
### Acceso al visor geográfico
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** acceder a un visor geográfico interactivo.  
> **Para:** consultar territorialmente las acciones, indicadores y estadísticas del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Control de acceso y seguridad
1.1 El sistema permite el acceso al visor únicamente a usuarios con permisos autorizados.

1.2 Los perfiles de usuario determinan el nivel de acceso a capas, indicadores y estadísticas.

1.3 Los intentos de acceso no autorizado son bloqueados y gestionados según la política de seguridad.

### 2. Acceso al visor geográfico
2.1 El visor geográfico es accesible desde el sidebar principal del sistema.

2.2 El visor carga correctamente al ingresar, sin requerir recarga manual.

2.3 El sistema muestra un estado de carga mientras se inicializan los componentes del mapa.

### 3. Interactividad del visor
3.1 El visor permite navegar el mapa (zoom, paneo, centrado).

3.2 El usuario puede activar y desactivar capas de información del PIGCCT.

3.3 El visor permite consultar atributos de las entidades geográficas.

3.4 El visor responde de forma fluida a las interacciones del usuario.

### 4. Consulta territorial de información
4.1 El visor permite visualizar acciones del PIGCCT asociadas al territorio.

4.2 Los indicadores y estadísticas se muestran georreferenciados.

4.3 El usuario puede consultar información por área geográfica, región o unidad territorial.

4.4 La información presentada corresponde a los datos más recientes disponibles.

### 5. Integración con indicadores y estadísticas
5.1 El visor muestra indicadores clave asociados a la capa o área seleccionada.

5.2 Las estadísticas se actualizan según la selección geográfica realizada.

5.3 El visor se integra con tableros o paneles de información cuando aplique.

### 6. Usabilidad y experiencia de usuario
6.1 La interfaz del visor es intuitiva y consistente con el diseño general del sistema.

6.2 Los símbolos, colores y etiquetas facilitan la interpretación de la información territorial.

6.3 El visor es compatible con diferentes tamaños de pantalla.

### 7. Rendimiento y disponibilidad
7.1 El visor carga en un tiempo aceptable según los estándares definidos.

7.2 El sistema gestiona adecuadamente grandes volúmenes de datos geográficos.

7.3 En caso de error, el sistema muestra mensajes claros y permite la recuperación.

---

## Resultado esperado

Los usuarios autorizados pueden acceder a un visor geográfico interactivo que les permite consultar de manera territorial las acciones, indicadores y estadísticas del PIGCCT, facilitando el análisis espacial, la toma de decisiones y el seguimiento del plan.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-206.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-206.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-206.png)
