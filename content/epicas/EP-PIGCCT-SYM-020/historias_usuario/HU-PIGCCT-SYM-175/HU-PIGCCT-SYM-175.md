# HU-PIGCCT-SYM-175  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Contenido mínimo del dashboard

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** visualizar en el dashboard un conjunto mínimo de información clave.  
> **Para:** conocer rápidamente el estado de las acciones, validaciones e indicadores del PIGCCT y priorizar mi gestión diaria.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Visualización del contenido mínimo
1.1 El sistema debe mostrar en el **dashboard** un conjunto mínimo de bloques de información.  
1.2 Estos bloques deben cargarse automáticamente al acceder al dashboard.  
1.3 El contenido debe presentarse de forma clara, resumida y visualmente comprensible.

### 2. Número de acciones por estado
2.1 El sistema debe mostrar el **número de acciones** clasificadas por los siguientes estados:
- **En borrador**.  
- **En validación**.  
- **Validadas**.  
- **Rechazadas**.

2.2 Los contadores deben reflejar información actualizada.  
2.3 Cada contador debe permitir el acceso al listado correspondiente, según permisos del usuario.

### 3. Alertas por acciones pendientes
3.1 El sistema debe mostrar **alertas** relacionadas con acciones pendientes, tales como:
- Acciones próximas a vencer.
- Acciones con tareas o seguimientos pendientes.

3.2 Las alertas deben ser visibles y priorizadas según su nivel de criticidad.

### 4. Indicadores con retraso
4.1 El sistema debe mostrar un bloque de **indicadores con retraso**.  
4.2 El sistema debe identificar como retrasados aquellos indicadores que no cumplen los tiempos definidos.  
4.3 El usuario debe poder acceder al detalle de los indicadores con retraso, según permisos.

### 5. Últimas validaciones realizadas
5.1 El sistema debe mostrar un resumen de las **últimas validaciones realizadas**.  
5.2 La información debe incluir, como mínimo:
- Acción validada.
- Fecha de validación.
- Estado resultante.

5.3 La visualización debe priorizar las validaciones más recientes.

### 6. Adaptación por rol
6.1 El contenido del dashboard debe adaptarse al **rol del usuario**, mostrando únicamente información relevante y autorizada.  
6.2 El sistema no debe mostrar información de acciones o indicadores a los que el usuario no tenga acceso.

### 7. Navegación desde el dashboard
7.1 Cada bloque de información debe permitir:
- Acceder al listado correspondiente.
- Navegar al detalle, según permisos.

7.2 La navegación desde el dashboard debe ser fluida y no generar pérdida de información.

### 8. Usabilidad y experiencia de usuario
8.1 El dashboard debe ser claro, ordenado y fácil de interpretar.  
8.2 La información debe presentarse de forma sintética para evitar sobrecarga visual.  
8.3 El diseño del dashboard debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El sistema muestra en el **dashboard un contenido mínimo estructurado y actualizado**, que incluye el estado de las acciones, alertas relevantes, indicadores con retraso y las últimas validaciones realizadas, permitiendo al usuario priorizar y orientar su gestión diaria de manera eficiente dentro del PIGCCT.



---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-175.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-175.png)

