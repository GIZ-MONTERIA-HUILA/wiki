# HU-PIGCCT-SYM-248
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Filtros por rango temporal

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                       
> **Quiero:** filtrar las acciones del PIGCCT por rangos de fechas y vigencias.                      
> **Para:** realizar análisis histórico, comparativo y de evolución temporal de la gestión del cambio climático en el territorio.

## CRITERIOS DE ACEPTACIÓN

### 1. Disponibilidad del filtro temporal

1.1 El sistema debe ofrecer un filtro por rango temporal accesible desde el visor geográfico.                 
1.2 El filtro debe estar disponible únicamente cuando exista un PIGCCT activo.                    
1.3 El acceso al filtro debe respetar los permisos asociados al rol del usuario.

### 2. Tipos de filtros temporales

2.1 El sistema debe permitir filtrar acciones por:

- Fecha de inicio de la acción.
- Fecha de finalización de la acción.
- Rango de vigencia del PIGCCT o de la acción.

2.2 El usuario debe poder definir:

- Fecha inicial.
- Fecha final.

2.3 El sistema debe permitir seleccionar rangos abiertos (solo fecha inicial o solo fecha final).

### 3. Comportamiento del visor geográfico

3.1 Al aplicar el filtro temporal, el visor debe mostrar únicamente:

- Acciones cuya ejecución o vigencia coincida total o parcialmente con el rango seleccionado.

3.2 Las capas geográficas deben actualizarse automáticamente según el filtro aplicado.                            
3.3 La simbología debe ajustarse para reflejar el subconjunto temporal filtrado.

### 4. Comportamiento del tablero analítico

4.1 Los gráficos, tablas e indicadores deben actualizarse automáticamente según el rango temporal seleccionado.                       
4.2 El tablero debe permitir analizar:

- Evolución temporal de acciones.
- Distribución de acciones por periodo.
- Comparaciones entre vigencias.

### 5. Integración con otros filtros

5.1 El filtro temporal debe poder combinarse con:

- Filtros territoriales.
- Filtros por eje.
- Filtros por medida.
- Filtros por indicador.

5.2 La lógica de combinación debe ser acumulativa (AND).

### 6. Gestión del filtro temporal

6.1 El sistema debe permitir:

- Activar o desactivar el filtro temporal.
- Modificar el rango seleccionado sin reiniciar el visor.
- Limpiar el filtro temporal.

6.2 Al limpiar los filtros, el visor y el tablero deben regresar al estado inicial del PIGCCT activo.

### 7. Validaciones y manejo de errores

7.1 El sistema debe validar que:

- La fecha inicial no sea posterior a la fecha final.
- El rango seleccionado sea compatible con las vigencias existentes.

7.2 En caso de rango inválido:

- El sistema debe mostrar un mensaje claro de validación.
- No debe aplicar el filtro hasta corregir los valores.

7.3 Si el rango no genera resultados:

- El visor debe indicarlo visualmente.
- El tablero debe mostrar ausencia de datos.

### 8. Usabilidad y rendimiento

8.1 El selector de fechas debe ser intuitivo y consistente con el diseño del sistema.                
8.2 La aplicación del filtro debe realizarse en tiempo casi real.                

---

### Resultado esperado

Un filtro temporal robusto y flexible que permita analizar la evolución histórica y vigencia de las acciones del PIGCCT, garantizando coherencia entre el visor geográfico y el tablero analítico.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-248.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-248.png)