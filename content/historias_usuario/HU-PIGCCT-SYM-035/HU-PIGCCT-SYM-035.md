# HU-PIGCCT-SYM-035  
## Épica: Administración de medidas del PIGCCT  
### Consultar medidas por eje

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  
> **Quiero:** consultar las medidas asociadas a un eje del PIGCCT.  
> **Para:** comprender la estructura jerárquica del plan y analizar cómo se organizan las líneas estratégicas, líneas de acción y medidas dentro de cada eje.



## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y acceso
1.1 Los usuarios con permisos de **consulta o superiores** deben poder acceder a la visualización de medidas por eje.  
1.2 El acceso debe respetar los roles y perfiles definidos en el sistema.



### 2. Selección del eje
2.1 El sistema debe permitir al usuario seleccionar un **PIGCCT** y posteriormente un **eje válido** asociado.  
2.2 El eje seleccionado debe existir y estar asociado correctamente al PIGCCT.



### 3. Visualización de medidas
3.1 El sistema debe mostrar el listado de medidas asociadas al eje seleccionado.  
3.2 Cada medida debe visualizar, como mínimo:
- Nombre de la medida.  
- Tipo o alcance (línea estratégica, línea de acción o medida).  
- Estado (activa / inactiva).  

3.3 El sistema debe presentar las medidas respetando la **estructura jerárquica** definida (línea estratégica → línea de acción → medida).



### 4. Filtros y ordenamiento
4.1 El sistema debe permitir filtrar las medidas por:
- Tipo o alcance.  
- Estado (activa / inactiva).  

4.2 El sistema debe permitir ordenar las medidas por:
- Nombre.  
- Tipo.  
- Estado.



### 5. Visualización de detalle
5.1 El usuario debe poder seleccionar una medida para visualizar su **detalle**, incluyendo información estratégica, acciones por horizonte temporal y datos asociados (si aplica).  
5.2 La navegación al detalle no debe alterar el contexto del eje seleccionado.



### 6. Integridad y consistencia
6.1 El sistema debe garantizar que solo se muestren medidas válidas y correctamente asociadas al eje.  
6.2 Si un eje no tiene medidas asociadas, el sistema debe notificarlo de forma clara al usuario.



### 7. Uso en otros módulos
7.1 La consulta de medidas por eje debe estar disponible como referencia en:
- Módulos de seguimiento y evaluación.  
- Reportes del PIGCCT.  
- Módulos de planeación operativa.



### Resultado esperado

El sistema permite **visualizar y analizar las medidas asociadas a cada eje del PIGCCT**, facilitando la comprensión de la estructura jerárquica del plan y apoyando los procesos de seguimiento, evaluación y toma de decisiones.



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-035.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-035.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-024-041.png)

