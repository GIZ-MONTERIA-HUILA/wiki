# HU-PIGCCT-SYM-188  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Reportes territoriales

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado con permisos de consulta o administración.  
> **Quiero:** generar reportes territoriales del PIGCCT por municipio o cobertura territorial.  
> **Para:** analizar el comportamiento y avance de las acciones e indicadores a nivel territorial y apoyar la toma de decisiones locales.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a los reportes territoriales
1.1 El sistema debe permitir el acceso a los **reportes territoriales** a usuarios con permisos de consulta, validación o administración.  
1.2 El acceso debe estar disponible desde el módulo de **Reportes**.  
1.3 El sistema no debe permitir el acceso a usuarios no autorizados.

### 2. Selección del nivel territorial
2.1 El sistema debe permitir seleccionar el nivel territorial del reporte:
- **Municipio específico**.
- **Cobertura territorial** (todo el departamento o conjunto de municipios).

2.2 El listado de territorios debe cargarse desde los catálogos territoriales oficiales del sistema.

### 3. Contenido del reporte territorial
3.1 El reporte territorial debe incluir como mínimo:
- Acciones asociadas al territorio seleccionado.
- Estados de las acciones.
- Indicadores relacionados.
- Avances y alertas territoriales.

3.2 La información debe presentarse de forma consolidada y estructurada.

### 4. Consolidación y actualización de la información
4.1 El sistema debe integrar información proveniente de:
- Acciones.
- Indicadores.
- Seguimientos.
- Estados de validación.

4.2 El reporte debe reflejar información actualizada al momento de su generación.

### 5. Visualización del reporte
5.1 El sistema debe permitir visualizar el reporte territorial en pantalla.  
5.2 La visualización debe incluir tablas, resúmenes o gráficos que faciliten el análisis territorial.

### 6. Control de acceso y seguridad
6.1 El sistema debe garantizar que el usuario solo pueda generar reportes para territorios autorizados.  
6.2 El acceso a información territorial restringida debe estar bloqueado.

### 7. Usabilidad y experiencia de usuario
7.1 El reporte territorial debe ser claro, ordenado y fácil de interpretar.  
7.2 El sistema debe permitir identificar rápidamente brechas y avances territoriales.  
7.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El usuario puede **generar y visualizar reportes territoriales del PIGCCT**, ya sea por municipio o por cobertura territorial, con información consolidada y actualizada que facilita el análisis espacial, la toma de decisiones y la rendición de cuentas a nivel local.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-188.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-188.png)


