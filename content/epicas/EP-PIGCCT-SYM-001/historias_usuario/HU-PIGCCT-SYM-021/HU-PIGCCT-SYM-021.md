# HU-PIGCCT-SYM-021  
## Épica: Administración de ejes del PIGCCT  
### Consultar ejes inactivos

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (consulta o administrador).  
> **Quiero:** consultar los ejes inactivos de un PIGCCT.  
> **Para:** realizar análisis históricos, comparativos y de evolución de la estructura del plan territorial de gestión del cambio climático.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la consulta
1.1 El sistema debe permitir la consulta de ejes inactivos a usuarios con rol de **consulta** y **administrador**.  
1.2 Los ejes inactivos deben estar disponibles únicamente en modo lectura.



### 2. Disponibilidad del filtro de estado
2.1 El sistema debe contar con una opción para **visualizar ejes inactivos** en la vista de ejes del PIGCCT.  
2.2 El filtro debe permitir seleccionar al menos las siguientes opciones:
- Ejes activos.
- Ejes inactivos.
- Todos (activos e inactivos).



### 3. Selección del PIGCCT
3.1 El usuario debe seleccionar un PIGCCT para consultar sus ejes inactivos.  
3.2 El sistema debe permitir consultar ejes inactivos incluso cuando el PIGCCT esté inactivo.



### 4. Visualización de ejes inactivos
4.1 El sistema debe mostrar los ejes cuyo estado sea **inactivo**.  
4.2 Cada eje inactivo debe mostrar como mínimo:
- Nombre del eje.
- Descripción.
- Alcance (estratégico o transversal).
- Estado (inactivo).
- Fecha de inactivación (si está disponible).



### 5. Diferenciación visual
5.1 Los ejes inactivos deben diferenciarse visualmente de los activos mediante:
- Colores atenuados.
- Etiquetas o íconos distintivos.
- Estados claramente visibles.



### 6. Consulta de detalle
6.1 El usuario debe poder acceder a la vista de detalle de un eje inactivo.  
6.2 La vista de detalle debe ser de **solo lectura** e incluir información histórica relevante.



### 7. Manejo de resultados vacíos
7.1 Si no existen ejes inactivos asociados al PIGCCT seleccionado, el sistema debe mostrar un mensaje informativo, por ejemplo:
> “El PIGCCT seleccionado no cuenta con ejes inactivos registrados”.

7.2 El sistema debe permitir cambiar fácilmente el filtro para visualizar otros estados.



### 8. Usabilidad y experiencia de usuario
8.1 El acceso a la consulta de ejes inactivos debe ser claro y accesible desde la vista principal de ejes.  
8.2 El sistema debe mantener el contexto del PIGCCT seleccionado al cambiar entre filtros.

---

### Resultado esperado

El usuario puede **consultar los ejes inactivos de un PIGCCT**, accediendo a información histórica confiable que permita análisis comparativos y evaluación de la evolución del plan a lo largo del tiempo.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-021.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-021.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-012-023.png)
