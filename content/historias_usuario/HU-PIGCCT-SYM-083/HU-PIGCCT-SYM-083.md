# HU-PIGCCT-SYM-083
## Épica: Gestión territorial de la acción (municipios)
### Seleccionar departamento de referencia

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                    
> **Quiero:** seleccionar el departamento de referencia para la acción.                      
> **Para:** filtrar los municipios disponibles y asegurar que la acción se asocie únicamente al territorio correspondiente al PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Selección del departamento

1.1 El sistema debe permitir seleccionar el departamento de referencia de la acción.                      
1.2 El departamento disponible debe corresponder únicamente al departamento asociado al PIGCCT activo.

### 2. Filtrado de municipios

2.1 Una vez seleccionado el departamento, el sistema debe mostrar únicamente los municipios pertenecientes a dicho departamento.                     
2.2 El sistema no debe permitir la visualización ni selección de municipios de otros departamentos.

### 3. Restricciones de selección

3.1 El sistema debe impedir asociar municipios que no pertenezcan al departamento del PIGCCT.                      
3.2 En caso de intento de selección inválida, el sistema debe mostrar un mensaje de validación al usuario.

### 4. Consistencia y validación

4.1 El sistema debe garantizar la coherencia entre el departamento seleccionado y el alcance territorial definido para la acción.                     
4.2 El sistema debe mantener esta restricción en todos los módulos donde se gestione o consulte la acción.

---

### Resultado esperado

El sistema permite seleccionar únicamente el departamento asociado al PIGCCT y filtra correctamente los municipios disponibles, garantizando que las acciones se asignen exclusivamente al territorio correspondiente y manteniendo la integridad territorial del modelo de datos.

---
    
## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-083.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-083.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-082-092.png)
