# HU-PIGCCT-SYM-165  
## Épica: Formulario de Registro y Gestión de Acciones del PIGCCT  
### Asociar la acción con indicadores

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** asociar una acción con indicadores del PIGCCT.  
> **Para:** definir a qué metas, ejes y medidas del plan aporta la acción, asegurando coherencia con la estructura estratégica del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la sección “Indicadores asociados”
1.1 El sistema debe permitir el acceso a la pestaña **“Indicadores asociados”** a usuarios con rol de **registrador** y **administrador**.  
1.2 Esta sección debe corresponder a la **quinta pestaña (tab)** del formulario de registro y gestión de acciones del PIGCCT.  
1.3 El sistema debe mostrar la interfaz para la asociación de la acción con ejes, medidas e indicadores.


### 2. Flujo guiado de asociación
2.1 El sistema debe implementar un **flujo secuencial y dependiente** para la selección de elementos:
1. **Selección de Eje** (select).  
2. **Selección de Medida** (select dependiente del eje seleccionado).  
3. **Selección de Indicadores** (multi-select dependiente de la medida seleccionada).

2.2 El sistema debe guiar visualmente al usuario a través de cada paso del flujo.


### 3. Selección de Eje
3.1 El campo **Eje** debe mostrar únicamente los ejes asociados al **PIGCCT** de la acción.  
3.2 El sistema no debe permitir avanzar al siguiente paso sin haber seleccionado un eje válido.  
3.3 Al cambiar el eje seleccionado:
- Debe limpiarse automáticamente la selección previa de medida e indicadores.
- Deben actualizarse dinámicamente las opciones disponibles.


### 4. Selección de Medida (dependiente)
4.1 El campo **Medida** debe mostrar únicamente las medidas asociadas al **eje seleccionado**.  
4.2 El sistema debe impedir la selección de medidas que no pertenezcan al eje activo.  
4.3 Al cambiar la medida:
- Debe limpiarse la selección previa de indicadores.
- Debe actualizarse dinámicamente el listado de indicadores disponibles.


### 5. Selección de Indicadores (multi-select)
5.1 El campo **Indicadores** debe permitir la selección de uno o varios indicadores asociados a la **medida seleccionada**.  
5.2 El sistema no debe permitir seleccionar indicadores que no correspondan a la medida activa.  
5.3 El sistema debe mostrar claramente los indicadores seleccionados.


### 6. Validaciones
6.1 El sistema debe validar que:
- Se haya seleccionado un **eje**.
- Se haya seleccionado una **medida**.
- Se haya seleccionado **al menos un indicador**.

6.2 En caso de incumplimiento:
- El sistema no debe permitir guardar ni avanzar a la siguiente pestaña.
- Debe mostrar mensajes de error claros indicando los campos pendientes o inválidos.


### 7. Persistencia de la asociación
7.1 Al guardar la información:
- El sistema debe registrar la relación entre la **acción**, el **eje**, la **medida** y los **indicadores seleccionados**.  
7.2 La asociación debe quedar disponible para:
- Seguimiento y monitoreo.
- Evaluación de aportes a metas del PIGCCT.
- Reportes e indicadores de avance.


### 8. Guardado progresivo
8.1 El sistema debe permitir el **guardado progresivo** de la información de asociación.  
8.2 Al guardar:
- La información debe persistirse sin requerir la finalización de todo el formulario.
- Debe mostrarse una confirmación visual de guardado exitoso.

8.3 En caso de error durante el guardado:
- El sistema debe informar claramente la causa.
- Debe conservar la información ya diligenciada.


### 9. Indicadores de estado y retroalimentación
9.1 El sistema debe mostrar indicadores claros de:
- Campos obligatorios.
- Estado de validación.
- Errores en la asociación.

9.2 Los mensajes deben ser comprensibles para el usuario, por ejemplo:  
> “Debe seleccionar al menos un indicador para asociar la acción.”


### 10. Usabilidad y experiencia de usuario
10.1 La interfaz de la pestaña **Indicadores asociados** debe ser coherente con los principios de diseño del formulario:
- Flujo guiado por pasos.
- Habilitación y deshabilitación dinámica de campos.
- Validaciones en tiempo real.

10.2 El sistema debe evitar la pérdida de información por errores de validación o navegación.  
10.3 El usuario debe poder modificar las asociaciones en cualquier momento, de acuerdo con sus permisos y la etapa del proceso.

---

### Resultado esperado

El usuario puede **asociar correctamente una acción del PIGCCT con uno o varios indicadores**, siguiendo un flujo guiado por eje, medida e indicadores, garantizando coherencia con la estructura del plan y permitiendo el seguimiento y evaluación del aporte de la acción a las metas territoriales.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-165.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-165.png)

