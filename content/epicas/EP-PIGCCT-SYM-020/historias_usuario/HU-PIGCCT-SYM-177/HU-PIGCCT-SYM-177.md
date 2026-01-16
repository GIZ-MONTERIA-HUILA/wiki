# HU-PIGCCT-SYM-177  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Listar acciones

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** visualizar un listado de acciones del PIGCCT.  
> **Para:** consultar, crear o editar la información de las acciones según mis permisos y rol dentro del sistema.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al listado de acciones
1.1 El sistema debe permitir a los usuarios autenticados acceder al **listado de acciones** desde el menú principal, según su rol y permisos.  
1.2 El acceso al listado debe estar restringido a usuarios autorizados.  
1.3 El sistema no debe permitir el acceso a usuarios no autenticados.

### 2. Visualización del listado
2.1 El sistema debe mostrar un **listado estructurado** de las acciones disponibles para el usuario.  
2.2 El listado debe incluir, como mínimo, información relevante de cada acción, tal como:
- Nombre de la acción.
- Estado.
- PIGCCT asociado.
- Responsable.
- Fechas relevantes.

2.3 El listado debe cargarse correctamente al acceder a la vista.

### 3. Filtrado y búsqueda
3.1 El sistema debe permitir **filtrar** el listado de acciones por criterios como:
- Estado.
- PIGCCT.
- Responsable.
- Periodo de tiempo.

3.2 El sistema debe permitir **buscar** acciones por texto libre (por ejemplo, nombre o código).  
3.3 Los filtros deben adaptarse a los permisos del usuario.

### 4. Acciones permitidas desde el listado
4.1 Desde el listado, el usuario debe poder:
- **Consultar** el detalle de una acción.
- **Crear** una nueva acción, si su rol lo permite.
- **Editar** una acción existente, si cuenta con los permisos correspondientes.

4.2 Las acciones disponibles deben mostrarse u ocultarse según el rol del usuario.

### 5. Comportamiento por rol y permisos
5.1 El sistema debe mostrar únicamente las acciones que el usuario está autorizado a visualizar.  
5.2 El sistema debe restringir la edición o creación de acciones según:
- Rol del usuario.
- Estado de la acción.

### 6. Navegación y continuidad
6.1 El usuario debe poder navegar desde el listado hacia:
- El detalle de la acción.
- El formulario de creación o edición.

6.2 La navegación no debe provocar pérdida de información sin advertencia previa.

### 7. Actualización de la información
7.1 El listado debe reflejar información **actualizada** sobre el estado de las acciones.  
7.2 Los cambios realizados en una acción deben reflejarse automáticamente en el listado.

### 8. Usabilidad y experiencia de usuario
8.1 El listado de acciones debe ser claro, ordenado y fácil de usar.  
8.2 El sistema debe facilitar la identificación rápida del estado de cada acción mediante indicadores visuales.  
8.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario puede **visualizar y gestionar un listado de acciones del PIGCCT**, accediendo a la consulta, creación o edición de información según sus permisos, con una vista clara, actualizada y alineada con el flujo de gestión del ciclo de vida de las acciones.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-177.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-177.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-177.png)
