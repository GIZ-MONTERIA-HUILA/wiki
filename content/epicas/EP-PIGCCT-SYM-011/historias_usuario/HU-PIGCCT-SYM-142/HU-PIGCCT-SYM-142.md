# HU-PIGCCT-SYM-142  
## Épica: Estructura y navegación del formulario de acciones  
### Visualizar pestañas iniciales al crear una acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** visualizar inicialmente solo las pestañas de información básica al crear una acción.  
> **Para:** completar primero los datos esenciales de la acción antes de asociar relaciones y documentos.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación del contexto de creación
1.1 El sistema debe identificar cuando el usuario está **creando una nueva acción** (acción sin identificador asignado aún).  
1.2 En este contexto, el sistema debe aplicar reglas especiales de visibilidad de pestañas.  
1.3 El formulario debe indicar claramente que se está en modo "Crear nueva acción".

### 2. Pestañas visibles inicialmente
2.1 Al crear una nueva acción, el sistema debe mostrar únicamente las siguientes pestañas habilitadas:
- **Información general**: Datos básicos de la acción
- **Territorio**: Información geográfica y de cobertura
- **Articulación con el plan**: Relación con ejes y medidas del PIGCCT
- **Programación y seguimiento**: Cronograma y presupuesto

2.2 Estas pestañas contienen información que no requiere que la acción tenga un identificador previo.

### 3. Pestañas no visibles inicialmente
3.1 Al crear una nueva acción, el sistema debe **deshabilitar y ocultar** las siguientes pestañas:
- **Indicadores asociados**: Requiere que la acción exista en BD
- **Adjuntos**: Requiere que la acción exista para asociar archivos
- **Estado y validación**: Solo aplica a acciones ya guardadas

3.2 Estas pestañas deben mostrarse visualmente como no disponibles (atenuadas o con icono de candado).

### 4. Justificación de restricción
4.1 El sistema debe explicar al usuario por qué ciertas pestañas no están disponibles.  
4.2 Al pasar el cursor sobre una pestaña deshabilitada, debe mostrarse un tooltip con mensaje:
```
"Esta sección estará disponible después de guardar la acción por primera vez."
```

4.3 Opcionalmente, puede mostrarse un mensaje informativo en la parte superior del formulario.

### 5. Validación de campos obligatorios
5.1 Antes de permitir guardar la acción por primera vez, el sistema debe validar que los campos obligatorios de las pestañas habilitadas estén completos:
- Información general: Nombre de la acción, tipo, responsable
- Territorio: Departamento, municipio
- Articulación: Eje estratégico, medida
- Programación: Fecha de inicio

5.2 Si faltan campos obligatorios, el sistema debe indicar en cuál pestaña se encuentran.

### 6. Orden de llenado sugerido
6.1 El sistema puede sugerir al usuario un orden lógico de llenado mediante indicadores visuales (numeración en pestañas: 1, 2, 3, 4).  
6.2 Esta sugerencia no debe ser obligatoria; el usuario puede navegar libremente entre las pestañas habilitadas.

### 7. Navegación permitida
7.1 El usuario debe poder navegar libremente entre las cuatro pestañas iniciales habilitadas.  
7.2 Al cambiar de pestaña, la información ingresada debe conservarse sin necesidad de guardar.  
7.3 El sistema debe indicar cuál pestaña está actualmente activa.

### 8. Guardado inicial de la acción
8.1 El sistema debe proporcionar un botón **"Guardar acción"** visible desde cualquiera de las pestañas habilitadas.  
8.2 Al guardar por primera vez:
- Se validan los campos obligatorios de todas las pestañas habilitadas
- Se asigna un identificador único a la acción
- Se almacena la información en la base de datos
- Se genera un evento de tipo "create" (ver HU-117)

8.3 Después del guardado exitoso, las pestañas restantes deben habilitarse automáticamente (ver HU-143).

### 9. Mensajes de confirmación
9.1 Al guardar exitosamente la acción por primera vez, el sistema debe:
- Mostrar un mensaje de confirmación: "Acción creada exitosamente"
- Informar que ahora puede acceder a las secciones de indicadores y adjuntos
- Actualizar visualmente las pestañas habilitándolas

### 10. Cancelación de la creación
10.1 El sistema debe permitir cancelar la creación de la acción en cualquier momento.  
10.2 Al cancelar, debe confirmar con el usuario si desea descartar los cambios no guardados.  
10.3 Si confirma, debe regresar a la vista anterior sin crear la acción.

### 11. Prevención de pérdida de datos
11.1 Si el usuario intenta salir del formulario sin guardar, el sistema debe advertir sobre la pérdida de información no guardada.  
11.2 Debe ofrecer opciones: "Guardar y salir", "Salir sin guardar", "Cancelar".

### 12. Almacenamiento temporal
12.1 Opcionalmente, el sistema puede guardar un borrador temporal de la acción en el navegador (localStorage).  
12.2 Si el usuario regresa al formulario, puede ofrecer restaurar el borrador.  
12.3 Los borradores deben eliminarse después de guardar exitosamente o después de un período determinado.

---

### Resultado esperado

Un **formulario de creación de acción con pestañas limitadas inicialmente** que muestra solo las secciones de información básica (información general, territorio, articulación con el plan, programación y seguimiento), guiando al usuario a completar primero los datos esenciales antes de habilitar las secciones de relaciones y documentos.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-142.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-142.png)
