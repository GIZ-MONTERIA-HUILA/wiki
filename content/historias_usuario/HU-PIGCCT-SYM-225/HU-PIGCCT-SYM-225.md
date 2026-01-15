# HU-PIGCCT-SYM-225  
## Épica: Reportes y tableros de control  
### Reportes desde tableros

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema con permisos de consulta o administración.  
> **Quiero:** generar reportes descargables (PDF, Excel) desde los tableros de control.  
> **Para:** apoyar la toma de decisiones y rendición de cuentas con información consolidada y exportable.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Opción de generar reporte desde el tablero
1.1 El tablero de control debe incluir un botón o menú de "Generar reporte".  
1.2 Al hacer clic, el sistema debe mostrar opciones de formato:
- PDF (documento formateado)
- Excel (.xlsx - datos tabulares)
- CSV (datos sin formato)

1.3 La opción debe estar visible solo para usuarios con permisos de generar reportes.

### 2. Configuración del reporte
2.1 Antes de generar el reporte, el sistema debe permitir configurar:
```
CONFIGURAR REPORTE

Título del reporte: [Texto editable]

Incluir en el reporte:
☑ Indicadores clave (KPIs)
☑ Gráficos
☑ Tablas de datos
☑ Alertas y observaciones
☐ Lista detallada de acciones

Período: [Selector de fechas]

Filtros aplicados:
- Departamento: Huila
- Estado: Todos
[Editar filtros]

[Generar PDF] [Generar Excel] [Cancelar]
```

2.2 Los filtros aplicados en el tablero deben respetarse en el reporte generado.

### 3. Formato PDF del reporte
3.1 El reporte PDF debe incluir:
- Encabezado con logo institucional y fecha de generación
- Título del reporte
- Resumen ejecutivo con KPIs principales
- Gráficos visuales del tablero
- Tablas con datos consolidados
- Pie de página con número de página y usuario generador

3.2 El PDF debe tener formato profesional y estar listo para presentaciones.

### 4. Formato Excel del reporte
4.1 El reporte Excel debe incluir múltiples hojas:
```
Hoja 1: Resumen
- Indicadores clave en tabla

Hoja 2: Acciones por estado
- Listado completo de acciones con sus campos principales

Hoja 3: Indicadores
- Detalle de indicadores y su cumplimiento

Hoja 4: Validaciones
- Estado de validaciones pendientes

Hoja 5: Datos para gráficos
- Datos fuente de los gráficos mostrados
```

4.2 El Excel debe tener formato de tabla y permitir filtros y ordenamiento.

### 5. Personalización del reporte
5.1 Permitir al usuario seleccionar qué secciones incluir en el reporte:
- Solo indicadores clave
- Solo gráficos específicos
- Datos detallados de acciones
- Comparación temporal

5.2 Vista previa antes de generar el reporte final.

### 6. Metadatos del reporte
6.1 Cada reporte generado debe incluir metadatos:
- Fecha y hora de generación
- Usuario que generó el reporte
- Filtros aplicados
- Período de datos incluidos
- Versión del sistema

6.2 Esta información debe aparecer al inicio o pie del reporte.

### 7. Validación de datos antes de generar
7.1 Antes de generar el reporte, validar:
- Que existan datos para el período seleccionado
- Que los filtros aplicados devuelvan resultados
- Que el usuario tenga permisos sobre los datos solicitados

7.2 Si no hay datos, mostrar mensaje apropiado en lugar de reporte vacío.

### 8. Marcas de agua y seguridad
8.1 Los reportes PDF deben incluir marca de agua si contienen información sensible:
```
[MARCA DE AGUA DIAGONAL]
"USO OFICIAL - PIGCCT"
```

8.2 Opcionalmente, protección con contraseña para PDFs sensibles.

### 9. Gráficos en alta resolución
9.1 Los gráficos incluidos en reportes PDF deben exportarse en alta resolución.  
9.2 Los colores y estilo visual deben mantenerse consistentes con el tablero.  
9.3 Gráficos deben incluir leyendas y etiquetas claras.

### 10. Logs de generación de reportes
10.1 El sistema debe registrar en logs cada reporte generado:
- Usuario que generó
- Fecha y hora
- Tipo de reporte
- Filtros aplicados
- Éxito o error en la generación

10.2 Para auditoría y control de acceso a la información.

---

### Resultado esperado

**Capacidad de generar reportes descargables** en formatos PDF, Excel y CSV desde los tableros de control, con configuración personalizable, respeto a filtros aplicados, formato profesional, validación de datos, seguridad con marcas de agua, gráficos en alta resolución, y logs de auditoría para apoyar la toma de decisiones y rendición de cuentas.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-225.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-225.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-225.png)
