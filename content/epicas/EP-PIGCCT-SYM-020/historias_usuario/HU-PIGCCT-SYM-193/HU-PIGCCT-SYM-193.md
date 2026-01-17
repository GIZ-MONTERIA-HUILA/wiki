# HU-PIGCCT-SYM-193  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Parametrizar el sistema

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** administrar los parámetros globales del sistema PIGCCT.  
> **Para:** configurar reglas generales como vigencias, estados y umbrales que controlan el comportamiento del sistema.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la parametrización del sistema
1.1 El sistema debe permitir el acceso al módulo **Parametrización del sistema** únicamente a usuarios con rol **administrador**.  
1.2 El acceso debe estar disponible desde el módulo de **Administración**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos administrativos.

### 2. Parámetros globales
2.1 El sistema debe permitir administrar parámetros globales, tales como:
- Vigencias.
- Estados del sistema.
- Umbrales de seguimiento.
- Valores de control y alertas.

2.2 Los parámetros deben ser utilizados transversalmente por los distintos módulos del sistema.

### 3. Gestión de vigencias
3.1 El administrador debe poder definir y actualizar:
- Años de vigencia.
- Periodos de implementación.
- Rangos temporales válidos.

3.2 Las vigencias configuradas deben aplicarse automáticamente en los formularios y reportes.

### 4. Gestión de estados
4.1 El sistema debe permitir configurar los estados utilizados en:
- Acciones.
- Indicadores.
- Validaciones.

4.2 Los estados deben estar alineados con los flujos definidos.

### 5. Gestión de umbrales
5.1 El sistema debe permitir definir umbrales para:
- Alertas de seguimiento.
- Identificación de retrasos.
- Indicadores críticos.

5.2 Los umbrales deben ser utilizados para generar alertas automáticas.

### 6. Validaciones de consistencia
6.1 El sistema debe validar que los parámetros configurados:
- No generen conflictos entre módulos.
- Mantengan coherencia temporal y lógica.

6.2 El sistema debe impedir guardar configuraciones inválidas.

### 7. Aplicación automática de parámetros
7.1 Los cambios en los parámetros deben aplicarse automáticamente en el sistema.  
7.2 El sistema debe reflejar los cambios sin afectar información histórica.

### 8. Auditoría y trazabilidad
8.1 El sistema debe registrar:
- Usuario administrador responsable.
- Fecha y hora de la modificación.
- Parámetro anterior y nuevo valor.

8.2 Esta información debe estar disponible para auditoría y control.

### 9. Usabilidad y experiencia de usuario
9.1 La parametrización debe ser clara y organizada por categorías.  
9.2 El sistema debe mostrar ayudas o descripciones para cada parámetro.  
9.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El administrador puede **parametrizar de forma centralizada el sistema PIGCCT**, gestionando vigencias, estados y umbrales que controlan su funcionamiento, asegurando coherencia operativa, flexibilidad institucional y trazabilidad de los cambios.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-193.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-193.png)


