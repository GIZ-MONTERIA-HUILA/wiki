# HU-PIGCCT-SYM-171  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Navegación contextual

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** que el menú del sistema se adapte al contexto del módulo activo.  
> **Para:** reducir el ruido visual, facilitar la orientación y mejorar la experiencia de navegación dentro del sistema PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación del contexto activo
1.1 El sistema debe identificar automáticamente el **módulo activo** según la ruta o funcionalidad que el usuario esté utilizando.  
1.2 El módulo activo debe estar claramente marcado en el menú principal.


### 2. Adaptación del menú al contexto
2.1 El sistema debe mostrar en el menú únicamente:
- Las opciones relevantes al **módulo activo**.
- Las acciones más utilizadas dentro de dicho módulo.

2.2 Las opciones no relacionadas con el contexto actual:
- Deben ocultarse.
- O mostrarse de forma secundaria (según el diseño definido).


### 3. Panel contextual dinámico
3.1 El sistema debe habilitar un **panel contextual dinámico** que:
- Cambie según el módulo activo.
- Muestre accesos directos a funciones frecuentes del módulo.

3.2 El panel contextual debe actualizarse automáticamente al cambiar de módulo.


### 4. Persistencia de navegación principal
4.1 La navegación contextual **no debe reemplazar** el menú principal.  
4.2 El usuario debe poder regresar en cualquier momento a otros módulos del sistema.


### 5. Comportamiento por rol y permisos
5.1 La navegación contextual debe respetar las reglas de:
- Rol del usuario.
- Permisos asociados.

5.2 El sistema no debe mostrar opciones contextuales que el usuario no esté autorizado a utilizar.


### 6. Indicadores de orientación
6.1 El sistema debe mostrar indicadores visuales claros del contexto actual, tales como:
- Opción activa resaltada.
- Título del módulo.
- Breadcrumb de navegación.

6.2 Estos indicadores deben permitir al usuario comprender fácilmente:
- Dónde se encuentra.
- Qué acciones puede realizar.


### 7. Usabilidad y experiencia de usuario
7.1 La navegación contextual debe:
- Reducir el número de opciones visibles simultáneamente.
- Priorizar acciones frecuentes.
- Mejorar la legibilidad del menú.

7.2 El sistema debe mantener una experiencia consistente entre módulos, evitando cambios abruptos en la interfaz.


### 8. Seguridad y control de acceso
8.1 El sistema debe aplicar las mismas validaciones de seguridad en la navegación contextual que en el menú principal.  
8.2 El acceso a opciones no autorizadas debe ser bloqueado tanto visual como funcionalmente.

---

### Resultado esperado

El sistema ofrece una **navegación contextual adaptada al módulo activo**, que reduce el ruido visual, mejora la orientación del usuario y facilita el acceso a las funcionalidades relevantes, manteniendo el control de acceso y una experiencia de usuario clara y coherente dentro del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-171.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-171.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-171.png)
