# HU-PIGCCT-SYM-087
## Épica: Gestión territorial de la acción (municipios)
### Registrar la cobertura departamental

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                 
> **Quiero:** registrar cuando una acción tiene cobertura sobre todo el departamento.                      
> **Para:** diferenciar claramente una cobertura departamental total de una selección parcial de municipios dentro del PIGCCT.

## CRITERIOS DE ACEPTACIÓN

### 1. Registro de la cobertura departamental

1.1 El sistema debe permitir registrar que una acción cubra todo el departamento.                     
1.2 Este registro debe diferenciarse explícitamente de la selección de municipios específicos.

### 2. Reglas de negocio para la implementación

El sistema debe implementar una de las siguientes opciones, garantizando el mismo comportamiento funcional:

Opción A – Campo en la acción                 
2.1 La entidad acción debe contar con un campo booleano **cobertura_departamental**.                    
2.2 Cuando cobertura_departamental = true, el sistema debe interpretar que la acción cubre todo el departamento.

Opción B – Registro especial en la relación acción–municipio                        
2.3 El sistema debe registrar un **valor especial o flag** en la tabla de relación acción_municipio que indique cobertura total del departamento.             
2.4 Este registro no debe representar un municipio específico, sino la cobertura departamental completa.

### 3. Restricciones y consistencia territorial

3.1 Cuando la acción tenga cobertura departamental, el sistema no debe permitir la coexistencia de registros de municipios específicos activos.                        
3.2 Si se cambia de cobertura departamental a selección parcial, el sistema debe requerir la selección explícita de uno o más municipios.

### 4. Uso de la información y trazabilidad

4.1 La cobertura departamental debe reflejarse correctamente en los módulos de seguimiento, indicadores y reportes.                      
4.2 El sistema debe permitir identificar de forma clara el tipo de cobertura territorial de la acción en consultas y auditorías.

### 5. Mensajes y retroalimentación al usuario

5.1 El sistema debe mostrar un mensaje de confirmación cuando la cobertura departamental se registre exitosamente.                         
5.2 En caso de error, el sistema debe informar la causa y permitir la corrección sin pérdida de información.

### 6. Auditoría y trazabilidad

6.1 El sistema debe registrar automáticamente:

- Usuario que registra.
- Fecha y hora de registro.
- Estado inicial del registro.

6.2 Esta información debe estar disponible para fines de auditoría y control.

### 8. Usabilidad y experiencia de usuario

8.1 El formulario debe ser claro y consistente con el diseño general del sistema.                      
8.2 El sistema debe permitir cancelar la operación sin guardar cambios.                     
8.3 El sistema debe prevenir la pérdida de información mediante validaciones previas.

### Resultado esperado

El sistema registra de manera explícita y consistente cuando una acción cubre todo el departamento, diferenciándola de una cobertura parcial por municipios y garantizando trazabilidad territorial, integridad del modelo de datos y claridad funcional en todos los módulos del PIGCCT.

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-087.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-087.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-082-092.png)

