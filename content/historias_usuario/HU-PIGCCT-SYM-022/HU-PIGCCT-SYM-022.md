# HU-PIGCCT-SYM-022  
## Épica: Administración de ejes del PIGCCT  
### Integridad referencial con PIGCCT

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** asegurar que todo eje del PIGCCT esté asociado a un PIGCCT válido.  
> **Para:** mantener la consistencia, integridad referencial y confiabilidad de la información en la base de datos del sistema.



## CRITERIOS DE ACEPTACIÓN

### 1. Asociación obligatoria al PIGCCT
1.1 El sistema debe exigir que todo eje esté asociado obligatoriamente a un **PIGCCT existente**.  
1.2 No se debe permitir la creación de ejes sin un PIGCCT asociado.



### 2. Validación en la creación del eje
2.1 Durante el registro de un eje, el sistema debe:
- Mostrar únicamente PIGCCT válidos para su selección.
- Validar que el PIGCCT seleccionado exista y esté correctamente identificado.

2.2 El identificador del PIGCCT debe almacenarse como clave foránea en el eje.



### 3. Reglas sobre PIGCCT inactivos
3.1 El sistema debe permitir asociar ejes **únicamente** a PIGCCT activos.  
3.2 Si un PIGCCT se encuentra inactivo:
- No debe permitirse la creación de nuevos ejes asociados.
- Los ejes existentes deben conservar su relación histórica.



### 4. Eliminación y protección de datos
4.1 El sistema no debe permitir eliminar un PIGCCT si existen ejes asociados.  
4.2 En caso de inactivación de un PIGCCT, los ejes asociados deben:
- Mantener su vínculo.
- Conservar su estado actual.



### 5. Validación a nivel de base de datos
5.1 La base de datos debe implementar restricciones de integridad referencial (clave foránea) entre:
- Tabla de PIGCCT.
- Tabla de ejes del PIGCCT.

5.2 El sistema debe manejar de forma controlada cualquier intento de violación de la integridad referencial.



### 6. Mensajes de error y retroalimentación
6.1 Si el usuario intenta asociar un eje a un PIGCCT inválido o inexistente, el sistema debe mostrar un mensaje claro, por ejemplo:
> “El PIGCCT seleccionado no es válido o no existe”.

6.2 Los mensajes deben orientar al usuario a corregir la acción.



### 7. Auditoría y trazabilidad
7.1 El sistema debe conservar la trazabilidad de la relación eje–PIGCCT para fines de auditoría.  
7.2 Los cambios de estado del PIGCCT no deben alterar la relación histórica con sus ejes.



### Resultado esperado

El sistema garantiza que **todo eje esté siempre asociado a un PIGCCT válido**, evitando inconsistencias, protegiendo la integridad referencial de la base de datos y asegurando la coherencia estructural del plan.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-pigcct-sym-022.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-pigcct-sym-022.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-012-023.png)