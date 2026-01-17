# HU-PIGCCT-SYM-164  
## Épica: Formulario de Registro y Gestión de Acciones del PIGCCT  
### Definir cobertura territorial

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** definir la cobertura territorial de una acción dentro del formulario del PIGCCT.  
> **Para:** especificar el alcance geográfico de la intervención y garantizar que la acción quede correctamente asociada al territorio correspondiente.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la sección “Territorio”
1.1 El sistema debe permitir el acceso a la pestaña **“Territorio”** a usuarios con rol de **registrador** y **administrador**.  
1.2 Esta sección debe corresponder a la **segunda pestaña (tab)** del formulario de registro y gestión de acciones del PIGCCT.  
1.3 El sistema debe mostrar los campos definidos para la captura de la cobertura territorial de la acción.


### 2. Campos del formulario
2.1 El sistema debe permitir diligenciar los siguientes campos:

- **Departamento** (selección tipo select, **precargado automáticamente desde el PIGCCT** asociado a la acción).  
- **Cobertura** (selección tipo radio):
  - **Todo el departamento**.  
  - **Municipios específicos**.  
- **Municipios** (selección múltiple / multi-select).

2.2 El campo **Departamento** debe mostrarse como solo lectura cuando esté precargado desde el PIGCCT.  
2.3 El sistema debe diferenciar visualmente los campos obligatorios de los opcionales, según la configuración del formulario.


### 3. Comportamiento según tipo de cobertura
3.1 Cuando el usuario seleccione la opción **“Todo el departamento”**:
- El campo **Municipios** debe deshabilitarse automáticamente.
- No debe permitirse seleccionar municipios individuales.
- La acción debe quedar asociada al 100 % del departamento seleccionado.

3.2 Cuando el usuario seleccione la opción **“Municipios específicos”**:
- El campo **Municipios** debe habilitarse.
- El usuario debe poder seleccionar uno o varios municipios para definir la cobertura territorial.


### 4. Filtrado y consistencia territorial
4.1 El listado de **Municipios** debe filtrarse automáticamente según el **Departamento** seleccionado o precargado.  
4.2 El sistema no debe permitir seleccionar municipios que no pertenezcan al departamento asociado al PIGCCT.  
4.3 Cualquier cambio en el departamento (si está habilitado por rol o etapa del proceso) debe actualizar dinámicamente el listado de municipios disponibles.


### 5. Validaciones
5.1 El sistema debe validar que:
- Se haya seleccionado una opción de **Cobertura**.
- Si la opción es **“Municipios específicos”**, al menos un municipio haya sido seleccionado.

5.2 En caso de incumplimiento:
- El sistema no debe permitir guardar ni avanzar a la siguiente pestaña.
- Debe mostrar mensajes de error claros indicando los campos pendientes o inválidos.


### 6. Guardado progresivo
6.1 El sistema debe permitir el **guardado progresivo** de la información territorial ingresada.  
6.2 Al guardar:
- La información de cobertura territorial debe persistirse sin requerir la finalización de todo el formulario.
- Debe mostrarse una confirmación visual de guardado exitoso.

6.3 En caso de error durante el guardado:
- El sistema debe informar claramente la causa.
- Debe conservar la información ya diligenciada por el usuario.


### 7. Indicadores de estado y retroalimentación
7.1 El sistema debe mostrar indicadores claros de:
- Campos obligatorios.
- Estado de validación.
- Errores asociados a la selección de cobertura o municipios.

7.2 Los mensajes deben ser comprensibles para el usuario, por ejemplo:  
> “Debe seleccionar al menos un municipio cuando la cobertura sea por municipios específicos.”


### 8. Usabilidad y experiencia de usuario
8.1 La interfaz de la pestaña **Territorio** debe ser coherente con los principios de diseño del formulario:
- Formulario guiado por pestañas.
- Habilitación o deshabilitación dinámica de campos según selección del usuario.
- Validaciones en tiempo real.

8.2 El sistema debe evitar la pérdida de información por errores de validación o navegación.  
8.3 El usuario debe poder modificar la cobertura territorial en cualquier momento, de acuerdo con sus permisos y la etapa del proceso.



### Resultado esperado

El usuario puede **definir correctamente la cobertura territorial de la acción del PIGCCT**, ya sea para todo el departamento o para municipios específicos, con validaciones automáticas, filtrado territorial coherente y persistencia segura de la información como base para la planificación, seguimiento y evaluación de la intervención.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-164.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-164.png)


