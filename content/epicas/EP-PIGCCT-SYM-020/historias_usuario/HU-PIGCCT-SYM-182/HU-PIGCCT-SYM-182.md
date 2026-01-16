# HU-PIGCCT-SYM-182  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Listar acciones pendientes de validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario validador.  
> **Quiero:** visualizar un listado de acciones pendientes de validación.  
> **Para:** revisar, analizar y gestionar oportunamente las acciones que requieren aprobación dentro del flujo institucional del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al listado de validaciones
1.1 El sistema debe permitir el acceso al **listado de acciones pendientes de validación** únicamente a usuarios con rol de **validador** (entidad o CAR) y **administrador**.  
1.2 El acceso debe estar disponible desde el menú principal, dentro del módulo de **Validaciones**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos de validación.

### 2. Filtrado por rol validador
2.1 El sistema debe filtrar automáticamente las acciones mostradas según el **rol del validador**, mostrando solo aquellas que le corresponden revisar.  
2.2 Para el **validador entidad**, deben mostrarse únicamente las acciones pendientes de validación por entidad.  
2.3 Para el **validador CAR**, deben mostrarse únicamente las acciones pendientes de validación en la etapa correspondiente a la CAR.

### 3. Visualización del listado
3.1 El sistema debe mostrar un **listado estructurado** de las acciones pendientes de validación.  
3.2 El listado debe incluir, como mínimo, la siguiente información:
- Nombre de la acción.  
- Estado actual.  
- PIGCCT asociado.  
- Entidad responsable.  
- Fecha de envío a validación.

3.3 El listado debe cargarse correctamente al acceder a la vista.

### 4. Ordenamiento y priorización
4.1 El sistema debe permitir ordenar las acciones pendientes por criterios como:
- Fecha de envío.
- Nivel de prioridad.
- PIGCCT.

4.2 Las acciones más antiguas o prioritarias deben poder identificarse fácilmente.

### 5. Acciones disponibles desde el listado
5.1 Desde el listado, el usuario validador debe poder:
- Acceder al **detalle de la acción**.
- Iniciar el proceso de **validación o rechazo**, según permisos.

5.2 Las acciones disponibles deben respetar el flujo de validación definido.

### 6. Actualización del listado
6.1 El listado debe reflejar información **actualizada** sobre el estado de las acciones.  
6.2 Una vez una acción sea validada o rechazada, debe desaparecer automáticamente del listado de pendientes.

### 7. Control de acceso y seguridad
7.1 El sistema debe garantizar que cada validador visualice únicamente las acciones que le correspondan.  
7.2 El acceso por navegación directa a acciones no autorizadas debe estar bloqueado.

### 8. Usabilidad y experiencia de usuario
8.1 El listado de acciones pendientes debe ser claro, ordenado y fácil de usar.  
8.2 El sistema debe facilitar la identificación rápida de acciones pendientes mediante indicadores visuales.  
8.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario validador puede **visualizar un listado actualizado de acciones pendientes de validación**, filtrado automáticamente según su rol, permitiendo una gestión eficiente, ordenada y segura del proceso de revisión y aprobación institucional del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-182.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-182.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-182.png)
