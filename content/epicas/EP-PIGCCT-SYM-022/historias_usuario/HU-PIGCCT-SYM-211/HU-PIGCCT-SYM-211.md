# HU-PIGCCT-SYM-211
## Épica: Visor geográfico del PIGCCT 
### Filtrar acciones por eje, medida o indicador
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** filtrar las acciones visibles en el mapa por eje, medida e indicador.  
> **Para:** realizar análisis temáticos del PIGCCT de manera focalizada y comparativa.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Disponibilidad de filtros temáticos
1.1 El sistema dispone de filtros independientes para Eje, Medida e Indicador, accesibles desde el visor geográfico.

1.2 Cada filtro muestra únicamente valores válidos y vigentes del PIGCCT.

1.3 Los filtros se presentan de forma clara y ordenada dentro de la interfaz del visor.

### 2. Funcionamiento de los filtros
2.1 El usuario puede seleccionar uno o varios valores en cada filtro (eje, medida e indicador).

2.2 El visor actualiza automáticamente la visualización del mapa conforme a las selecciones realizadas.

2.3 Solo se muestran en el mapa las acciones que cumplen simultáneamente con los criterios seleccionados.

### 3. Combinación entre filtros
3.1 Los filtros de eje, medida e indicador pueden combinarse entre sí y con otros filtros territoriales.

3.2 Al seleccionar un eje, el sistema limita las opciones disponibles de medidas e indicadores a las que correspondan a dicho eje.

3.3 Al seleccionar una medida, el sistema limita las opciones de indicadores asociadas a dicha medida.

### 4. Comportamiento del mapa
4.1 El mapa ajusta su visualización para mostrar únicamente las acciones filtradas.

4.2 Las acciones no relacionadas con los filtros activos no se visualizan o se muestran atenuadas.

4.3 La simbología del mapa se mantiene consistente y legible tras la aplicación de los filtros.

### 5. Interacción y experiencia de usuario
5.1 Los filtros permiten modificar o retirar selecciones sin necesidad de recargar el visor.

5.2 El sistema ofrece una opción para limpiar los filtros temáticos y restaurar la vista general.

5.3 El estado de los filtros activos es visible y comprensible para el usuario.

### 6. Rendimiento y consistencia
6.1 La aplicación de filtros se realiza con un tiempo de respuesta adecuado, incluso con múltiples criterios activos.

6.2 El comportamiento de los filtros es consistente entre sesiones y navegadores.

6.3 No se generan inconsistencias entre los resultados mostrados en el mapa y la información asociada (paneles o tablas).

---

## Resultado esperado

El usuario puede realizar análisis temáticos precisos del PIGCCT, filtrando las acciones por eje, medida e indicador, lo que facilita la identificación de patrones, el seguimiento estratégico y la toma de decisiones informadas.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-211.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-211.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-211.png)
