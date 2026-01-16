# HU-PIGCCT-SYM-033  
## Épica: Administración de medidas del PIGCCT  
### Registrar barreras de implementación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** documentar las barreras para la implementación de una medida del PIGCCT.  
> **Para:** anticipar riesgos, identificar limitaciones y apoyar la definición de estrategias de mitigación que aseguren el cumplimiento de las metas del plan.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y acceso
1.1 Solo los usuarios con rol **administrador** pueden registrar, editar o inactivar barreras de implementación.  
1.2 Los usuarios de consulta pueden visualizar las barreras asociadas a una medida.



### 2. Asociación con la medida
2.1 El sistema debe permitir registrar barreras únicamente asociadas a **medidas válidas** del PIGCCT.  
2.2 Una medida puede tener una o varias barreras de implementación registradas.  



### 3. Clasificación de las barreras
3.1 El sistema debe permitir clasificar cada barrera según un catálogo predefinido, por ejemplo:  
- Institucional  
- Financiera  
- Técnica  
- Social / comunitaria  
- Normativa / legal  
- Ambiental / territorial  

3.2 El catálogo de tipos de barrera debe ser configurable por el administrador del sistema.



### 4. Información mínima requerida
Para cada barrera de implementación, el sistema debe permitir registrar como mínimo:

- **Tipo de barrera** (obligatorio).  
- **Descripción de la barrera** (obligatorio).  
- **Nivel de impacto** (alto, medio, bajo) (obligatorio).  

Campos opcionales:
- Probabilidad de ocurrencia.  
- Observaciones adicionales.  
- Referencia a actores relacionados con la barrera.



### 5. Validaciones
5.1 El sistema debe validar que:
- La descripción de la barrera no esté vacía.
- El tipo y nivel de impacto correspondan a valores permitidos.
- La medida asociada exista y esté activa.

5.2 El sistema debe evitar duplicar barreras idénticas dentro de una misma medida, según reglas de negocio definidas.



### 6. Gestión del estado
6.1 El usuario administrador debe poder **editar** la información de una barrera registrada.  
6.2 El sistema debe permitir **activar o inactivar** una barrera sin eliminar el registro, para conservar trazabilidad histórica.  
6.3 Las barreras inactivas no deben mostrarse por defecto en vistas operativas.



### 7. Visualización y análisis
7.1 El sistema debe mostrar las barreras de implementación en:
- La ficha de detalle de la medida.
- Reportes de riesgos y seguimiento del PIGCCT.

7.2 La visualización debe permitir identificar rápidamente:
- Barreras de alto impacto.
- Tipos de barreras más frecuentes por eje o medida.



### 8. Persistencia y trazabilidad
8.1 El sistema debe conservar el historial de barreras asociadas a cada medida.  
8.2 Si el sistema cuenta con auditoría, se debe registrar:
- Usuario que realiza el registro o modificación.
- Fecha y hora del cambio.



### 9. Uso en módulos posteriores
9.1 Las barreras registradas deben poder ser utilizadas en:
- Módulos de seguimiento y evaluación.
- Reportes de gestión del riesgo.
- Análisis para la formulación de estrategias de mitigación y ajustes al plan.

---

### Resultado esperado

El sistema permite **identificar, documentar y analizar las barreras de implementación de las medidas del PIGCCT**, facilitando la gestión de riesgos, la toma de decisiones y la mejora continua en la ejecución del plan.

---
   
## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-033.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-033.png)
