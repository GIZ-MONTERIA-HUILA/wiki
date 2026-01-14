# HU-PIGCCT-SYM-051  
## Épica: Administración de indicadores del PIGCCT  
### Registrar actores involucrados

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** registrar los actores involucrados en el indicador.  
> **Para:** facilitar la coordinación interinstitucional, la articulación de roles y la gestión colaborativa en el seguimiento del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Registro de actores involucrados
1.1 El sistema debe permitir registrar uno o varios **actores involucrados** asociados al indicador.  
1.2 Los actores deben poder seleccionarse desde un catálogo institucional o registrarse manualmente (cuando aplique).  
1.3 El registro de actores involucrados debe ser obligatorio cuando el indicador así lo requiera según su tipo o alcance.



### 2. Información del actor
2.1 Para cada actor involucrado, el sistema debe permitir registrar:
- Nombre de la entidad, organización o actor.  
- Tipo de actor (institucional, comunitario, privado, académico, cooperación, etc.).  
- Rol o nivel de participación (ejecutor, apoyo, articulador, beneficiario, veedor, etc.).

2.2 El sistema debe permitir asociar actores internos y externos al sistema.



### 3. Relación con responsables del indicador
3.1 El sistema debe diferenciar claramente entre **responsables del indicador** y **actores involucrados**.  
3.2 Un actor involucrado no necesariamente debe ser responsable del indicador.  
3.3 El sistema debe permitir que un responsable también pueda ser registrado como actor, si aplica.



### 4. Validaciones de coherencia
4.1 El sistema debe validar la coherencia de los actores involucrados con:
- La medida asociada.  
- El tipo de indicador.  

4.2 El sistema debe advertir si los actores registrados no corresponden al ámbito del indicador.



### 5. Integridad con el indicador y la medida
5.1 El sistema debe mostrar como referencia el indicador, la medida, el eje y el PIGCCT asociados.  
5.2 El sistema debe impedir guardar actores involucrados si el indicador no está correctamente asociado a una medida válida.



### 6. Edición y trazabilidad
6.1 El sistema debe permitir agregar, modificar o retirar actores involucrados del indicador.  
6.2 El sistema debe conservar el historial de cambios, registrando:
- Actor agregado, modificado o eliminado.  
- Fecha de la acción.  
- Usuario que realizó la modificación.

---

### Resultado esperado

El sistema permite identificar y gestionar los actores involucrados en los indicadores del PIGCCT, fortaleciendo la coordinación interinstitucional, la transparencia y la gobernanza del proceso de seguimiento y evaluación del plan.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-051.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-051.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)

