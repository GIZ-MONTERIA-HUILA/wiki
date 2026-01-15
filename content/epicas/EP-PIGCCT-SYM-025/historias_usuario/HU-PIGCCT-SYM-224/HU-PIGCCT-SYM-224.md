# HU-PIGCCT-SYM-224  
## Épica: Reportes y tableros de control  
### Tablero de control general

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador, validador o consultor).  
> **Quiero:** visualizar un tablero de control general del PIGCCT.  
> **Para:** monitorear el estado de acciones, indicadores y validaciones de manera consolidada y visual.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al tablero de control general
1.1 El sistema debe permitir el acceso al tablero de control general desde el menú principal.  
1.2 La opción debe estar disponible para usuarios con roles de administrador, validador y consulta.  
1.3 El tablero debe cargarse en una vista principal con toda la información consolidada visible.

### 2. Indicadores clave del PIGCCT
2.1 El tablero debe mostrar indicadores clave (KPIs) del PIGCCT:
- Total de acciones registradas
- Total de acciones validadas
- Total de acciones en proceso de validación
- Total de acciones rechazadas
- Porcentaje de cumplimiento general
- Total de indicadores del plan

2.2 Los indicadores deben mostrarse con valores numéricos destacados y su representación visual (gráficos, barras de progreso).

### 3. Estado de las acciones
3.1 El tablero debe incluir una sección que muestre el estado de las acciones:
```
ESTADO DE ACCIONES

● Borrador: 45
● En validación entidad: 23
● Validado entidad: 67
● En validación CAR: 12
● Validado CAR: 89
● Rechazado: 8

Total: 244 acciones
```

3.2 Cada estado debe mostrarse con su código de color distintivo.

### 4. Gráficos de distribución
4.1 El tablero debe incluir gráficos visuales de distribución:
- Gráfico de pastel: Distribución de acciones por eje estratégico
- Gráfico de barras: Acciones por municipio o departamento
- Gráfico de línea temporal: Evolución de acciones registradas por mes
- Gráfico de barras horizontales: Top 10 municipios con más acciones

4.2 Los gráficos deben ser interactivos (permitir hover para ver detalles).

### 5. Estado de validaciones
5.1 El tablero debe mostrar el estado de las validaciones pendientes:
```
VALIDACIONES PENDIENTES

Nivel Entidad:
- Pendientes: 23 acciones
- Tiempo promedio de validación: 5 días

Nivel CAR:
- Pendientes: 12 acciones
- Tiempo promedio de validación: 8 días
```

5.2 Alertas visuales si hay validaciones con más de 15 días pendientes.

### 6. Indicadores por dimensión
6.1 El tablero debe mostrar el progreso de indicadores agrupados por dimensión:
- Mitigación: X indicadores (% completado)
- Adaptación: Y indicadores (% completado)
- Gestión del riesgo: Z indicadores (% completado)

6.2 Cada dimensión debe mostrar su estado de avance con barra de progreso.

### 7. Filtros del tablero
7.1 El tablero debe permitir filtrar la información por:
- Departamento
- Municipio
- Eje estratégico
- Medida
- Período de tiempo (rango de fechas)
- Estado de validación

7.2 Al aplicar filtros, todos los gráficos e indicadores deben actualizarse automáticamente.

### 8. Comparación temporal
8.1 El tablero debe permitir comparar datos entre períodos:
```
Comparación: Trimestre actual vs. Trimestre anterior

Acciones registradas:
Actual: 45 | Anterior: 38 | ↑ +18%

Acciones validadas:
Actual: 67 | Anterior: 52 | ↑ +29%
```

8.2 Indicadores de tendencia (↑ ↓ →) para cada métrica.

### 9. Acciones destacadas
9.1 El tablero debe incluir una sección de acciones destacadas o alertas:
- Acciones recientemente validadas (últimas 5)
- Acciones que requieren atención (rechazadas o con observaciones)
- Acciones próximas a vencer (si tienen fechas límite)

9.2 Enlaces directos a cada acción desde el tablero.

### 10. Exportación de vista
10.1 El tablero debe permitir exportar la vista actual como:
- Imagen PNG (captura del tablero completo)
- PDF (reporte visual del tablero)

10.2 La exportación debe respetar los filtros aplicados.

### 11. Actualización de datos
11.1 El tablero debe mostrar la fecha y hora de última actualización de los datos.  
11.2 Botón de "Actualizar" para recargar los datos en tiempo real.  
11.3 Opcionalmente, actualización automática cada X minutos.

### 12. Responsividad y visualización
12.1 El tablero debe ser responsive y adaptarse a diferentes tamaños de pantalla.  
12.2 En dispositivos móviles, los gráficos deben apilarse verticalmente para mejor visualización.  
12.3 Permitir maximizar gráficos individuales para análisis detallado.

### 13. Navegación a detalles
13.1 Al hacer clic en un gráfico o indicador, el sistema debe permitir navegar al detalle:
- Clic en "Acciones validadas" → Lista de acciones validadas
- Clic en barra de municipio → Acciones de ese municipio
- Clic en eje estratégico → Acciones de ese eje

13.2 Navegación contextual desde el tablero a los datos subyacentes.

### 14. Personalización del tablero
14.1 Permitir al usuario reordenar los widgets del tablero (drag and drop).  
14.2 Permitir ocultar/mostrar widgets según las necesidades del usuario.  
14.3 Guardar la configuración personalizada por usuario.

### 15. Alertas y notificaciones
15.1 El tablero debe mostrar alertas visuales:
- Validaciones pendientes por más de 15 días
- Acciones rechazadas sin corrección
- Indicadores sin datos actualizados

15.2 Contador de alertas activas en el tablero.

---

### Resultado esperado

Un **tablero de control general consolidado y visual** que muestre el estado de acciones, indicadores y validaciones del PIGCCT, con KPIs destacados, gráficos interactivos de distribución, estado de validaciones, filtros dinámicos, comparación temporal, alertas de atención, capacidad de exportación, actualización en tiempo real, navegación contextual a detalles, y personalización por usuario para facilitar el monitoreo y toma de decisiones.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-224.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-224.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-224.png)
