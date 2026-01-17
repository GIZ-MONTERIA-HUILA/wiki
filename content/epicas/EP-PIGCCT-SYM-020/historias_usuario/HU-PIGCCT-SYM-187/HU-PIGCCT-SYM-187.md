# HU-PIGCCT-SYM-187  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Reporte general del PIGCCT

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado con permisos de consulta o administración.  
> **Quiero:** generar un reporte general consolidado del PIGCCT por departamento.  
> **Para:** contar con una visión integral del estado del plan, facilitando la toma de decisiones y la rendición de cuentas institucional.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso al reporte general
1.1 El sistema debe permitir el acceso al **reporte general del PIGCCT** a usuarios con permisos de consulta, validación o administración.  
1.2 El acceso debe estar disponible desde el módulo de **Reportes**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos.

### 2. Selección del departamento
2.1 El sistema debe permitir seleccionar un **departamento** para la generación del reporte.  
2.2 El listado de departamentos debe cargarse desde el catálogo oficial del sistema.  
2.3 El usuario debe poder generar el reporte para un departamento específico.

### 3. Contenido del reporte
3.1 El reporte general debe consolidar información del PIGCCT del departamento seleccionado, incluyendo como mínimo:
- Número total de acciones.
- Estado de las acciones (borrador, en validación, validadas, rechazadas).
- Avance general de indicadores.
- Información territorial resumida.

3.2 La información presentada debe ser clara, estructurada y de fácil interpretación.

### 4. Consolidación de la información
4.1 El sistema debe integrar información proveniente de:
- Acciones registradas.
- Indicadores asociados.
- Estados de validación.
- Seguimientos.

4.2 El reporte debe reflejar información actualizada al momento de su generación.

### 5. Visualización del reporte
5.1 El sistema debe permitir visualizar el reporte directamente en pantalla.  
5.2 La visualización debe presentar gráficos, tablas o resúmenes que faciliten el análisis.

### 6. Control de acceso y seguridad
6.1 El sistema debe garantizar que el usuario solo pueda generar reportes para departamentos autorizados.  
6.2 El acceso a información no permitida debe estar restringido.

### 7. Usabilidad y experiencia de usuario
7.1 El reporte debe presentarse de forma clara, ordenada y comprensible.  
7.2 El sistema debe permitir identificar rápidamente el estado general del PIGCCT.  
7.3 El diseño del reporte debe ser consistente con la identidad visual del sistema.

---

## Resultado esperado

El usuario puede **generar y visualizar un reporte general consolidado del PIGCCT por departamento**, con información actualizada y estructurada que ofrece una visión integral del estado del plan, apoyando la toma de decisiones y la rendición de cuentas institucional.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-187.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-187.png)


