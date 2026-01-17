# HU-PIGCCT-SYM-178  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Crear acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado con permisos de registro.  
> **Quiero:** registrar una nueva acción del PIGCCT en el sistema.  
> **Para:** estructurar y gestionar una intervención territorial, asociándola a los componentes estratégicos del plan.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la creación de acciones
1.1 El sistema debe permitir el acceso a la opción **“Crear acción”** únicamente a usuarios con permisos de registro.  
1.2 La opción debe estar disponible desde:
- El menú principal.
- El listado de acciones.

1.3 El sistema no debe permitir la creación de acciones a usuarios sin permisos.

### 2. Inicio del registro de la acción
2.1 Al seleccionar la opción **“Crear acción”**, el sistema debe mostrar el **formulario de registro de acciones del PIGCCT**.  
2.2 La acción debe crearse inicialmente en estado **Borrador**.  
2.3 El sistema debe asignar automáticamente un identificador único a la nueva acción.

### 3. Asociación con componentes del PIGCCT
3.1 El sistema debe permitir asociar la acción, como mínimo, con los siguientes componentes:
- **Eje**.
- **Medida**.
- **Territorio**.
- **Indicadores**.

3.2 Las asociaciones deben realizarse mediante selecciones controladas desde catálogos y estructuras definidas del PIGCCT.  
3.3 El sistema debe validar la coherencia entre eje, medida e indicadores seleccionados.

### 4. Formulario guiado y validaciones
4.1 El formulario de creación debe ser **guiado por secciones o pestañas**, facilitando el diligenciamiento progresivo.  
4.2 El sistema debe aplicar validaciones en tiempo real sobre los campos obligatorios.  
4.3 El sistema no debe permitir finalizar el registro si existen campos críticos sin diligenciar.

### 5. Guardado progresivo
5.1 El sistema debe permitir el **guardado progresivo** de la información ingresada.  
5.2 El usuario debe poder guardar la acción en estado borrador y continuar su edición posteriormente.  
5.3 El sistema debe confirmar visualmente cada guardado exitoso.

### 6. Comportamiento por rol y permisos
6.1 El sistema debe habilitar o deshabilitar campos del formulario según:
- Rol del usuario.
- Estado de la acción.

6.2 Los usuarios solo deben poder registrar acciones dentro del alcance permitido por su rol.

### 7. Persistencia e integridad de la información
7.1 El sistema debe almacenar de forma segura toda la información asociada a la acción.  
7.2 La acción creada debe quedar disponible en el listado de acciones del usuario.  
7.3 La información debe estar preparada para los procesos de validación, seguimiento y monitoreo.

### 8. Usabilidad y experiencia de usuario
8.1 El proceso de creación de acciones debe ser claro, intuitivo y consistente con el diseño del sistema.  
8.2 El sistema debe prevenir la pérdida de información mediante validaciones y mensajes de advertencia.  
8.3 El usuario debe poder cancelar el proceso sin guardar cambios, con confirmación previa.

---

## Resultado esperado

El usuario puede **crear una nueva acción del PIGCCT**, asociándola correctamente a eje, medida, territorio e indicadores, quedando registrada en estado borrador y lista para su edición, validación y seguimiento dentro del ciclo de vida del sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-178.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-178.png)


