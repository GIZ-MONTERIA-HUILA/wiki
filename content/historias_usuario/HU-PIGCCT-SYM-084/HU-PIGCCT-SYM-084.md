# HU-PIGCCT-SYM-084
## Épica: Gestión territorial de la acción (municipios)
### Seleccionar uno o varios municipios

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.                       
> **Quiero:** seleccionar uno o varios municipios para la acción.                  
> **Para:** definir con precisión el territorio exacto donde se ejecuta la intervención del PIGCCT.

## CRITERIOS DE ACEPTACIÓN

### 1. Selección múltiple de municipios

1.1 El sistema debe permitir la selección de uno o varios municipios de forma simultánea.                              
1.2 La selección de municipios debe realizarse a partir del listado filtrado por el departamento del PIGCCT.

## 2. Validaciones territoriales

2.1 El sistema debe validar que todos los municipios seleccionados pertenezcan al departamento asociado al PIGCCT.                      
2.2 El sistema debe impedir la selección de municipios de otros departamentos.

## 3. Reglas de obligatoriedad

3.1 Cuando el alcance territorial de la acción sea municipios específicos, el sistema debe exigir la selección de al menos un municipio.                  
3.2 El sistema no debe permitir guardar la acción si no se ha seleccionado ningún municipio cuando esta opción esté activa.

## 4. Consistencia y uso de la información

4.1 El sistema debe asociar correctamente la acción con todos los municipios seleccionados.                   
4.2 La información de municipios asociados debe reflejarse de manera consistente en los módulos de seguimiento, indicadores y reportes.

## Resultado esperado

El sistema permite la selección múltiple de municipios para cada acción, asegurando que el territorio de intervención quede claramente definido, validado y alineado con el departamento del PIGCCT, manteniendo la coherencia territorial en todos los módulos del sistema.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-084.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-084.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-082-092.png)
