# HU-PIGCCT-SYM-023  
## Épica: Administración de ejes del PIGCCT  
### Uso del eje en módulos posteriores

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (consulta o administrador, según el módulo).  
> **Quiero:** seleccionar un eje del PIGCCT desde otros módulos del sistema.  
> **Para:** alinear la planificación operativa, el seguimiento y el reporte de acciones, indicadores y proyectos con la estructura estratégica del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Disponibilidad del eje en otros módulos
1.1 El sistema debe permitir la selección de ejes del PIGCCT en los módulos que lo requieran, tales como:
- Acciones de adaptación.
- Acciones de mitigación.
- Programas o proyectos.
- Indicadores y reportes.
- Visor geográfico (si aplica).

1.2 La selección del eje debe realizarse mediante un campo controlado (lista desplegable, buscador o selector jerárquico).



### 2. Restricción por estado del eje
2.1 El sistema debe permitir seleccionar **únicamente ejes activos** en procesos operativos.  
2.2 Los ejes inactivos:
- No deben aparecer como opción seleccionable.
- Sí pueden visualizarse en consultas históricas o reportes.



### 3. Contexto del PIGCCT
3.1 El sistema debe mostrar únicamente los ejes asociados al **PIGCCT previamente seleccionado** en el módulo correspondiente.  
3.2 No se deben permitir asociaciones cruzadas entre ejes y PIGCCT distintos.



### 4. Información visible del eje
4.1 En el selector de ejes, el sistema debe mostrar información mínima suficiente, como:
- Nombre del eje.
- Alcance (estratégico o transversal).

4.2 El sistema puede permitir visualizar información adicional al pasar el cursor o seleccionar el eje (tooltip o vista rápida).



### 5. Integridad referencial
5.1 El sistema debe garantizar la integridad referencial entre:
- El módulo operativo.
- El eje seleccionado.
- El PIGCCT asociado.

5.2 La relación debe almacenarse utilizando el identificador único del eje.



### 6. Comportamiento ante cambios de estado
6.1 Si un eje cambia a estado inactivo:
- No debe permitir nuevas asociaciones en módulos operativos.
- Las asociaciones históricas deben conservarse.

6.2 El sistema debe manejar estos casos sin generar inconsistencias.



### 7. Usabilidad y experiencia de usuario
7.1 El selector de ejes debe ser claro, ordenado y fácil de usar.  
7.2 El sistema debe permitir filtrar o buscar ejes cuando el listado sea extenso.



### 8. Mensajes y validaciones
8.1 Si el usuario intenta guardar un registro sin seleccionar un eje obligatorio, el sistema debe mostrar un mensaje claro.  
8.2 En caso de error en la asociación, el sistema debe informar la causa y orientar la corrección.

---

### Resultado esperado

El usuario puede **seleccionar ejes del PIGCCT desde otros módulos del sistema**, asegurando la alineación operativa, la coherencia estructural del plan y la integridad de la información en todo el sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA ](assets/secuencia-atributiva-HU-pigcct-sym-023.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-atributiva-HU-pigcct-sym-023.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-012-023.png)