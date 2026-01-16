# HU-PIGCCT-SYM-247
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Filtros territoriales combinados

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                          
> **Quiero:** aplicar filtros avanzados y combinados por departamento, municipio, eje, medida e indicador.                       
> **Para:** analizar de forma precisa y segmentada la información territorial y estratégica del PIGCCT en el visor geográfico y el tablero asociado.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Disponibilidad de filtros avanzados

1.1 El sistema debe ofrecer un módulo de filtros avanzados accesible desde el visor geográfico.                              
1.2 Los filtros deben estar disponibles únicamente cuando exista un PIGCCT activo.                      
1.3 El acceso a los filtros debe respetar los permisos del rol del usuario.

### 2. Tipos de filtros disponibles

2.1 El sistema debe permitir aplicar filtros por:
- Departamento.
- Municipio.
- Eje estratégico del PIGCCT.
- Medida asociada.
- Indicador vinculado.

2.2 Cada filtro debe mostrar únicamente valores válidos según el PIGCCT activo.

### 3. Combinación de filtros

3.1 El usuario debe poder aplicar dos o más filtros de forma simultánea.                      
3.2 Los filtros deben operar bajo una lógica acumulativa (AND).                   
3.3 El sistema debe actualizar automáticamente:

- Las capas del mapa.
- La simbología.
- Los gráficos y tablas del tablero sincronizado.

### 4. Comportamiento del visor geográfico

4.1 Al aplicar filtros combinados, el visor debe:
- Mostrar únicamente las entidades geográficas que cumplan los criterios seleccionados.
- Ajustar la simbología según los resultados filtrados.

4.2 El mapa no debe mostrar información fuera del alcance de los filtros activos.

### 5. Comportamiento del tablero analítico

5.1 Los gráficos, indicadores y tablas deben reflejar exactamente los filtros aplicados en el visor.
5.2 El tablero debe recalcular métricas como:

- Número de acciones.
- Nivel de avance.
- Inversión asociada.
- Distribución por eje o medida.

### 6. Gestión de filtros

6.1 El sistema debe permitir:
- Activar o desactivar filtros individuales.
- Limpiar todos los filtros con una sola acción.

6.2 Al limpiar los filtros, el visor y el tablero deben volver al estado inicial del PIGCCT activo.

### 7. Validaciones y manejo de errores

7.1 El sistema debe validar que la combinación de filtros tenga resultados válidos.                          
7.2 Si una combinación no genera resultados:

- El mapa debe mostrarse vacío o con un mensaje informativo.
- El tablero debe indicar ausencia de datos.               

7.3 El sistema no debe generar errores de carga ni inconsistencias visuales.

### 8. Usabilidad y rendimiento

8.1 La aplicación de filtros debe realizarse en tiempo casi real.
8.2 El sistema debe mostrar claramente qué filtros están activos.

---

### Resultado esperado

Un sistema de filtros avanzados y combinados que permita explorar el PIGCCT desde múltiples dimensiones territoriales y estratégicas, garantizando coherencia entre el visor geográfico y el tablero analítico.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-247.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-247.png)