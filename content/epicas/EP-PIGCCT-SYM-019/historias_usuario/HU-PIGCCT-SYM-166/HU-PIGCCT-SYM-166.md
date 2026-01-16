# HU-PIGCCT-SYM-166  
## Épica: Formulario de Registro y Gestión de Acciones del PIGCCT  
### Definir programación de la acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** definir la programación de una acción mediante fechas, vigencia y forma de evaluación.  
> **Para:** establecer el periodo de ejecución, calcular automáticamente los seguimientos y asegurar una planificación coherente para el monitoreo de la acción.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la sección “Programación y seguimiento”
1.1 El sistema debe permitir el acceso a la pestaña **“Programación y seguimiento”** a usuarios con rol de **registrador** y **administrador**.  
1.2 Esta sección debe corresponder a la **cuarta pestaña (tab)** del formulario de registro y gestión de acciones del PIGCCT.  
1.3 El sistema debe mostrar los campos definidos para la programación de la acción.


### 2. Campos del formulario
2.1 El sistema debe permitir diligenciar los siguientes campos:

- **Fecha inicial** (selector de fecha / date picker).  
- **Fecha final** (selector de fecha / date picker).  
- **Vigencia** (número entero: cantidad de años para la implementación completa de la acción).  
- **Forma de evaluación** (selección tipo enum).  
- **Valor invertido (COP)** (numérico).  
- **Fuente de los recursos** (texto).  
- **Insumo** (texto).  
- **Producto** (texto).

2.2 Los campos tipo **select (enum)** deben cargarse desde catálogos maestros del sistema.  
2.3 El sistema debe diferenciar visualmente los campos obligatorios de los opcionales, según la configuración del formulario.


### 3. Validaciones de fechas
3.1 El sistema debe validar que la **fecha final sea posterior a la fecha inicial**.  
3.2 Si la fecha final es menor o igual a la fecha inicial:
- El sistema no debe permitir guardar ni avanzar a la siguiente pestaña.
- Debe mostrarse un mensaje de error claro indicando la inconsistencia.


### 4. Generación automática de seguimientos
4.1 El sistema debe generar automáticamente los **registros de seguimiento** en función de:
- La **vigencia**.
- La **forma de evaluación** definida para la acción.

4.2 El sistema debe mostrar un **tooltip o ayuda contextual** que explique al usuario que:
> “La vigencia y la forma de evaluación determinan la generación automática de los seguimientos de la acción.”


### 5. Comportamiento ante cambios en vigencia y forma de evaluación
5.1 Cuando el usuario modifique los valores de **vigencia** o **forma de evaluación**:
- El sistema debe recalcular automáticamente los seguimientos asociados.

5.2 El sistema **solo debe permitir el recálculo** de los seguimientos si:
- **No existen valores ejecutados** o registrados en los seguimientos actuales.

5.3 Si existen valores ejecutados:
- El sistema debe bloquear el recálculo.
- Debe mostrar un mensaje indicando que no es posible modificar la vigencia o forma de evaluación debido a la existencia de información ya registrada.


### 6. Validaciones de consistencia
6.1 El sistema debe validar que:
- La vigencia sea un **número entero positivo**.
- Los campos numéricos acepten únicamente valores válidos.
- Los campos de texto no excedan los límites definidos por el sistema.

6.2 En caso de error:
- El sistema no debe permitir guardar ni avanzar.
- Debe mostrar mensajes claros orientando la corrección de los datos.


### 7. Guardado progresivo
7.1 El sistema debe permitir el **guardado progresivo** de la información de programación.  
7.2 Al guardar:
- La información debe persistirse sin requerir la finalización de todo el formulario.
- Debe mostrarse una confirmación visual de guardado exitoso.

7.3 En caso de error durante el guardado:
- El sistema debe informar claramente la causa.
- Debe conservar la información ya diligenciada por el usuario.


### 8. Indicadores de estado y retroalimentación
8.1 El sistema debe mostrar indicadores claros de:
- Campos obligatorios.
- Estado de validación.
- Errores asociados a fechas, vigencia o forma de evaluación.

8.2 Los mensajes deben ser comprensibles para el usuario, por ejemplo:  
> “La fecha final debe ser posterior a la fecha inicial.”


### 9. Usabilidad y experiencia de usuario
9.1 La interfaz de la pestaña **Programación y seguimiento** debe ser coherente con los principios de diseño del formulario:
- Validaciones en tiempo real.
- Ayudas contextuales (tooltips).
- Campos habilitados o deshabilitados según el estado de la información.

9.2 El sistema debe evitar la pérdida de información por errores de validación o navegación.  
9.3 El usuario debe poder editar la programación de la acción en cualquier momento, de acuerdo con sus permisos y la etapa del proceso.

---

### Resultado esperado

El usuario puede **definir correctamente la programación de la acción del PIGCCT**, estableciendo fechas, vigencia y forma de evaluación, con validaciones automáticas y generación controlada de seguimientos, garantizando una planificación adecuada para el monitoreo y evaluación de la intervención.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-166.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-166.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-166.png)
