# HU-PIGCCT-SYM-080
## Épica: Gestión de acciones territoriales y seguimiento de indicadores del PIGCCT
### Activar o inactivar acción

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.                       
> **Quiero:** activar o inactivar una acción territorial.                         
> **Para:** gestionar su vigencia sin perder la información histórica asociada.

## CRITERIOS DE ACEPTACIÓN

### 1. Activación e inactivación de la acción

1.1 El sistema debe permitir cambiar el estado de una acción territorial entre activa e inactiva.                           
1.2 Solo los usuarios con rol de administrador deben poder realizar esta acción.

### 2. Conservación de la información histórica

2.1 La inactivación de una acción no debe eliminar la información registrada.                            
2.2 Los datos históricos de la acción y sus seguimientos deben conservarse para consulta y análisis.

### 3. Consistencia del sistema

3.1 El estado de la acción debe reflejarse de forma consistente en los módulos de seguimiento y consulta.                      
3.2 El sistema debe impedir la edición de acciones inactivas, salvo reactivación por un administrador.

### 4. Auditoría y trazabilidad

4.1 El sistema debe registrar automáticamente:

- Usuario que registra.
- Fecha y hora de registro.

4.2 El sistema debe conservar la información histórica para fines de auditoría y control.

### 5. Usabilidad y experiencia de usuario

5.1 La interfaz debe ser clara y consistente con el diseño general del sistema.                      
5.2 El sistema debe permitir cancelar la operación sin guardar cambios.  

### Resultado esperado

El sistema permite a los usuarios administradores activar o inactivar acciones territoriales, garantizando la gestión de su vigencia y la conservación de la información histórica para el seguimiento de los indicadores del PIGCCT.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-080.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-080.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-062-081.png)

