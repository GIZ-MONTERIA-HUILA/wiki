# HU-PIGCCT-SYM-246
## Épica: Detalle funcional del visor geográfico del PIGCCT
### Sincronización mapa–tablero

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema (administrador o consulta).                
> **Quiero:** que las selecciones realizadas en el mapa del visor geográfico se sincronicen automáticamente con los gráficos y tablas del tablero.                     
> **Para:** realizar un análisis integrado y coherente entre la información espacial y los datos analíticos del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la sincronización mapa–tablero

1.1 El sistema debe permitir la sincronización automática entre el visor geográfico y el tablero de análisis.            
1.2 La funcionalidad debe estar disponible para usuarios con permisos de consulta o gestión del PIGCCT.                    
1.3 La sincronización debe operar únicamente cuando exista un PIGCCT activo.    

### 2. Eventos de sincronización

2.1 El sistema debe sincronizar el tablero cuando el usuario:
- Seleccione un municipio en el mapa.
- Seleccione una acción del PIGCCT.
- Cambie filtros espaciales relevantes.

2.2 Cada evento de selección debe generar una actualización inmediata del tablero.

### 3. Comportamiento del tablero

3.1 Al seleccionar un municipio, el tablero debe:
- Actualizar gráficos e indicadores asociados al municipio.
- Filtrar tablas según el territorio seleccionado.

3.2 Al seleccionar una acción, el tablero debe:
- Mostrar información detallada de la acción.
- Actualizar indicadores relacionados con su estado, avance o inversión.

### 4. Consistencia de la información

4.1 La información mostrada en el mapa y en el tablero debe ser consistente y provenir de la misma fuente de datos.                       
4.2 El sistema debe evitar discrepancias entre los datos espaciales y los analíticos.                        
4.3 La sincronización no debe alterar el PIGCCT activo ni la configuración general del visor.

### 5. Interacción bidireccional (si aplica)

5.1 El sistema puede permitir que las selecciones realizadas en el tablero:

- Resalten la entidad correspondiente en el mapa.
- Centren la vista del mapa en la entidad seleccionada.

5.2 Esta interacción debe realizarse sin recargar el visor ni el tablero.

### 6. Manejo de errores y validaciones

6.1 Si ocurre un error durante la sincronización, el sistema debe:

- Mantener la última visualización válida.
- Informar al usuario sobre el inconveniente.

6.2 El sistema debe prevenir la sincronización de datos incompletos o inconsistentes.

### 7. Usabilidad y experiencia de usuario

7.1 La sincronización debe realizarse en tiempo casi real, sin afectar el rendimiento del sistema.                  
7.2 El usuario debe percibir claramente la relación entre el mapa y el tablero.                      
7.3 El sistema debe permitir deshacer o cambiar la selección sin pérdida de información.

---

### Resultado esperado

Un visor geográfico y tablero de análisis completamente sincronizados, donde las selecciones espaciales se reflejen de forma inmediata en gráficos y tablas, permitiendo un análisis integrado, coherente y eficiente del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-246.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-246.png)