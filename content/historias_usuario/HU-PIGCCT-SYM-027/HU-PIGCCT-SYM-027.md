# HU-PIGCCT-SYM-027  
## Épica: Administración de medidas del PIGCCT  
### Registrar acciones por horizonte temporal

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador.  
> **Quiero:** registrar acciones asociadas a una medida del PIGCCT, clasificadas por horizonte temporal.  
> **Para:** planificar de manera progresiva y ordenada la implementación de la medida en el corto, mediano y largo plazo.



## DEFINICIÓN DE HORIZONTES TEMPORALES

El sistema debe manejar, como mínimo, los siguientes horizontes:

- **Corto plazo**
- **Mediano plazo**
- **Largo plazo**

Estos valores deben ser controlados por catálogo o configuración del sistema.



## CRITERIOS DE ACEPTACIÓN

### 1. Permisos y acceso
1.1 Solo los usuarios con rol **administrador** pueden crear, editar o inactivar acciones.  
1.2 Los usuarios de consulta pueden visualizar las acciones registradas.



### 2. Registro de acciones
2.1 El sistema debe permitir registrar una o varias **acciones** asociadas a una medida.  
2.2 Cada acción debe estar asociada obligatoriamente a:
- Una **medida** válida.
- Un **horizonte temporal** (corto, mediano o largo plazo).



### 3. Información mínima de la acción
Cada acción debe permitir registrar al menos:

- **Nombre o título de la acción** (obligatorio).  
- **Descripción de la acción** (obligatorio).  
- **Horizonte temporal** (obligatorio).  

Campos adicionales (opcional según diseño):
- Fecha estimada de inicio y fin.
- Observaciones.



### 4. Validaciones
4.1 El sistema debe validar que:
- La acción tenga una medida asociada.
- El horizonte temporal sea válido.
- Los campos obligatorios estén diligenciados.

4.2 El sistema debe evitar el registro de acciones duplicadas con el mismo nombre dentro de la misma medida y horizonte temporal (si se configura esta regla).



### 5. Organización y visualización
5.1 El sistema debe presentar las acciones agrupadas por:
- Horizonte temporal.
- Medida.

5.2 La visualización debe permitir identificar claramente:
- Acciones de corto plazo.
- Acciones de mediano plazo.
- Acciones de largo plazo.



### 6. Edición y gestión del estado
6.1 El usuario administrador debe poder editar la información de una acción.  
6.2 El sistema debe permitir **activar o inactivar** una acción sin eliminarla.  
6.3 Las acciones inactivas no deben mostrarse por defecto en vistas operativas.



### 7. Persistencia y trazabilidad
7.1 El sistema debe almacenar las acciones y su horizonte temporal.  
7.2 Si el sistema cuenta con auditoría, debe registrar:
- Usuario creador.
- Fecha de creación.
- Cambios realizados.



### 8. Uso en módulos posteriores
8.1 Las acciones registradas deben poder ser utilizadas en:
- Módulos de seguimiento.
- Registro de indicadores.
- Reportes de avance del PIGCCT.



### Resultado esperado

El sistema permite **planificar la implementación de cada medida mediante acciones claramente definidas y organizadas por horizonte temporal**, facilitando la programación, el seguimiento y la evaluación progresiva del PIGCCT.



   
## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-027.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-027.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-024-041.png)