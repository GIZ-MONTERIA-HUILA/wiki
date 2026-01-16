# HU-PIGCCT-SYM-143  
## Épica: Estructura y navegación del formulario de acciones  
### Habilitar pestañas de relaciones después de guardar

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** que las pestañas de indicadores asociados y adjuntos se habiliten solo después de guardar la acción.  
> **Para:** garantizar que exista un identificador de acción válido antes de crear relaciones con otras tablas.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación del contexto de edición
1.1 El sistema debe identificar cuando el usuario está **editando una acción existente** (acción con identificador asignado).  
1.2 En este contexto, el sistema debe habilitar todas las pestañas del formulario.  
1.3 El formulario debe indicar claramente el nombre/código de la acción que se está editando.

### 2. Pestañas que se habilitan después de guardar
2.1 Una vez que la acción ha sido guardada por primera vez y tiene un identificador válido, el sistema debe habilitar automáticamente las siguientes pestañas:
- **Indicadores asociados**: Para crear y gestionar indicadores de la acción
- **Adjuntos**: Para subir documentos y archivos soporte
- **Estado y validación**: Para consultar el estado del flujo de validación

2.2 Estas pestañas requieren el identificador de la acción para establecer relaciones en la base de datos.

### 3. Habilitación automática
3.1 Al completar el guardado exitoso de una acción nueva, el sistema debe:
- Habilitar las pestañas restantes automáticamente
- Actualizar la apariencia visual de las pestañas (de deshabilitadas a habilitadas)
- Mostrar un indicador o mensaje informando que ahora puede acceder a estas secciones

3.2 La habilitación debe ocurrir sin necesidad de recargar la página.

### 4. Razón de la restricción inicial
4.1 Las pestañas de relaciones requieren que la acción tenga un identificador porque:
- **Indicadores asociados**: La tabla `indicador_accion` requiere `accion_id` como clave foránea
- **Adjuntos**: La tabla `adjuntos` requiere `accion_id` para asociar archivos
- **Estado y validación**: Los eventos requieren referencia a la acción (`tabla_id` + `accion_id`)

4.2 Intentar crear estas relaciones sin un identificador de acción resultaría en errores de integridad referencial.

### 5. Validación de existencia de acción
5.1 Al acceder al formulario de edición de una acción existente, el sistema debe verificar que la acción exista en la base de datos.  
5.2 Si la acción existe, todas las pestañas deben estar habilitadas desde el inicio.  
5.3 Si la acción no existe, debe redirigir al formulario de creación con pestañas limitadas.

### 6. Navegación a pestañas recién habilitadas
6.1 Después de guardar y habilitar las nuevas pestañas, el sistema puede opcionalmente:
- Mostrar un mensaje guiando al usuario: "Ahora puedes agregar indicadores y documentos"
- Resaltar brevemente las pestañas recién habilitadas
- Ofrecer un botón para ir directamente a "Indicadores asociados"

6.2 Esto mejora la experiencia del usuario al hacerle saber qué puede hacer a continuación.

### 7. Pestaña de Indicadores asociados
7.1 Al acceder a la pestaña "Indicadores asociados" después de guardar, el sistema debe:
- Mostrar una lista vacía inicialmente (si es una acción nueva)
- Proporcionar opción para "Agregar indicador"
- Permitir asociar indicadores existentes o crear nuevos
- Cada indicador debe quedar asociado al `accion_id` de la acción actual

### 8. Pestaña de Adjuntos
8.1 Al acceder a la pestaña "Adjuntos" después de guardar, el sistema debe:
- Mostrar interfaz de carga de archivos
- Permitir subir documentos PDF, imágenes, Excel, etc.
- Almacenar cada archivo con referencia al `accion_id`
- Mostrar lista de archivos adjuntos previamente cargados

### 9. Pestaña de Estado y validación
9.1 Al acceder a la pestaña "Estado y validación" después de guardar, el sistema debe:
- Mostrar el estado actual de la acción
- Mostrar eventos de validación asociados (si existen)
- Permitir enviar la acción a validación si aplica
- Mostrar observaciones de validadores (si existen)

### 10. Persistencia de datos al cambiar pestañas
10.1 Al navegar entre las pestañas recién habilitadas, la información ingresada en cada una debe mantenerse.  
10.2 Los cambios en indicadores o adjuntos deben guardarse de forma individual al crearlos o modificarlos.  
10.3 No es necesario "guardar toda la acción" nuevamente para conservar los cambios en relaciones.

### 11. Indicadores visuales en pestañas habilitadas
11.1 Las pestañas habilitadas deben mostrar indicadores que informen:
- Cuántos indicadores están asociados (ej: "Indicadores (3)")
- Cuántos adjuntos se han cargado (ej: "Adjuntos (5)")
- El estado actual de validación (ej: "Estado: Pendiente")

11.2 Estos indicadores ayudan al usuario a conocer el estado de cada sección sin tener que ingresar.

### 12. Permisos para edición
12.1 El sistema debe validar que el usuario tenga permisos para editar la acción y sus relaciones.  
12.2 Si la acción está en proceso de validación o validada, puede aplicar restricciones:
- Bloquear edición de información básica
- Permitir solo consulta de indicadores y adjuntos
- Generar eventos si se intenta modificar (ver HU-118)

### 13. Sincronización con backend
13.1 Al habilitar las pestañas de relaciones, el sistema debe cargar desde el backend:
- Lista de indicadores asociados existentes (si los hay)
- Lista de adjuntos cargados previamente (si los hay)
- Eventos de validación relacionados (si los hay)

13.2 Esta información debe cargarse de forma eficiente al acceder a cada pestaña.

---

### Resultado esperado

Un **formulario de acciones con pestañas progresivamente habilitadas** donde las secciones de indicadores asociados, adjuntos y estado/validación se activan automáticamente después de guardar la acción, garantizando la integridad referencial de la base de datos y proporcionando una experiencia de usuario clara y guiada.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-143.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-143.png)
