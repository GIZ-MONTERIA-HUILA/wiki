# HU-PIGCCT-SYM-227  
## Épica: Reportes y tableros de control  
### Reportes comparativos territoriales

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario analista o tomador de decisiones.  
> **Quiero:** generar reportes comparativos entre municipios o departamentos.  
> **Para:** analizar brechas y avances del PIGCCT entre diferentes territorios.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a reportes comparativos
1.1 El sistema debe incluir una opción de "Generar reporte comparativo" en el módulo de reportes.  
1.2 La opción debe estar disponible desde los tableros de control y el visor geográfico.  
1.3 Al seleccionar, el sistema debe abrir un asistente de comparación territorial.

### 2. Selección de territorios a comparar
2.1 El asistente debe permitir seleccionar múltiples territorios:
```
REPORTE COMPARATIVO TERRITORIAL

Tipo de comparación:
○ Entre municipios
○ Entre departamentos
○ Municipios de un departamento

Selecciona territorios (mínimo 2, máximo 10):

Departamento: [Huila ▼]

Municipios:
☑ Neiva
☑ Pitalito
☑ Garzón
☐ La Plata
☐ Campoalegre

[6 municipios más...]

[Continuar] [Cancelar]
```

2.2 Validar que se seleccionen al menos 2 territorios para comparar.

### 3. Selección de métricas a comparar
3.1 El asistente debe permitir seleccionar qué métricas comparar:
```
¿Qué deseas comparar?

Acciones:
☑ Número de acciones por territorio
☑ Acciones por tipo (mitigación/adaptación)
☑ Estado de validación
☑ Porcentaje de cumplimiento

Indicadores:
☑ Reducción de emisiones proyectada
☑ Población beneficiada
☑ Inversión comprometida

Temporalidad:
☑ Evolución temporal de acciones

[Continuar]
```

3.2 Al menos una métrica debe seleccionarse para continuar.

### 4. Tabla comparativa de acciones
4.1 El reporte debe incluir una tabla comparativa:
```
| Territorio | Acciones registradas | Mitigación | Adaptación | Validadas | En proceso |
|------------|---------------------|------------|------------|-----------|------------|
| Neiva | 24 | 15 | 9 | 18 | 6 |
| Pitalito | 18 | 10 | 8 | 14 | 4 |
| Garzón | 12 | 7 | 5 | 10 | 2 |
| **TOTAL** | **54** | **32** | **22** | **42** | **12** |
```

4.2 Incluir totales y promedios cuando sea relevante.

### 5. Gráficos comparativos
5.1 El reporte debe incluir gráficos de comparación:
- Gráfico de barras agrupadas: Acciones por municipio
- Gráfico de barras apiladas: Distribución mitigación/adaptación
- Gráfico de radar: Comparación multidimensional
- Gráfico de líneas: Evolución temporal por municipio

5.2 Código de color distintivo por territorio.

### 6. Ranking territorial
6.1 El reporte debe incluir rankings de territorios:
```
TOP 5 MUNICIPIOS - Acciones Registradas

🥇 1. Neiva - 24 acciones
🥈 2. Pitalito - 18 acciones
🥉 3. Garzón - 12 acciones
   4. La Plata - 9 acciones
   5. Campoalegre - 7 acciones
```

6.2 Rankings por diferentes métricas (acciones, emisiones reducidas, inversión, etc.).

### 7. Análisis de brechas
7.1 El reporte debe identificar brechas entre territorios:
```
ANÁLISIS DE BRECHAS

Brecha en acciones de mitigación:
- Territorio con más acciones: Neiva (15)
- Territorio con menos acciones: Garzón (7)
- Brecha: 8 acciones (53% diferencia)

Recomendación: Los territorios con menor número de acciones 
requieren apoyo técnico para incrementar su participación en el PIGCCT.
```

7.2 Identificación automática de territorios rezagados.

### 8. Comparación de indicadores clave
8.1 El reporte debe comparar indicadores territoriales:
```
| Territorio | Reducción CO2 (tCO2eq) | Población beneficiada | Inversión (millones $) |
|------------|------------------------|----------------------|------------------------|
| Neiva | 45,000 | 120,000 | $8,500 |
| Pitalito | 32,000 | 85,000 | $6,200 |
| Garzón | 18,000 | 42,000 | $3,800 |
```

8.2 Permitir ordenar la tabla por cualquier columna.

### 9. Mapas comparativos
9.1 El reporte debe incluir mapas visuales de comparación:
- Mapa de calor: Densidad de acciones por territorio
- Mapa coroplético: Colorear territorios según número de acciones
- Mapas lado a lado de territorios seleccionados

9.2 Leyenda clara de la escala de colores utilizada.

### 10. Comparación por ejes estratégicos
10.1 Permitir comparar el desempeño por eje estratégico:
```
Eje: ENERGÍA

| Territorio | Acciones | % del total territorial |
|------------|----------|------------------------|
| Neiva | 8 | 33% |
| Pitalito | 5 | 28% |
| Garzón | 3 | 25% |
```

10.2 Comparación por cada eje del PIGCCT.

### 11. Exportación del reporte comparativo
11.1 El reporte comparativo debe exportarse en múltiples formatos:
- PDF: Reporte visual con gráficos y mapas
- Excel: Datos tabulares de la comparación en múltiples hojas
- CSV: Datos crudos para análisis adicional

11.2 El Excel debe incluir una hoja por cada tipo de comparación.

---

### Resultado esperado

**Reportes comparativos territoriales completos** que permitan analizar brechas y avances entre municipios o departamentos, con selección flexible de territorios y métricas, tablas comparativas detalladas, gráficos visuales de comparación, rankings territoriales, análisis de brechas, mapas comparativos, comparación por ejes estratégicos, y múltiples formatos de exportación para la toma de decisiones estratégicas.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-227.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-227.png)
