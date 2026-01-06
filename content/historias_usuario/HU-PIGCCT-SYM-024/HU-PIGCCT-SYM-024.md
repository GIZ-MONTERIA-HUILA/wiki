# HU-PIGCCT-SYM-024  
## Épica: Administración de medidas del PIGCCT  
### Registrar medida del PIGCCT

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** registrar una medida del PIGCCT asociada a un eje.  
> **Para:** definir y estructurar las líneas estratégicas, líneas de acción y medidas concretas que componen el plan territorial de gestión del cambio climático.



## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y control de acceso
1.1 El sistema debe permitir el registro de medidas **únicamente** a usuarios con rol de **administrador**.  
1.2 Los usuarios con rol de consulta deben acceder solo en modo lectura.



### 2. Asociación obligatoria al eje
2.1 El sistema debe exigir que toda medida esté asociada a:
- Un **PIGCCT válido**.
- Un **eje válido y activo** del PIGCCT.

2.2 El sistema debe mostrar únicamente los ejes activos del PIGCCT seleccionado para su asociación.



### 3. Información mínima de la medida
3.1 El sistema debe permitir registrar, como mínimo, los siguientes campos:
- Nombre de la medida.
- Descripción de la medida.
- Eje asociado.
- Tipo de medida (mitigación, adaptación o transversal, si aplica).
- Estado inicial (activo por defecto).



### 4. Validaciones
4.1 El nombre de la medida no debe estar vacío.  
4.2 El sistema debe validar que no exista otra medida con el mismo nombre asociada al **mismo eje**.  
4.3 La descripción debe cumplir con las reglas de longitud y formato definidas.



### 5. Persistencia y relaciones
5.1 Al guardar la medida, el sistema debe:
- Almacenar la información en la base de datos.
- Conservar la relación con el eje y el PIGCCT correspondiente.

5.2 La medida debe contar con un identificador único.



### 6. Trazabilidad y auditoría
6.1 El sistema debe registrar:
- Usuario creador.
- Fecha y hora de creación.

6.2 La información debe estar disponible para auditoría y análisis histórico.



### 7. Confirmación y mensajes
7.1 Al finalizar el registro correctamente, el sistema debe mostrar un mensaje de confirmación, por ejemplo:
> “La medida ha sido registrada exitosamente”.

7.2 En caso de error, el sistema debe mostrar mensajes claros que permitan corregir la información.



### 8. Usabilidad y experiencia de usuario
8.1 El formulario de registro debe ser claro, guiado y de fácil uso.  
8.2 El sistema debe permitir:
- Cancelar el registro sin guardar información.
- Redirigir al usuario al listado de medidas del eje correspondiente.



### Resultado esperado

El administrador puede **registrar medidas del PIGCCT asociadas a un eje específico**, asegurando la correcta estructuración del plan, la integridad referencial y la trazabilidad de la información.



   
## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-024.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-024.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-024-041.png)
