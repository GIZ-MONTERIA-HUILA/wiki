# HU-PIGCCT-SYM-163  
## Épica: Formulario de Registro y Gestión de Acciones del PIGCCT  
### Diligenciar información general

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** diligenciar la información general de una acción dentro del formulario del PIGCCT.  
> **Para:** registrar la información básica del proyecto territorial, garantizando que la acción quede correctamente definida para su estructuración, seguimiento y validación.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la sección “Información general”
1.1 El sistema debe permitir el acceso a la pestaña **“Información general”** a usuarios con rol de **registrador** y **administrador**.  
1.2 Esta sección debe corresponder a la **primera pestaña (tab)** del formulario de registro y gestión de acciones del PIGCCT.  
1.3 El sistema debe mostrar los campos definidos para la captura de la información básica de la acción.


### 2. Campos del formulario
2.1 El sistema debe permitir diligenciar los siguientes campos:

**Campos obligatorios:**
- **Nombre del proyecto** (texto).
- **Impacto** (selección tipo enum).
- **Fase de la acción** (selección tipo enum).
- **Enfoque diferencial** (checkbox).
- **Objetivo general** (campo tipo textarea).

**Campos opcionales:**
- **Objetivos específicos** (textarea).
- **Pertinencia** (textarea).
- **Entidad a cargo** (texto).

**Campo de control administrativo:**
- **Activo** (switch), visible y editable **solo para usuarios con rol administrador**.

2.2 Los campos tipo **select (enum)** deben cargarse desde catálogos maestros del sistema.  
2.3 El sistema debe diferenciar visualmente los campos obligatorios de los opcionales.


### 3. Validaciones en tiempo real
3.1 El sistema debe validar en tiempo real que los **campos obligatorios** se encuentren diligenciados.  
3.2 En caso de campos vacíos o con formato inválido:
- El sistema debe mostrar mensajes de error claros por campo.
- Debe resaltarse visualmente el campo con inconsistencias.

3.3 La validación debe ejecutarse tanto al momento de edición como al intentar guardar la información.


### 4. Control de avance en el formulario
4.1 El sistema **no debe permitir avanzar a la siguiente pestaña** si:
- Existen campos obligatorios sin diligenciar.
- Se presentan errores de validación en la sección “Información general”.

4.2 El sistema debe mostrar un mensaje indicando que existen **campos críticos pendientes** antes de continuar.


### 5. Comportamiento según rol del usuario
5.1 Los usuarios con rol **registrador**:
- Pueden diligenciar todos los campos, excepto el campo **Activo**.
- No pueden modificar el estado de activación de la acción.

5.2 Los usuarios con rol **administrador**:
- Pueden diligenciar todos los campos.
- Pueden activar o desactivar la acción mediante el switch **Activo**.


### 6. Guardado progresivo
6.1 El sistema debe permitir el **guardado progresivo** de la información ingresada en la pestaña “Información general”.  
6.2 Al guardar:
- La información debe persistirse sin necesidad de completar todo el formulario.
- Debe mostrarse una confirmación visual de guardado exitoso.

6.3 En caso de error durante el guardado:
- El sistema debe informar claramente la causa.
- Debe conservar la información ya diligenciada.


### 7. Indicadores de estado y retroalimentación
7.1 El sistema debe mostrar indicadores claros de:
- Campos obligatorios.
- Estado de validación.
- Errores por campo.

7.2 Los mensajes deben ser comprensibles para el usuario, por ejemplo:  
> “Debe completar todos los campos obligatorios para continuar.”


### 8. Usabilidad y experiencia de usuario
8.1 La interfaz de la pestaña debe ser coherente con los **principios de diseño del formulario**:
- Formulario guiado por pestañas.
- Campos habilitados o deshabilitados según rol, etapa del proceso y estado de validación.
- Indicadores visuales de errores y obligatoriedad.

8.2 El sistema no debe permitir la pérdida de información por errores de validación o navegación.  
8.3 El usuario debe poder editar la información previamente registrada en cualquier momento, según sus permisos.



### Resultado esperado

El usuario puede **registrar correctamente la información general de una acción del PIGCCT**, asegurando que todos los campos críticos estén completos, con validaciones en tiempo real, control de avance por pestañas y persistencia segura de los datos como base para la estructuración y gestión del proyecto territorial.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-163.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-163.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-163.png)
