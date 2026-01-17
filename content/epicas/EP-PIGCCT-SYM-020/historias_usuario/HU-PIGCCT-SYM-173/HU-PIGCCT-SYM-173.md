# HU-PIGCCT-SYM-173  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Acceder al dashboard

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** acceder a un panel de inicio (dashboard) al ingresar al sistema.  
> **Para:** visualizar de forma sintética y priorizada el estado general de las acciones y validaciones del PIGCCT, según mi rol.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al dashboard
1.1 El sistema debe permitir a todo **usuario autenticado** acceder al **dashboard**.  
1.2 El dashboard debe ser la **vista inicial por defecto** después del inicio de sesión, salvo que el rol defina otro comportamiento.  
1.3 El usuario debe poder acceder al dashboard en cualquier momento desde el menú principal.

### 2. Propósito del dashboard
2.1 El dashboard debe brindar una **vista sintética y priorizada** del estado del PIGCCT.  
2.2 La información presentada debe apoyar la gestión diaria del usuario según su rol.  
2.3 El contenido debe enfocarse en el estado de las acciones y validaciones.

### 3. Contenido mínimo del dashboard
3.1 El sistema debe mostrar como mínimo los siguientes bloques de información:
- **Acciones en borrador**.  
- **Acciones en validación**.  
- **Acciones validadas**.  
- **Alertas de seguimiento**.

3.2 Cada bloque debe mostrar información clara y resumida, como contadores o indicadores visuales.

### 4. Comportamiento por rol
4.1 El contenido del dashboard debe adaptarse al **rol del usuario**, mostrando únicamente información relevante y autorizada.  
4.2 El sistema no debe mostrar información de acciones o validaciones a las que el usuario no tenga acceso.

### 5. Navegación desde el dashboard
5.1 Cada bloque del dashboard debe permitir:
- Acceder al listado correspondiente.
- Visualizar el detalle según permisos.

5.2 La navegación desde el dashboard no debe generar pérdida de información en otras vistas.

### 6. Indicadores y alertas
6.1 El sistema debe mostrar **alertas de seguimiento** relacionadas con:
- Acciones con fechas próximas.
- Seguimientos pendientes.
- Indicadores con retraso, si aplica.

6.2 Las alertas deben ser visibles y priorizadas según su relevancia.

### 7. Usabilidad y experiencia de usuario
7.1 El dashboard debe ser claro, visualmente ordenado y fácil de interpretar.  
7.2 La información debe presentarse de forma resumida, evitando sobrecarga visual.  
7.3 El diseño del dashboard debe ser coherente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario autenticado puede **acceder a un dashboard inicial** que presenta una **vista clara, sintética y priorizada del estado del PIGCCT**, con información sobre acciones, validaciones y alertas de seguimiento, adaptada a su rol y facilitando la gestión diaria dentro del sistema.


---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-173.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-173.png)

