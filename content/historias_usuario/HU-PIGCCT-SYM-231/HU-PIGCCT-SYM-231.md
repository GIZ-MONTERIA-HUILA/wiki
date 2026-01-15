# HU-PIGCCT-SYM-231  
## Épica: Usuario de consulta pública (sin autenticación)  
### Estadísticas públicas territoriales

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** ciudadano interesado en el PIGCCT de mi territorio.  
> **Quiero:** visualizar estadísticas generales por municipio y departamento.  
> **Para:** conocer el avance del plan de cambio climático en mi región.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Página de estadísticas públicas
1.1 El sistema debe incluir una página accesible sin autenticación: "Estadísticas públicas".  
1.2 La página debe estar visible desde el menú principal público.  
1.3 Al acceder, mostrar estadísticas agregadas del PIGCCT.

### 2. Estadísticas generales del departamento
2.1 Mostrar estadísticas consolidadas del departamento:
```
HUILA - ESTADÍSTICAS GENERALES

Total acciones validadas: 89
Municipios participantes: 12 de 37
Última actualización: 15/01/2026

Por tipo:
- Mitigación: 45 acciones (51%)
- Adaptación: 44 acciones (49%)

Por eje estratégico:
- Energía: 25 acciones
- Bosques: 22 acciones
- Transporte: 18 acciones
- Agua: 15 acciones
- Otros: 9 acciones
```

2.2 Datos agregados sin información sensible.

### 3. Selección de municipio
3.1 Permitir seleccionar un municipio específico:
```
CONSULTAR ESTADÍSTICAS POR MUNICIPIO

Departamento: Huila

Municipio: [Selector ▼]
- Neiva
- Pitalito
- Garzón
- La Plata
- ...

[Ver estadísticas]
```

3.2 Mostrar estadísticas específicas del municipio seleccionado.

### 4. Estadísticas por municipio
4.1 Al seleccionar un municipio, mostrar sus datos:
```
NEIVA - ESTADÍSTICAS MUNICIPALES

Acciones validadas: 24
Posición departamental: 1° de 12 municipios

Distribución:
- Mitigación: 15 acciones (63%)
- Adaptación: 9 acciones (37%)

Ejes más desarrollados:
1. Energía: 8 acciones
2. Transporte: 6 acciones
3. Bosques: 5 acciones

Impacto proyectado:
- Reducción CO2: 45,000 tCO2eq
- Población beneficiada: 120,000 habitantes
```

4.2 Comparación con el resto del departamento.

### 5. Gráficos visuales públicos
5.1 Incluir gráficos para mejor comprensión:
```
[Gráfico de pastel]
Distribución de acciones por eje estratégico

[Gráfico de barras]
Top 10 municipios con más acciones

[Gráfico de líneas]
Evolución de acciones validadas por año
```

5.2 Gráficos interactivos y descargables como imagen.

### 6. Comparación entre municipios
6.1 Permitir comparar dos o más municipios:
```
COMPARAR MUNICIPIOS

Municipios seleccionados:
☑ Neiva
☑ Pitalito
☑ Garzón

[Generar comparación]

RESULTADO:
| Municipio | Acciones | Mitigación | Adaptación |
|-----------|----------|------------|------------|
| Neiva | 24 | 15 | 9 |
| Pitalito | 18 | 10 | 8 |
| Garzón | 12 | 7 | 5 |
```

6.2 Tabla y gráficos comparativos entre territorios.

### 7. Ranking municipal
7.1 Mostrar ranking de municipios por número de acciones:
```
RANKING MUNICIPAL - HUILA

🥇 1. Neiva - 24 acciones validadas
🥈 2. Pitalito - 18 acciones validadas
🥉 3. Garzón - 12 acciones validadas
   4. La Plata - 9 acciones validadas
   5. Campoalegre - 7 acciones validadas
   ...

Mostrando municipios con acciones validadas (12/37)
```

7.2 Rankings por diferentes métricas si están disponibles.

### 8. Mapa de calor territorial
8.1 Incluir mapa visual del avance territorial:
```
MAPA DE AVANCE TERRITORIAL

[Mapa coroplético del departamento]

Municipios coloreados según número de acciones:
- Verde oscuro: >20 acciones
- Verde medio: 10-20 acciones
- Verde claro: 5-10 acciones
- Amarillo: 1-5 acciones
- Gris: Sin acciones validadas

[Ver en visor geográfico]
```

8.2 Visualización rápida del avance territorial.

### 9. Evolución temporal pública
9.1 Mostrar evolución de acciones validadas en el tiempo:
```
EVOLUCIÓN TEMPORAL

Acciones validadas por año:

2024: ████████░░ 45 acciones
2025: ████████████████░░ 44 acciones
2026: ██░░ (en curso)

Total acumulado: 89 acciones validadas
```

9.2 Gráfico de tendencia temporal del PIGCCT.

### 10. Exportación de estadísticas públicas
10.1 Permitir descargar las estadísticas públicas:
```
📥 DESCARGAR ESTADÍSTICAS

Formato:
○ PDF (reporte visual)
○ CSV (datos tabulares)

Contenido:
☑ Estadísticas departamentales
☑ Estadísticas por municipio
☑ Gráficos

[Descargar]
```

10.2 Reportes públicos descargables sin autenticación.

---

### Resultado esperado

**Visualización de estadísticas públicas territoriales** con estadísticas consolidadas del departamento, selección de municipio específico, distribución por tipo y eje estratégico, impacto proyectado agregado, gráficos visuales interactivos, comparación entre municipios, ranking municipal, mapa de calor territorial, evolución temporal de acciones validadas, y capacidad de exportar estadísticas públicas para facilitar el conocimiento ciudadano del avance del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-231.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-231.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-231.png)
