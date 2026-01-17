# HU-PIGCCT-SYM-189  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Reportes por componente

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado con permisos de consulta o administración.  
> **Quiero:** generar reportes del PIGCCT por componente estratégico.  
> **Para:** analizar el desempeño y avance de los ejes, medidas e indicadores del plan, facilitando el seguimiento y la toma de decisiones.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a los reportes por componente
1.1 El sistema debe permitir el acceso a los **reportes por componente** a usuarios con permisos de consulta, validación o administración.  
1.2 El acceso debe estar disponible desde el módulo de **Reportes**.  
1.3 El sistema no debe permitir el acceso a usuarios no autorizados.

### 2. Selección del tipo de componente
2.1 El sistema debe permitir seleccionar el tipo de componente a reportar:
- **Eje**.
- **Medida**.
- **Indicador**.

2.2 La selección debe condicionar la información que será mostrada en el reporte.

### 3. Selección del componente específico
3.1 Según el tipo seleccionado, el sistema debe permitir elegir:
- Un eje específico.
- Una medida específica.
- Un indicador específico.

3.2 Los listados deben cargarse desde los catálogos oficiales del PIGCCT.

### 4. Contenido del reporte
4.1 El reporte por componente debe incluir como mínimo:
- Acciones asociadas al componente seleccionado.
- Estados de las acciones.
- Avances y resultados de indicadores.
- Información territorial relacionada.

4.2 La información debe presentarse de forma consolidada y estructurada.

### 5. Consolidación y actualización de la información
5.1 El sistema debe integrar información proveniente de:
- Acciones.
- Indicadores.
- Seguimientos.
- Estados de validación.

5.2 El reporte debe reflejar información actualizada al momento de su generación.

### 6. Visualización del reporte
6.1 El sistema debe permitir visualizar el reporte por componente en pantalla.  
6.2 La visualización debe incluir tablas, resúmenes o gráficos que faciliten el análisis.

### 7. Control de acceso y seguridad
7.1 El sistema debe garantizar que el usuario solo pueda generar reportes de componentes autorizados.  
7.2 El acceso a información restringida debe estar bloqueado.

### 8. Usabilidad y experiencia de usuario
8.1 El reporte por componente debe ser claro, ordenado y fácil de interpretar.  
8.2 El sistema debe permitir identificar avances, brechas y prioridades.  
8.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario puede **generar y visualizar reportes del PIGCCT por eje, medida o indicador**, con información consolidada y actualizada que facilita el seguimiento estratégico, el análisis del desempeño y la toma de decisiones institucionales.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-189.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-189.png)


