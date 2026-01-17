# HU-PIGCCT-SYM-212
## Épica: Visor geográfico del PIGCCT 
### Filtrar acciones por estado de validación
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** filtrar las acciones por su estado de validación (borrador, en validación, validado).  
> **Para:** visualizar únicamente la información permitida según mi rol y garantizar el control de la información del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Disponibilidad del filtro por estado
1.1 El sistema dispone de un filtro específico para el estado de validación de las acciones.

1.2 Los estados disponibles incluyen, como mínimo: Borrador, En validación y Validado.

1.3 Los valores del filtro se muestran de manera clara y comprensible para el usuario.

### 2. Restricciones por rol
2.1 El sistema valida el rol del usuario antes de permitir la visualización de acciones según su estado.

2.2 Los usuarios solo pueden seleccionar y visualizar los estados de validación permitidos por su rol.

2.3 Las acciones cuyo estado no esté autorizado para el rol del usuario no se muestran en el mapa ni en los paneles asociados.

### 3. Funcionamiento del filtro
3.1 El usuario puede seleccionar uno o varios estados de validación según los permisos asignados.

3.2 Al aplicar el filtro, el visor actualiza automáticamente la visualización del mapa.

3.3 Solo se visualizan las acciones que coinciden con los estados de validación seleccionados.

### 4. Integración con otros filtros
4.1 El filtro por estado de validación puede combinarse con filtros territoriales y temáticos (departamento, municipio, eje, medida, indicador).

4.2 El sistema aplica los filtros de manera conjunta, mostrando únicamente las acciones que cumplen todos los criterios seleccionados.

4.3 No se generan conflictos ni inconsistencias al combinar filtros de estado con otros filtros disponibles.

### 5. Comportamiento del visor y la interfaz
5.1 Las acciones no autorizadas por estado o rol no se visualizan ni son accesibles desde el mapa.

5.2 El estado de validación de las acciones visibles puede identificarse claramente en la información asociada (panel contextual, ficha o tabla).

5.3 El sistema ofrece una opción para limpiar o restablecer el filtro de estado.

### 6. Seguridad, trazabilidad y rendimiento
6.1 El control de visualización por estado se gestiona tanto en la interfaz como a nivel de servicios o consultas.

6.2 El sistema garantiza que no se pueda acceder a información no autorizada mediante manipulación de filtros.

6.3 La aplicación del filtro se realiza con tiempos de respuesta adecuados y comportamiento consistente.

---

## Resultado esperado

El sistema permite filtrar las acciones por su estado de validación, asegurando que cada usuario visualice únicamente la información acorde a su rol, fortaleciendo el control, la seguridad y la confiabilidad de la información del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-212.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-212.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-212.png)
