# HU-PIGCCT-SYM-034  
## Épica: Administración de medidas del PIGCCT  
### Registrar fuentes de financiación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** registrar las fuentes de financiación asociadas a una medida del PIGCCT.  
> **Para:** asegurar la sostenibilidad financiera, facilitar la planeación presupuestal y hacer seguimiento a los recursos destinados a la implementación de la medida.



## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y acceso
1.1 Solo los usuarios con rol **administrador** pueden registrar, editar o inactivar fuentes de financiación.  
1.2 Los usuarios de consulta pueden visualizar las fuentes de financiación asociadas a la medida.



### 2. Asociación con la medida
2.1 El sistema debe permitir registrar fuentes de financiación únicamente asociadas a **medidas válidas** del PIGCCT.  
2.2 Una medida puede tener una o varias fuentes de financiación.  
2.3 Una misma fuente de financiación puede estar asociada a múltiples medidas.



### 3. Tipos de fuentes de financiación
3.1 El sistema debe permitir clasificar la fuente de financiación según un catálogo, por ejemplo:
- Recursos públicos (nacionales, departamentales, municipales).  
- Cooperación internacional.  
- Sector privado.  
- Mecanismos financieros climáticos.  
- Otras fuentes.

3.2 El catálogo de tipos de financiación debe ser configurable por el administrador del sistema.



### 4. Información mínima requerida
Para cada fuente de financiación, el sistema debe permitir registrar como mínimo:

- **Nombre de la fuente de financiación** (obligatorio).  
- **Tipo de fuente** (obligatorio).  
- **Monto estimado o asignado** (obligatorio, si la información está disponible).  
- **Moneda** (obligatorio).  

Campos opcionales:
- Estado de la financiación (identificada, gestionada, aprobada, ejecutada).  
- Periodo de financiación.  
- Observaciones adicionales.



### 5. Validaciones
5.1 El sistema debe validar que:
- El nombre de la fuente no esté vacío.
- El tipo de fuente corresponda a valores permitidos.
- El monto sea un valor numérico válido (mayor o igual a cero).
- La medida asociada exista y esté activa.

5.2 El sistema debe evitar duplicar la misma fuente de financiación dentro de una misma medida, según reglas de negocio definidas.



### 6. Gestión del estado
6.1 El usuario administrador debe poder **editar** la información de una fuente de financiación registrada.  
6.2 El sistema debe permitir **activar o inactivar** una fuente de financiación sin eliminar el registro.  
6.3 Las fuentes inactivas no deben mostrarse por defecto en vistas operativas.



### 7. Visualización y análisis
7.1 El sistema debe mostrar las fuentes de financiación en:
- La ficha de detalle de la medida.
- Reportes financieros y de sostenibilidad del PIGCCT.

7.2 La visualización debe permitir identificar:
- Fuentes confirmadas vs. potenciales.
- Distribución de recursos por tipo de fuente.



### 8. Persistencia y trazabilidad
8.1 El sistema debe conservar el historial de fuentes de financiación asociadas a cada medida.  
8.2 Si el sistema cuenta con auditoría, se debe registrar:
- Usuario que realiza el registro o modificación.
- Fecha y hora del cambio.



### 9. Uso en módulos posteriores
9.1 Las fuentes de financiación deben poder ser utilizadas en:
- Módulos de seguimiento presupuestal.
- Reportes de ejecución financiera.
- Análisis de sostenibilidad y toma de decisiones.



### Resultado esperado

El sistema permite **registrar, gestionar y analizar las fuentes de financiación de las medidas del PIGCCT**, fortaleciendo la sostenibilidad financiera, la transparencia y el seguimiento a la inversión asociada al plan.

   
## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-034.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-034.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-024-041.png)
