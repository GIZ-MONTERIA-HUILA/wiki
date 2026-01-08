# HU-PIGCCT-SYM-013  
## Épica: Administración de ejes del PIGCCT  
### Definir alcance del eje

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** clasificar cada eje del PIGCCT como **estratégico** o **transversal**.  
> **Para:** diferenciar claramente su rol, nivel de intervención y función dentro del plan de gestión de cambio climático.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Tipos de alcance del eje
1.1 El sistema debe definir de forma parametrizada los tipos de alcance del eje:
- Estratégico.
- Transversal.

1.2 Los valores deben ser controlados (catálogo o enumeración) y no editables manualmente por el usuario final.



### 2. Definición del alcance al registrar el eje
2.1 Al momento de crear un eje, el sistema debe exigir la selección del **alcance del eje**.  
2.2 El campo debe ser obligatorio y no permitir valores nulos.



### 3. Edición del alcance del eje
3.1 El sistema debe permitir al administrador modificar el alcance del eje, siempre que el eje:
- Esté activo.
- No tenga restricciones de negocio que lo impidan.

3.2 El cambio de alcance debe reflejarse inmediatamente en:
- La vista de detalle del eje.
- Los listados asociados al PIGCCT.



### 4. Visualización diferenciada
4.1 El sistema debe mostrar claramente el alcance del eje en:
- Listados de ejes.
- Vistas de detalle.
- Reportes.

4.2 Los ejes estratégicos y transversales deben poder diferenciarse visualmente mediante:
- Etiquetas.
- Íconos.
- Colores (según lineamientos de diseño del sistema).



### 5. Uso del alcance en otros módulos
5.1 El alcance del eje debe poder utilizarse como criterio de:
- Filtrado.
- Agrupación.
- Análisis en reportes y tableros.

5.2 Otros módulos del sistema (indicadores, proyectos, acciones) deben poder identificar el alcance del eje asociado.



### 6. Integridad y consistencia
6.1 El sistema debe garantizar que cada eje tenga **un único alcance válido**.  
6.2 No debe permitirse asignar múltiples alcances al mismo eje.



### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar:
- Usuario que definió o modificó el alcance.
- Fecha y hora del cambio.
- Valor anterior y nuevo (si aplica).



### 8. Usabilidad y experiencia de usuario
8.1 El sistema debe mostrar mensajes claros al confirmar la definición o modificación del alcance.  
8.2 En caso de error, el sistema debe indicar claramente la causa.

---

### Resultado esperado

Cada eje del PIGCCT queda **claramente clasificado como estratégico o transversal**, permitiendo una mejor organización, análisis y uso del plan dentro del sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-013.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-013.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-012-023.png)
