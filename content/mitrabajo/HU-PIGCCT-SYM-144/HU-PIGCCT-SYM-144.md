# HU-PIGCCT-SYM-144  
## Épica: Botones del formulario y comportamiento  
### Visualizar botones globales del formulario

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** visualizar botones globales en el formulario de acciones.  
> **Para:** guardar o enviar la acción sin depender de la pestaña activa y tener acceso rápido a las acciones principales.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Ubicación de los botones globales
1.1 El sistema debe mostrar botones de acción globales en una ubicación fija y visible del formulario.  
1.2 Los botones deben estar disponibles en todas las pestañas del formulario.  
1.3 La ubicación recomendada es en la parte inferior del formulario o en una barra flotante.

### 2. Botones disponibles
2.1 El sistema debe proporcionar los siguientes botones globales:
- **Guardar borrador**: Guarda la acción sin enviarla a validación
- **Enviar a validación**: Guarda y envía la acción al flujo de validación
- **Cancelar**: Descarta cambios y sale del formulario

2.2 Todos los botones deben ser claramente identificables con texto descriptivo.

### 3. Botón "Guardar borrador"
3.1 El botón debe estar siempre visible y habilitado cuando hay cambios sin guardar.  
3.2 El botón debe tener estilo visual diferenciado (ej: color secundario).  
3.3 Al hacer clic, debe ejecutar guardado sin validaciones completas (ver HU-145).  
3.4 Debe mostrar feedback visual durante el proceso de guardado.

### 4. Botón "Enviar a validación"
4.1 El botón debe estar visible pero puede estar deshabilitado hasta que se cumplan condiciones mínimas.  
4.2 Debe tener estilo visual destacado (ej: color primario).  
4.3 Al hacer clic, debe validar todos los campos obligatorios antes de enviar.  
4.4 Si hay errores de validación, debe mostrarlos y mantener el formulario abierto.

### 5. Botón "Cancelar"
5.1 El botón debe estar siempre visible y habilitado.  
5.2 Debe tener estilo visual neutral (ej: color gris).  
5.3 Al hacer clic, debe verificar si hay cambios sin guardar.  
5.4 Si hay cambios sin guardar, debe mostrar confirmación antes de salir.

### 6. Visibilidad persistente
6.1 Los botones deben permanecer visibles al desplazarse por el formulario.  
6.2 Puede usarse una barra fija en la parte inferior o botones flotantes.  
6.3 Los botones no deben quedar ocultos por el contenido del formulario.

### 7. Comportamiento según estado de la acción
7.1 Para **acción nueva (sin guardar)**:
- "Guardar borrador": Habilitado
- "Enviar a validación": Puede estar deshabilitado hasta completar campos mínimos
- "Cancelar": Habilitado

7.2 Para **acción guardada como borrador**:
- "Guardar borrador": Habilitado
- "Enviar a validación": Habilitado si cumple validaciones
- "Cancelar": Habilitado

7.3 Para **acción enviada a validación o validada**:
- Los botones pueden cambiar o deshabilitarse según la lógica de negocio
- Puede aparecer "Solicitar edición" en lugar de "Guardar"

### 8. Indicadores de estado
8.1 El sistema debe mostrar indicadores visuales del estado actual:
- Icono de "guardando..." mientras se procesa
- Mensaje de "Guardado exitosamente" al completar
- Mensaje de error si falla el guardado

8.2 Los indicadores deben ser visibles cerca de los botones.

### 9. Confirmaciones de acciones
9.1 Al hacer clic en "Cancelar" con cambios sin guardar:
- Mostrar diálogo: "¿Deseas guardar los cambios antes de salir?"
- Opciones: "Guardar y salir", "Salir sin guardar", "Continuar editando"

9.2 Al hacer clic en "Enviar a validación":
- Si hay errores de validación, mostrarlos claramente
- Si está todo correcto, mostrar confirmación: "¿Deseas enviar esta acción a validación?"
- Informar que después de enviar, la acción no será editable hasta que sea revisada

### 10. Deshabilitación de botones durante procesamiento
10.1 Mientras se procesa una acción (guardar o enviar), los botones deben deshabilitarse temporalmente.  
10.2 Debe mostrarse un indicador de carga o progreso.  
10.3 Al completar la acción, los botones deben volver a su estado normal.

### 11. Mensajes de retroalimentación
11.1 El sistema debe proporcionar mensajes claros después de cada acción:
- "Borrador guardado exitosamente" (con timestamp)
- "Acción enviada a validación exitosamente"
- "Cambios descartados"

11.2 Los mensajes deben desaparecer automáticamente después de unos segundos.

### 12. Accesibilidad de botones
12.1 Los botones deben ser accesibles mediante teclado (navegación Tab).  
12.2 Deben tener atributos ARIA apropiados.  
12.3 El orden de foco debe ser lógico: "Guardar borrador" → "Enviar a validación" → "Cancelar".

### 13. Diseño responsivo
13.1 En pantallas pequeñas, los botones pueden reorganizarse verticalmente.  
13.2 El texto de los botones puede abreviarse si es necesario (ej: "Guardar", "Enviar", "Cancelar").  
13.3 Los botones deben mantener tamaño suficiente para ser clickeables en dispositivos táctiles.

### 14. Tooltips informativos
14.1 Los botones pueden tener tooltips que expliquen brevemente su función:
- "Guardar borrador": "Guarda tus cambios sin enviar a validación"
- "Enviar a validación": "Envía la acción para revisión por validadores"
- "Cancelar": "Descarta cambios y regresa al listado"

---

### Resultado esperado

Un **conjunto de botones globales visibles y accesibles** en todas las pestañas del formulario de acciones, que permiten al usuario guardar como borrador, enviar a validación o cancelar desde cualquier punto del formulario, con feedback visual apropiado y confirmaciones cuando sea necesario.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-144.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-144.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-144.png)
