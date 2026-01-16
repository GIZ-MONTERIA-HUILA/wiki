# HU-PIGCCT-SYM-172  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Propuesta de mapa de navegación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** contar con un mapa de navegación claro basado en un sidebar híbrido y un panel contextual.  
> **Para:** facilitar la exploración del sistema, mejorar la orientación y acceder de forma eficiente a las funcionalidades según mi rol y contexto de uso.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Modelo de navegación
1.1 El sistema debe implementar un **modelo de navegación basado en sidebar híbrido + panel contextual**.  
1.2 El modelo debe mantenerse consistente en todos los módulos del sistema.  
1.3 La navegación debe adaptarse al rol del usuario y al módulo activo.

### 2. Sidebar fijo (izquierdo)
2.1 El sistema debe mostrar un **sidebar fijo ubicado en el costado izquierdo** de la interfaz.  
2.2 El sidebar debe estar **siempre visible** durante la navegación.  
2.3 En estado expandido, el sidebar debe mostrar:
- Íconos representativos.
- Texto descriptivo de cada opción de menú.

### 3. Comportamiento del sidebar contraído
3.1 El sistema debe permitir **contraer el sidebar**.  
3.2 En estado contraído:
- Solo deben mostrarse los íconos.
- Cada ícono debe contar con un **tooltip informativo** que muestre el nombre de la opción.

3.3 El cambio entre estado expandido y contraído no debe afectar la navegación ni la información cargada.

### 4. Panel contextual dinámico
4.1 El sistema debe disponer de un **panel contextual dinámico** asociado al módulo activo.  
4.2 El panel contextual debe mostrar:
- Acciones frecuentes del módulo.
- Opciones específicas según el contexto.

4.3 El panel debe actualizarse automáticamente al cambiar de módulo.

### 5. Breadcrumb inteligente
5.1 El sistema debe mostrar un **breadcrumb inteligente** que refleje:
- La ruta de navegación actual.
- El módulo y submódulo activo.

5.2 El breadcrumb debe permitir la navegación hacia niveles superiores cuando aplique.  
5.3 El breadcrumb debe actualizarse dinámicamente según la navegación del usuario.

### 6. Accesos rápidos por estado
6.1 El sistema debe ofrecer **accesos rápidos** basados en el estado de los elementos, tales como:
- Acciones en borrador.
- Acciones en validación.
- Acciones rechazadas o pendientes.

6.2 Los accesos rápidos deben adaptarse al rol del usuario y a sus permisos.  
6.3 Estos accesos deben facilitar la gestión priorizada de tareas.

### 7. Comportamiento por rol y permisos
7.1 Todos los componentes del mapa de navegación deben respetar:
- El rol del usuario.
- Los permisos asignados.

7.2 El sistema no debe mostrar opciones o accesos que el usuario no esté autorizado a utilizar.

### 8. Usabilidad y experiencia de usuario
8.1 El mapa de navegación debe:
- Reducir el esfuerzo cognitivo del usuario.
- Mantener coherencia visual y funcional.
- Facilitar la orientación dentro del sistema.

8.2 El diseño debe ser consistente, accesible y alineado con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El sistema cuenta con un **mapa de navegación estructurado y coherente**, basado en un sidebar híbrido, panel contextual dinámico, breadcrumb inteligente y accesos rápidos por estado, que mejora la orientación, reduce el ruido visual y facilita el acceso eficiente a las funcionalidades del sistema PIGCCT según el rol y contexto del usuario.


---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-172.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-172.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-172.png)
