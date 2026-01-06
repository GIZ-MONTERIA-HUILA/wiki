# HU-PIGCCT-SYM-060  
## Épica: Administración de indicadores del PIGCCT  
### Integridad referencial con medida

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** asegurar que todo indicador esté asociado a una medida válida.  
> **Para:** mantener la consistencia, coherencia e integridad del modelo de datos del PIGCCT.



## CRITERIOS DE ACEPTACIÓN

### 1. Asociación obligatoria con medida
1.1 El sistema debe exigir que cada indicador esté asociado a **una y solo una medida válida**.  
1.2 El campo de asociación a medida debe ser obligatorio al crear o editar un indicador.  
1.3 El sistema no debe permitir guardar indicadores sin una medida asociada.



### 2. Validación de la medida asociada
2.1 El sistema debe validar que la medida seleccionada:
- Exista en la base de datos.  
- Se encuentre en estado **activo**, salvo en consultas históricas.  

2.2 El sistema debe impedir la asociación de un indicador a una medida inexistente o inválida.



### 3. Restricciones de eliminación
3.1 El sistema debe impedir la eliminación de una medida que tenga indicadores asociados.  
3.2 En caso de inactivar una medida, los indicadores asociados deben conservar su información histórica y estado.



### 4. Consistencia jerárquica
4.1 El sistema debe garantizar la coherencia jerárquica:
- Indicador → Medida → Eje → PIGCCT.  

4.2 El sistema debe asegurar que todos los niveles de la jerarquía correspondan al mismo PIGCCT.



### 5. Integración con otros módulos
5.1 La relación indicador–medida debe ser utilizada de forma consistente en:
- Módulos de seguimiento.  
- Módulos de análisis y reporte.  
- Módulos de visualización y consulta.

5.2 El sistema debe impedir inconsistencias en los flujos de información entre módulos.



### 6. Trazabilidad y control
6.1 El sistema debe registrar cambios en la asociación del indicador con la medida.  
6.2 Cada cambio debe almacenar:
- Medida anterior.  
- Nueva medida.  
- Fecha del cambio.  
- Usuario que realizó la modificación.



### Resultado esperado

El sistema garantiza que todos los indicadores del PIGCCT estén correctamente asociados a una medida válida, preservando la integridad referencial, la coherencia jerárquica y la confiabilidad de la información en todos los módulos del sistema.



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-pigcct-sym-060.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-pigcct-sym-060.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)
