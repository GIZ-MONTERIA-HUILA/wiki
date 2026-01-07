# HU-PIGCCT-SYM-029  
## Épica: Administración de medidas del PIGCCT  
### Registrar área de intervención territorial

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** registrar el área territorial de intervención asociada a una medida del PIGCCT.  
> **Para:** ubicar geográficamente la implementación de la medida y facilitar su análisis espacial y territorial.



## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y acceso
1.1 Solo los usuarios con rol **administrador** pueden registrar, editar o inactivar el área de intervención territorial.  
1.2 Los usuarios de consulta pueden visualizar el área registrada en el visor geográfico.



### 2. Asociación con la medida
2.1 El sistema debe permitir registrar áreas de intervención únicamente para **medidas válidas** del PIGCCT.  
2.2 Cada área de intervención debe estar asociada, como mínimo, a una medida.  
2.3 Una medida puede tener una o varias áreas de intervención (si el diseño del sistema lo permite).



### 3. Registro del área territorial
3.1 El sistema debe permitir registrar el área de intervención mediante:
- Dibujo directo sobre el mapa (polígono, multipolígono).
- Selección de unidades territoriales predefinidas (opcional), como municipio, departamento o región.

3.2 El sistema debe permitir almacenar la geometría en un sistema de referencia espacial definido (ej. MAGNA-SIRGAS).



### 4. Información mínima del área de intervención
Cada área de intervención debe permitir registrar:

- **Nombre o identificador del área** (obligatorio).  
- **Tipo de área** (ej. municipal, subregional, puntual, área protegida, cuenca, etc.).  
- **Geometría** del área de intervención (obligatoria).  

Campos adicionales (opcional según diseño):
- Descripción.
- Observaciones técnicas.



### 5. Validaciones espaciales
5.1 El sistema debe validar que:
- La geometría no esté vacía.
- La geometría sea válida topológicamente.
- El área se encuentre dentro del territorio nacional (si aplica).

5.2 El sistema debe impedir guardar geometrías inválidas o incompletas.



### 6. Visualización en el visor geográfico
6.1 El sistema debe mostrar el área de intervención en el mapa con un estilo diferenciado.  
6.2 Debe permitir activar o desactivar la visualización del área.  
6.3 El usuario debe poder centrar o hacer zoom sobre el área registrada.



### 7. Edición y gestión del estado
7.1 El usuario administrador debe poder editar la geometría y atributos del área.  
7.2 El sistema debe permitir **activar o inactivar** un área de intervención sin eliminarla.  
7.3 Las áreas inactivas no deben mostrarse por defecto.



### 8. Persistencia y trazabilidad
8.1 El sistema debe almacenar el histórico de áreas de intervención asociadas a la medida.  
8.2 Si existe auditoría, debe registrar:
- Usuario creador.
- Fecha de creación.
- Modificaciones realizadas.



### 9. Uso en módulos posteriores
9.1 Las áreas de intervención deben poder ser utilizadas en:
- Análisis espaciales.
- Cruces territoriales con indicadores.
- Reportes cartográficos y temáticos.



### Resultado esperado

El sistema permite **ubicar y gestionar espacialmente la implementación de cada medida del PIGCCT**, fortaleciendo el análisis territorial, el seguimiento geográfico y la toma de decisiones basadas en información espacial.

   
## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-029.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-029.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-029-041.png)


