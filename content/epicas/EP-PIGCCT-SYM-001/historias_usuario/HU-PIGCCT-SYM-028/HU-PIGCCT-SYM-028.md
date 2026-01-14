# HU-PIGCCT-SYM-028  
## Épica: Administración de medidas del PIGCCT  
### Registrar potencial de reducción de GEI

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** registrar el potencial de reducción de gases de efecto invernadero (GEI) asociado a una medida del PIGCCT.  
> **Para:** evaluar y analizar el impacto climático de la medida en términos de mitigación del cambio climático.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y acceso
1.1 Solo los usuarios con rol **administrador** pueden registrar, editar o inactivar información relacionada con el potencial de reducción de GEI.  
1.2 Los usuarios de consulta pueden visualizar la información registrada.



### 2. Asociación con la medida
2.1 El sistema debe permitir registrar el potencial de reducción de GEI únicamente para **medidas válidas y activas** del PIGCCT.  
2.2 Cada registro de potencial de reducción de GEI debe estar asociado a una única medida.



### 3. Información del potencial de reducción de GEI
El sistema debe permitir registrar, como mínimo, la siguiente información:

- **Valor estimado de reducción de GEI** (obligatorio).  
- **Unidad de medida** (por ejemplo: tCO₂e/año, tCO₂e acumuladas) (obligatorio).  
- **Periodo de estimación** (por ejemplo: anual, periodo del plan, horizonte específico) (obligatorio).  

Campos adicionales (opcional según diseño):
- Metodología utilizada para la estimación.
- Fuente de información.
- Supuestos o notas técnicas.



### 4. Validaciones
4.1 El sistema debe validar que:
- El valor de reducción de GEI sea numérico y mayor o igual a cero.  
- La unidad de medida corresponda a un catálogo definido.  
- La medida asociada exista y esté activa.

4.2 El sistema debe evitar registrar múltiples valores de potencial de reducción de GEI para la misma medida y el mismo periodo, si así lo define la regla de negocio.



### 5. Edición y gestión del estado
5.1 El usuario administrador debe poder **editar** el potencial de reducción de GEI registrado.  
5.2 El sistema debe permitir **activar o inactivar** el registro sin eliminarlo, para conservar trazabilidad histórica.  
5.3 Los registros inactivos no deben mostrarse por defecto en vistas operativas.



### 6. Visualización y análisis
6.1 El sistema debe mostrar el potencial de reducción de GEI asociado a la medida en:
- La ficha de detalle de la medida.
- Reportes de impacto climático.

6.2 La información debe poder agregarse o consolidarse para análisis por:
- Eje.
- PIGCCT.
- Horizonte temporal (si aplica).



### 7. Persistencia y trazabilidad
7.1 El sistema debe almacenar el histórico de los valores registrados.  
7.2 Si existe auditoría, se debe registrar:
- Usuario que realiza el registro o modificación.
- Fecha y hora del cambio.



### 8. Uso en módulos posteriores
8.1 El potencial de reducción de GEI debe ser utilizado en:
- Módulos de seguimiento y evaluación.
- Reportes de mitigación del cambio climático.
- Indicadores agregados del PIGCCT.

---

### Resultado esperado

El sistema permite **cuantificar y analizar el impacto climático de cada medida del PIGCCT**, facilitando la evaluación de la contribución del plan a la reducción de emisiones de GEI y al cumplimiento de compromisos climáticos.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-028.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-028.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-024-041.png)
