# HU-PIGCCT-SYM-185  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Flujo de doble validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** que el sistema soporte un flujo de validación secuencial Entidad → CAR.  
> **Para:** garantizar el control institucional, la trazabilidad y la correcta aprobación de las acciones del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Definición del flujo de doble validación
1.1 El sistema debe implementar un **flujo de validación secuencial** compuesto por dos etapas:
- Validación por **Entidad**.
- Validación por **CAR**.

1.2 El flujo debe aplicarse a las acciones del PIGCCT que requieran doble validación según configuración del sistema.

### 2. Estados del flujo de validación
2.1 El sistema debe manejar estados diferenciados para cada etapa del flujo, como mínimo:
- **En validación Entidad**.
- **En validación CAR**.
- **Validada**.
- **Rechazada**.

2.2 Los estados deben reflejar claramente el avance de la acción en el proceso de validación.

### 3. Comportamiento de la validación por Entidad
3.1 Cuando una acción se encuentre en estado **En validación Entidad**:
- Solo usuarios con rol **validador entidad** deben poder validarla o rechazarla.

3.2 Al validar por Entidad:
- La acción debe avanzar automáticamente a **En validación CAR**.

3.3 Al rechazar por Entidad:
- La acción debe cambiar a estado **Rechazada**.
- Deben registrarse observaciones obligatorias.

### 4. Comportamiento de la validación por CAR
4.1 Cuando una acción se encuentre en estado **En validación CAR**:
- Solo usuarios con rol **validador CAR** deben poder validarla o rechazarla.

4.2 Al validar por CAR:
- La acción debe cambiar a estado **Validada**.

4.3 Al rechazar por CAR:
- La acción debe cambiar a estado **Rechazada**.
- Deben registrarse observaciones obligatorias.

### 5. Bloqueo de edición durante la validación
5.1 Mientras la acción se encuentre en cualquier estado de validación:
- La edición de la acción debe permanecer bloqueada.
- La información debe mostrarse en modo solo lectura.

### 6. Auditoría y trazabilidad
6.1 El sistema debe registrar automáticamente, para cada etapa:
- Usuario validador.
- Rol del validador.
- Fecha y hora de la validación o rechazo.
- Observaciones registradas.
- Estado anterior y nuevo estado.

6.2 El historial de validaciones debe ser visible en el detalle de la acción.

### 7. Control de acceso y seguridad
7.1 El sistema debe garantizar que cada etapa del flujo solo pueda ser ejecutada por el rol correspondiente.  
7.2 El acceso por navegación directa a etapas no autorizadas debe estar bloqueado.

### 8. Configuración y flexibilidad
8.1 El sistema debe permitir habilitar o deshabilitar el flujo de doble validación según configuración institucional.  
8.2 La configuración debe ser gestionada por usuarios con rol **administrador**.

### 9. Usabilidad y experiencia de usuario
9.1 El flujo de doble validación debe ser claro y comprensible para todos los roles involucrados.  
9.2 El sistema debe mostrar mensajes claros sobre el estado actual y el siguiente paso del proceso.  
9.3 El usuario debe poder identificar fácilmente en qué etapa de validación se encuentra la acción.

---

## Resultado esperado

El sistema **soporta un flujo de doble validación secuencial (Entidad → CAR)**, asegurando que las acciones del PIGCCT sean revisadas y aprobadas de manera ordenada, controlada y trazable, cumpliendo con los requisitos de control institucional.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-185.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-185.png)


