# HU-PIGCCT-SYM-030  
## Épica: Administración de medidas del PIGCCT  
### Registrar población beneficiada estimada

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** registrar la población beneficiada estimada asociada a una medida del PIGCCT.  
> **Para:** analizar el alcance social de la medida y su contribución al bienestar de la población.



## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y acceso
1.1 Solo los usuarios con rol **administrador** pueden registrar, editar o inactivar la información de población beneficiada.  
1.2 Los usuarios de consulta pueden visualizar la información registrada.



### 2. Asociación con la medida
2.1 El sistema debe permitir registrar la población beneficiada únicamente para **medidas válidas** del PIGCCT.  
2.2 Cada registro de población beneficiada debe estar asociado a una única medida.



### 3. Información de población beneficiada
El sistema debe permitir registrar, como mínimo, la siguiente información:

- **Número estimado de personas beneficiadas** (obligatorio).  
- **Tipo de beneficiarios** (ej. población total, mujeres, comunidades rurales, comunidades étnicas, población urbana, etc.).  
- **Periodo de estimación** (ej. anual, horizonte del plan, acumulado) (obligatorio).

Campos adicionales (opcional según diseño):
- Metodología de estimación.
- Fuente de información.
- Observaciones.



### 4. Validaciones
4.1 El sistema debe validar que:
- El número de personas beneficiadas sea un valor entero mayor o igual a cero.  
- El tipo de beneficiarios corresponda a un catálogo definido.  
- El periodo de estimación esté definido.

4.2 El sistema debe evitar registros duplicados para la misma medida, tipo de beneficiario y periodo, si la regla de negocio así lo establece.



### 5. Desagregación de la población (opcional)
5.1 El sistema puede permitir desagregar la población beneficiada por:
- Sexo.
- Grupo etario.
- Enfoque diferencial (género, étnico, rural/urbano).

5.2 La suma de las desagregaciones debe ser consistente con el total registrado (si aplica).



### 6. Edición y gestión del estado
6.1 El usuario administrador debe poder editar la información registrada.  
6.2 El sistema debe permitir **activar o inactivar** el registro sin eliminarlo, para conservar trazabilidad histórica.  
6.3 Los registros inactivos no deben mostrarse por defecto en vistas operativas.



### 7. Visualización y análisis
7.1 El sistema debe mostrar la población beneficiada estimada en:
- La ficha de detalle de la medida.
- Reportes de impacto social.

7.2 La información debe poder consolidarse para análisis por:
- Medida.
- Eje.
- PIGCCT.



### 8. Persistencia y trazabilidad
8.1 El sistema debe almacenar el histórico de los valores registrados.  
8.2 Si existe auditoría, se debe registrar:
- Usuario que realiza el registro o modificación.
- Fecha y hora del cambio.



### 9. Uso en módulos posteriores
9.1 La información de población beneficiada debe ser utilizada en:
- Módulos de seguimiento y evaluación.
- Reportes de impacto social.
- Indicadores agregados del PIGCCT.



### Resultado esperado

El sistema permite **medir y analizar el alcance social de cada medida del PIGCCT**, facilitando la evaluación de su impacto en la población beneficiaria y apoyando la toma de decisiones con enfoque social.


   
## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-030.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-030.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-024-41.png)

