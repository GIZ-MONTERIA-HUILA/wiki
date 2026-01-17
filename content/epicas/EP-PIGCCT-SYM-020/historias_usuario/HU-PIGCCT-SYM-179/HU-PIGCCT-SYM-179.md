# HU-PIGCCT-SYM-179  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Editar acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado con permisos de registro.  
> **Quiero:** editar una acción del PIGCCT que se encuentre en estado borrador o rechazada.  
> **Para:** realizar ajustes, corregir observaciones y preparar la acción para su envío a validación.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la edición de acciones
1.1 El sistema debe permitir editar acciones únicamente a usuarios con permisos de registro.  
1.2 La opción **“Editar acción”** debe estar disponible desde:
- El listado de acciones.
- La vista de detalle de la acción.

1.3 El sistema no debe permitir la edición a usuarios sin permisos.

### 2. Estados permitidos para edición
2.1 El sistema debe permitir la edición de acciones que se encuentren en los siguientes estados:
- **Borrador**.
- **Rechazada**.

2.2 Las acciones en otros estados (por ejemplo, en validación o validadas) no deben ser editables.

### 3. Carga de la información existente
3.1 Al acceder a la edición, el sistema debe cargar automáticamente toda la información previamente registrada de la acción.  
3.2 El usuario debe visualizar los datos actuales y poder modificarlos según sus permisos.

### 4. Validaciones durante la edición
4.1 El sistema debe aplicar las mismas validaciones definidas para la creación de acciones.  
4.2 El sistema debe validar la coherencia de la información modificada antes de permitir el guardado.

### 5. Guardado progresivo
5.1 El sistema debe permitir el **guardado progresivo** de los cambios realizados.  
5.2 El usuario debe poder guardar los cambios sin necesidad de completar todo el formulario.  
5.3 El sistema debe confirmar visualmente cada guardado exitoso.

### 6. Manejo de acciones rechazadas
6.1 Cuando una acción se encuentre en estado **Rechazada**, el sistema debe:
- Mostrar las observaciones registradas durante la validación.
- Permitir la corrección de la información observada.

6.2 Las observaciones deben permanecer visibles durante el proceso de edición.

### 7. Control de acceso y seguridad
7.1 El sistema debe garantizar que el usuario solo pueda editar acciones:
- Que haya creado.
- O que estén dentro de su ámbito de responsabilidad, según rol.

7.2 El sistema debe bloquear cualquier intento de edición no autorizado.

### 8. Usabilidad y experiencia de usuario
8.1 El proceso de edición debe ser claro y consistente con el formulario de creación.  
8.2 El sistema debe prevenir la pérdida de información mediante advertencias y confirmaciones.  
8.3 El usuario debe poder cancelar la edición sin guardar cambios, con confirmación previa.

---

## Resultado esperado

El usuario puede **editar correctamente una acción del PIGCCT en estado borrador o rechazada**, realizando los ajustes necesarios para corregir observaciones y preparar la acción para su posterior envío a validación, manteniendo la integridad y trazabilidad de la información.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-179.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-179.png)


