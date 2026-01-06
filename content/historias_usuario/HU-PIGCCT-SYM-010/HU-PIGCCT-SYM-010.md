# HU-PIGCCT-SYM-010  
## Épica: Administración de la tabla maestra de PIGCCT  
### Relación con catálogo de departamentos

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** asociar cada PIGCCT a un departamento válido de Colombia.  
> **Para:** garantizar la integridad referencial, consistencia territorial y confiabilidad de la información en la base de datos.



## CRITERIOS DE ACEPTACIÓN

### 1. Catálogo oficial de departamentos
1.1 El sistema debe contar con un **catálogo maestro de departamentos de Colombia**, previamente parametrizado.  
1.2 El catálogo debe incluir como mínimo:
- Código del departamento.
- Nombre del departamento.
- Estado (activo/inactivo).

1.3 El catálogo debe ser utilizado de forma transversal por todos los módulos del sistema que requieran referencia territorial.



### 2. Asociación obligatoria al registrar un PIGCCT
2.1 Al crear un nuevo PIGCCT, el sistema debe exigir la selección de un departamento desde el catálogo oficial.  
2.2 El campo **Departamento** debe ser obligatorio y no permitir valores nulos.  
2.3 El departamento debe seleccionarse mediante:
- Lista desplegable.
- Búsqueda asistida (autocomplete).



### 3. Validación de integridad referencial
3.1 El sistema debe validar que el departamento seleccionado exista y esté **activo** en el catálogo.  
3.2 No se debe permitir:
- Ingresar departamentos manualmente.
- Asociar PIGCCT a departamentos inexistentes o inactivos.

3.3 La base de datos debe implementar una **clave foránea** entre PIGCCT y el catálogo de departamentos.



### 4. Comportamiento ante cambios en el catálogo
4.1 Si un departamento es marcado como inactivo en el catálogo:
- No debe poder ser seleccionado para nuevos PIGCCT.
- Los PIGCCT ya asociados deben conservar la relación histórica.

4.2 El sistema debe impedir la eliminación física de un departamento que tenga PIGCCT asociados.



### 5. Visualización y consistencia
5.1 En los listados y vistas de detalle de PIGCCT, el sistema debe mostrar:
- El nombre completo del departamento.
- Opcionalmente, su código oficial.

5.2 La información del departamento debe ser consistente en:
- Listados.
- Filtros.
- Reportes.
- Exportaciones.



### 6. Filtros y consultas por departamento
6.1 El sistema debe permitir filtrar PIGCCT utilizando el catálogo de departamentos.  
6.2 Los filtros deben mostrar únicamente departamentos válidos del catálogo.  



### 7. Auditoría y control
7.1 El sistema debe registrar en auditoría:
- El departamento asociado al momento de creación del PIGCCT.
- Cualquier cambio permitido sobre la relación (si aplica por reglas del negocio).

7.2 La información debe estar disponible para procesos de control y seguimiento institucional.



### Resultado esperado

Cada PIGCCT queda **correctamente relacionado a un departamento válido de Colombia**, asegurando integridad referencial, consistencia territorial y trazabilidad histórica dentro del sistema.


   
## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-010.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-010.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-001-011.png)


