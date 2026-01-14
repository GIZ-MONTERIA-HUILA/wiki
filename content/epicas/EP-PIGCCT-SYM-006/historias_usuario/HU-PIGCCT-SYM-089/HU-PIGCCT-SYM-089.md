# HU-PIGCCT-SYM-089
## Épica: Gestión territorial de la acción (municipios)
### Prevenir la duplicidad en la relación acción–municipio

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                       
> **Quiero:** evitar la duplicidad de la relación entre una acción y un municipio.                       
> **Para:** mantener la consistencia, integridad y confiabilidad de la información territorial del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Prevención de duplicidades

1.1 El sistema debe impedir registrar más de una vez la misma relación acción–municipio.                 
1.2 La validación debe aplicarse tanto al crear como al editar una acción.

### 2. Reglas de unicidad

2.1 El sistema debe garantizar la unicidad de la relación acción–municipio a nivel de base de datos.                    
2.2 No debe permitirse la coexistencia de registros duplicados activos para la misma acción y el mismo municipio.

### 3. Cobertura departamental

3.1 Cuando una acción tenga registrada cobertura sobre todo el departamento, el sistema no debe permitir registrar relaciones individuales con municipios.                        
3.2 El sistema debe prevenir duplicidades lógicas entre cobertura departamental y selección parcial de municipios.

### 4. Consistencia y uso de la información

4.1 La información territorial debe reflejarse de manera consistente en los módulos de seguimiento, indicadores y reportes.                        
4.2 El sistema debe mantener reglas de validación que eviten inconsistencias territoriales derivadas de duplicidades.

---

### Resultado esperado

El sistema evita la duplicación de la relación acción–municipio y previene inconsistencias entre coberturas parciales y departamentales, garantizando integridad territorial, coherencia del modelo de datos y confiabilidad de la información del PIGCCT en todos los módulos del sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-089.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-089.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-082-092.png)


