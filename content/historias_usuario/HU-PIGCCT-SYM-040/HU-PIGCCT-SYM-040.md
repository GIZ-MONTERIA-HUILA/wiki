# HU-PIGCCT-SYM-040  
## Épica: Administración de medidas del PIGCCT  
### Integridad referencial con eje

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema / administrador.  
> **Quiero:** asegurar que cada medida del PIGCCT esté asociada a un eje válido.  
> **Para:** mantener la consistencia del modelo de datos, la correcta estructura jerárquica del plan y la integridad de la información.



## CRITERIOS DE ACEPTACIÓN

### 1. Asociación obligatoria con eje
1.1 El sistema debe exigir que toda medida esté asociada **obligatoriamente** a un eje del PIGCCT.  
1.2 No debe ser posible crear ni guardar una medida sin seleccionar previamente un eje válido.



### 2. Validación del eje
2.1 El sistema debe validar que el eje seleccionado:
- Exista en la base de datos.  
- Esté asociado al PIGCCT correspondiente.  

2.2 El sistema debe impedir la asociación con ejes inexistentes o eliminados.



### 3. Estado del eje
3.1 El sistema debe validar el **estado del eje** al momento de asociar una medida.  
3.2 No debe permitirse asociar nuevas medidas a ejes inactivos, salvo reglas de negocio explícitas.



### 4. Comportamiento ante cambios del eje
4.1 Si un eje es inactivado:
- Las medidas asociadas deben conservarse para fines históricos.  
- El sistema debe advertir que no se podrán crear nuevas medidas bajo ese eje mientras esté inactivo.

4.2 El sistema no debe eliminar ni alterar automáticamente las medidas existentes al cambiar el estado del eje.



### 5. Integridad en edición
5.1 Al editar una medida, el sistema debe permitir cambiar el eje asociado únicamente a:
- Ejes válidos.  
- Ejes pertenecientes al mismo PIGCCT.

5.2 El sistema debe validar la coherencia jerárquica tras el cambio de eje.



### 6. Integridad a nivel de base de datos
6.1 El modelo de datos debe implementar **llaves foráneas** entre medidas y ejes.  
6.2 El sistema debe manejar adecuadamente errores de integridad referencial y mostrar mensajes claros al usuario.



### 7. Uso en otros módulos
7.1 La relación medida–eje debe ser utilizada de forma consistente en:
- Consultas jerárquicas del PIGCCT.  
- Reportes y tableros de control.  
- Módulos de seguimiento y evaluación.



### Resultado esperado

El sistema garantiza que **toda medida del PIGCCT esté correctamente asociada a un eje válido**, asegurando integridad referencial, consistencia estructural y confiabilidad de la información en todo el sistema.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-040.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-040.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-024-041.png)
