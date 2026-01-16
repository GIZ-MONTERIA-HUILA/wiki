# HU-PIGCCT-SYM-235
# Épica: Detalle funcional del visor geográfico del PIGCCT
# Selección de PIGCCT activo

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                         
> **Quiero:** seleccionar el PIGCCT activo directamente desde el visor geográfico.                   
> **Para:** actualizar automáticamente las capas, estadísticas y filtros disponibles, garantizando que la información visualizada corresponda al plan territorial seleccionado.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la funcionalidad de selección

1.1 El sistema debe permitir la selección del PIGCCT activo.                    
1.2 La opción de selección debe estar disponible dentro del visor geográfico del PIGCCT, mediante un componente visible y accesible tipo panel lateral.                             
1.3 El sistema debe cargar automáticamente el listado de PIGCCT disponibles desde la tabla maestra del sistema.

### 2. Listado de PIGCCT disponibles

2.1 El selector debe mostrar únicamente los PIGCCT en estado Activo.                         
2.2 Cada elemento del listado debe incluir como mínimo:

- Departamento.
- Año de formulación.
- Denominación oficial del PIGCCT.
2.3 El listado debe presentarse de forma ordenada y comprensible para el usuario.

### 3. Selección y activación del PIGCCT

3.1 Al seleccionar un PIGCCT del listado, el sistema debe establecerlo como PIGCCT activo en sesión.                      
3.2 El cambio de PIGCCT activo debe realizarse sin necesidad de recargar completamente el sistema.                        
3.3 El sistema debe confirmar visualmente al usuario el PIGCCT activo seleccionado.

### 4. Actualización automática del visor

4.1 Al cambiar el PIGCCT activo, el sistema debe actualizar automáticamente:

- La vista inicial del visor geográfico.
- Las capas territoriales asociadas.
- Las estadísticas y gráficos visibles.
- Los filtros disponibles.

4.2 La vista del mapa debe centrarse automáticamente en el departamento correspondiente al nuevo PIGCCT activo.                     
4.3 Las capas previamente cargadas deben sincronizarse con la información del PIGCCT seleccionado.

### 5. Manejo de estado y consistencia

5.1 El sistema debe garantizar que solo exista un PIGCCT activo por sesión de usuario.                    
5.2 El PIGCCT activo seleccionado debe mantenerse durante la navegación del usuario en los diferentes módulos del sistema.                       
5.3 En caso de cerrar sesión, el sistema debe restablecer el PIGCCT activo según la configuración inicial definida.

### 6. Manejo de errores y validaciones

6.1 Si el sistema no puede cargar la información del PIGCCT seleccionado, debe:

- Mantener el PIGCCT previamente activo.
- Mostrar un mensaje claro indicando el error ocurrido.

6.2 Si no existen PIGCCT activos disponibles, el sistema debe:

- Deshabilitar el selector.
- Mostrar un mensaje informativo al usuario.

### 7. Usabilidad y experiencia de usuario

7.1 El cambio de PIGCCT activo debe realizarse en un tiempo razonable, sin afectar el rendimiento del visor.                         
7.2 El selector debe ser intuitivo y accesible desde cualquier vista del visor.                         
7.3 El sistema debe evitar la pérdida de información o configuraciones temporales del usuario durante el cambio de PIGCCT.

---

## Resultado esperado

Un PIGCCT activo seleccionado desde el visor geográfico, con actualización automática y coherente de las capas, estadísticas y filtros, permitiendo una gestión territorial clara, consistente y alineada con el plan de cambio climático seleccionado.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-235.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-235.png)