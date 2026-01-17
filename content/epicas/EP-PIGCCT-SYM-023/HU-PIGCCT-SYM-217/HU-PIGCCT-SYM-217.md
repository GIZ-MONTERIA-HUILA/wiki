# HU-PIGCCT-SYM-217
## Épica: Estadísticas territoriales del PIGCCT
### Indicadores de avance territorial
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  
> **Quiero:** visualizar indicadores agregados de avance (proyectado vs ejecutado) por municipio y departamento.  
> **Para:** evaluar el cumplimiento de los planes del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Agregación de indicadores de avance
1.1 El sistema consolida los valores proyectados y ejecutados de los indicadores por municipio.

1.2 El sistema consolida los valores proyectados y ejecutados de los indicadores por departamento.

1.3 Los cálculos consideran todas las acciones asociadas a cada territorio.

1.4 La agregación respeta la unidad de medida definida para cada indicador.

### 2. Cálculo del cumplimiento
2.1 El sistema calcula el porcentaje de avance comparando valores proyectados versus ejecutados.

2.2 Los cálculos se realizan automáticamente y se actualizan ante cambios en los datos.

2.3 El sistema maneja adecuadamente valores parciales, nulos o pendientes.

2.4 Los resultados reflejan el estado real de cumplimiento del plan.

### 3. Visualización de indicadores
3.1 Los indicadores agregados se presentan mediante gráficos, tablas o indicadores KPI.

3.2 La visualización permite diferenciar claramente entre valores proyectados y ejecutados.

3.3 El sistema utiliza codificación visual (colores, barras, porcentajes) para facilitar la interpretación.

3.4 El usuario puede alternar entre vista municipal y departamental.

### 4. Comparación territorial
4.1 El sistema permite comparar el avance entre municipios dentro de un mismo departamento.

4.2 El sistema permite comparar el avance entre departamentos a nivel regional.

4.3 Las comparaciones se presentan de forma clara y ordenada.

4.4 El usuario puede identificar territorios con alto, medio o bajo nivel de cumplimiento.

### 5. Integración con el visor geográfico
5.1 Los indicadores agregados se integran con el visor geográfico del sistema.

5.2 El mapa refleja el nivel de cumplimiento mediante simbología temática.

5.3 Al seleccionar un municipio o departamento en el mapa, se muestran sus indicadores de avance.

5.4 Existe coherencia entre la información gráfica, estadística y espacial.

### 6. Filtros y segmentación
6.1 El usuario puede filtrar los indicadores por eje, medida o tipo de acción.

6.2 El sistema permite visualizar los indicadores por periodo de tiempo, cuando aplique.

6.3 Los filtros se aplican tanto a la vista estadística como al mapa.

6.4 La información se actualiza dinámicamente al cambiar los filtros.

### 7. Control de acceso y roles

7.1 El sistema muestra los indicadores según los permisos del usuario.

7.2 Los usuarios solo visualizan información autorizada según su rol.

7.3 Los datos sensibles se protegen conforme a las políticas del sistema.

### 8. Actualización y rendimiento
8.1 Los indicadores se calculan con datos actualizados y validados.

8.2 El sistema presenta los resultados en tiempos adecuados.

8.3 La agregación de datos no afecta el rendimiento general del sistema.

---

## Resultado esperado

El usuario puede visualizar indicadores agregados de avance (proyectado vs ejecutado) por municipio y departamento, presentados de forma clara, consistente y georreferenciada, permitiendo evaluar el nivel de cumplimiento de los planes del PIGCCT y apoyar la toma de decisiones estratégicas y territoriales.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-217.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-217.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-217.png)
