# HU-PIGCCT-SYM-176  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Dashboard adaptado por rol

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autenticado.  
> **Quiero:** que el contenido del dashboard se adapte automáticamente a mi rol.  
> **Para:** visualizar únicamente la información relevante para mis responsabilidades dentro del sistema PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Adaptación del dashboard por rol
1.1 El sistema debe adaptar automáticamente el contenido del **dashboard** según el rol del usuario autenticado.  
1.2 El sistema debe determinar el rol activo al momento de cargar el dashboard.  
1.3 La información mostrada debe corresponder únicamente a los permisos asociados al rol.

### 2. Contenido para usuario registrador
2.1 El **usuario registrador** debe visualizar:
- Acciones propias creadas por el usuario.
- Estados de sus acciones (borrador, en validación, validadas, rechazadas).
- Alertas relacionadas con sus acciones.

2.2 El sistema no debe mostrar acciones creadas por otros usuarios.

### 3. Contenido para usuario validador
3.1 El **usuario validador** (entidad o CAR) debe visualizar:
- Acciones pendientes de validación.
- Alertas relacionadas con procesos de validación.

3.2 El sistema debe priorizar la visualización de acciones que requieren revisión.

### 4. Contenido para usuario administrador
4.1 El **usuario administrador** debe visualizar:
- Una **vista consolidada** de todas las acciones.
- Estados generales del PIGCCT.
- Alertas globales del sistema.

4.2 La información debe permitir una visión integral para la gestión y toma de decisiones.

### 5. Contenido para usuario consulta
5.1 El **usuario consulta** debe visualizar:
- Únicamente información validada.
- Indicadores y acciones aprobadas.

5.2 El sistema no debe mostrar información en borrador, en validación o rechazada.

### 6. Control de acceso y seguridad
6.1 El sistema debe garantizar que:
- Cada rol acceda solo a la información permitida.
- No sea posible acceder a información restringida por navegación directa.

6.2 Las validaciones de acceso deben aplicarse tanto en frontend como en backend.

### 7. Actualización y consistencia de la información
7.1 El dashboard debe mostrar información actualizada al momento de cargarse.  
7.2 Los cambios en el estado de las acciones deben reflejarse automáticamente en el dashboard.

### 8. Usabilidad y experiencia de usuario
8.1 El dashboard debe mantener una estructura clara y coherente, independientemente del rol.  
8.2 La presentación debe evitar sobrecarga de información mostrando solo lo relevante.  
8.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El sistema presenta un **dashboard adaptado al rol del usuario**, mostrando únicamente la información relevante y autorizada para cada tipo de usuario, facilitando la gestión, validación, supervisión o consulta del estado del PIGCCT de forma clara y eficiente.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-176.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-176.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-176.png)
