# HU-PIGCCT-SYM-088
## Épica: Gestión territorial de la acción (municipios)
### Validar la coherencia territorial con el PIGCCT

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                        
> **Quiero:** validar que los municipios asociados a una acción pertenezcan al departamento del PIGCCT.                             
> **Para:** garantizar la coherencia territorial del plan y la integridad de la información registrada.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Validación territorial con el PIGCCT

1.1 El sistema debe validar que todos los municipios asociados a una acción pertenezcan al departamento definido en el PIGCCT.                        
1.2 Esta validación debe aplicarse tanto al momento de crear como de editar una acción.

### 2. Cobertura departamental

2.1 Cuando la acción tenga registrada cobertura sobre todo el departamento, el sistema debe validar que dicha cobertura corresponda al departamento del PIGCCT activo.                  
2.2 No debe permitirse registrar cobertura departamental para un departamento distinto al del PIGCCT.

### 3. Restricciones ante inconsistencias

3.1 El sistema debe impedir guardar o actualizar la acción si se detectan municipios que no pertenecen al departamento del PIGCCT.                            
3.2 El sistema debe mostrar un mensaje claro de validación cuando se presente una inconsistencia territorial.

### 4. Consistencia en todos los módulos

4.1 Las validaciones de coherencia territorial deben mantenerse en los módulos de acciones, seguimientos, indicadores y reportes.   

---                             

### Resultado esperado

El sistema valida de forma estricta que los municipios y la cobertura departamental asociados a cada acción correspondan al departamento definido en el PIGCCT, garantizando coherencia territorial, integridad referencial y confiabilidad de la información del plan en todos los módulos del sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-088.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-088.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-082-092.png)
