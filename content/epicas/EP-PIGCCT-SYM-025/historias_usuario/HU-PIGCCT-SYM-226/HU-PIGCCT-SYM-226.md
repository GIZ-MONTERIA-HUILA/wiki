# HU-PIGCCT-SYM-226  
## Épica: Reportes y tableros de control  
### Reportes desde el visor geográfico

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema trabajando en el visor geográfico.  
> **Quiero:** generar reportes territoriales directamente desde el visor.  
> **Para:** documentar resultados por municipio o departamento con contexto espacial.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Opción de generar reporte desde el visor
1.1 El visor geográfico debe incluir un botón de "Generar reporte territorial".  
1.2 El botón debe estar visible en la barra de herramientas del visor.  
1.3 Al hacer clic, el sistema debe abrir un asistente de generación de reporte.

### 2. Selección de área territorial
2.1 El asistente debe permitir seleccionar el área para el reporte:
```
GENERAR REPORTE TERRITORIAL

Selecciona el área:
○ Municipio específico: [Selector]
○ Departamento completo: [Selector]
○ Área dibujada en el mapa
○ Área visible actualmente en el visor

[Continuar] [Cancelar]
```

2.2 Si el usuario selecciona "Área dibujada", el visor debe permitir dibujar un polígono de selección.

### 3. Configuración del reporte territorial
3.1 El asistente debe permitir configurar el contenido:
```
CONFIGURAR REPORTE TERRITORIAL

Título: [Reporte Municipal - Neiva]

Incluir:
☑ Mapa del territorio
☑ Acciones en el territorio (tabla)
☑ Indicadores territoriales
☑ Gráficos estadísticos
☑ Capas activas del visor

Capas a incluir en el mapa:
☑ Acciones de mitigación
☑ Acciones de adaptación
☐ Límites administrativos
☐ Áreas protegidas

Formato: ○ PDF  ○ Excel

[Generar reporte]
```

3.2 El reporte debe respetar las capas y filtros activos en el visor.

### 4. Mapa territorial en el reporte
4.1 El reporte PDF debe incluir uno o más mapas del territorio:
- Mapa general del municipio/departamento
- Mapas temáticos por tipo de acción
- Leyenda de simbología
- Escala y coordenadas

4.2 Los mapas deben exportarse en alta resolución para impresión.

### 5. Datos territoriales
5.1 El reporte debe incluir información territorial consolidada:
```
MUNICIPIO: NEIVA
Departamento: Huila
Área: 1,533 km²
Población: 357,392 habitantes

ACCIONES REGISTRADAS: 24

Por tipo:
- Mitigación: 15 acciones
- Adaptación: 9 acciones

Por estado:
- Validadas: 18
- En validación: 4
- Borrador: 2
```

5.2 Datos contextuales del territorio.

### 6. Lista de acciones territoriales
6.1 El reporte debe incluir tabla con todas las acciones del territorio:
```
| ID | Nombre de la acción | Tipo | Estado | Responsable |
|----|---------------------|------|--------|-------------|
| ACC-001 | Reforestación urbana | Mitigación | Validado | Alcaldía |
| ACC-002 | Sistema de alerta temprana | Adaptación | Validado | CAM |
...
```

6.2 Tabla exportable a Excel con todos los campos relevantes.

### 7. Indicadores por territorio
7.1 El reporte debe incluir indicadores específicos del territorio:
- Reducción de emisiones proyectada (tCO2eq)
- Población beneficiada
- Área de influencia (hectáreas)
- Inversión total en el territorio

7.2 Comparación con otros territorios similares si está disponible.

### 8. Gráficos territoriales
8.1 El reporte debe incluir gráficos específicos del territorio:
- Distribución de acciones por eje estratégico
- Línea de tiempo de acciones registradas
- Comparación con meta territorial
- Progreso en indicadores clave

8.2 Gráficos visuales y contextualizados al territorio seleccionado.

### 9. Capas del visor en el reporte
9.1 El reporte debe documentar qué capas estaban activas:
```
Capas incluidas en el mapa:
✓ Acciones de mitigación (17 elementos)
✓ Acciones de adaptación (12 elementos)
✓ Límites municipales
✓ Red hídrica

Fecha de generación: 15/01/2026
Vista centrada en: Neiva, Huila
```

9.2 Información de contexto sobre la configuración del visor.

### 10. Coordenadas y ubicación
10.1 Para cada acción territorial, incluir sus coordenadas:
```
Acción: Reforestación urbana Río del Oro
Ubicación: 2°55'34"N 75°17'21"W
Vereda: El Caguán
Municipio: Neiva
```

10.2 Coordenadas en formato decimal y geográfico.

### 11. Exportación del mapa como imagen
11.1 Permitir exportar solo el mapa visible como imagen independiente:
- PNG de alta resolución
- JPEG para uso en presentaciones
- Incluir leyenda y escala

11.2 Botón "Exportar mapa" adicional al de generar reporte completo.

### 12. Reporte multi-territorial
12.1 Permitir seleccionar múltiples municipios para un reporte comparativo:
```
Generar reporte comparativo

Municipios seleccionados:
☑ Neiva
☑ Pitalito
☑ Garzón

[Generar reporte comparativo]
```

12.2 El reporte debe incluir mapas y datos de cada territorio lado a lado.

### 13. Filtros territoriales aplicados
13.1 El reporte debe documentar los filtros aplicados en el visor:
```
Filtros aplicados:
- Tipo de acción: Mitigación
- Estado: Validado
- Período: 2024-2026
- Eje: Energía

Resultados: 12 acciones encontradas
```

13.2 Transparencia sobre qué datos se incluyen en el reporte.

### 14. Metadatos del reporte territorial
14.1 El reporte debe incluir metadatos específicos:
- Sistema de coordenadas utilizado (ej: WGS84)
- Fuente de datos geográficos
- Fecha de actualización de datos
- Usuario que generó el reporte
- Filtros y capas activas al momento de generación

14.2 Para reproducibilidad y trazabilidad del reporte.

### 15. Impresión optimizada de mapas
15.1 El PDF del reporte debe estar optimizado para impresión:
- Tamaño carta u oficio
- Mapas en páginas completas cuando sea necesario
- Márgenes apropiados
- Calidad de impresión profesional

15.2 Listo para presentar o distribuir impreso.

---

### Resultado esperado

**Capacidad de generar reportes territoriales** directamente desde el visor geográfico, con selección flexible de áreas (municipio, departamento, área dibujada o visible), mapas de alta resolución, datos territoriales consolidados, lista detallada de acciones con coordenadas, indicadores territoriales, gráficos específicos, documentación de capas activas, exportación de mapas como imagen, reportes multi-territoriales comparativos, transparencia de filtros aplicados, metadatos completos, y formato optimizado para impresión profesional.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-226.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-226.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-226.png)
