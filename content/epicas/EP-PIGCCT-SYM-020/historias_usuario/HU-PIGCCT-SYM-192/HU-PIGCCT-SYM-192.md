# HU-PIGCCT-SYM-192  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Configurar flujos de validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** configurar los flujos de validación del PIGCCT según el tipo de acción o la entidad responsable.  
> **Para:** garantizar que las acciones sigan el proceso de revisión institucional definido y se ajusten a los lineamientos de control establecidos.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la configuración de flujos
1.1 El sistema debe permitir el acceso al módulo **Configuración de flujos de validación** únicamente a usuarios con rol **administrador**.  
1.2 El acceso debe estar disponible desde el módulo de **Administración**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos administrativos.

### 2. Tipos de flujo de validación
2.1 El sistema debe permitir configurar diferentes **tipos de flujos de validación**, tales como:
- Validación simple.
- Doble validación (Entidad → CAR).
- Otros flujos definidos por la institución.

2.2 Cada flujo debe poder asociarse a:
- Tipo de acción.
- Entidad responsable.
- Configuración territorial, si aplica.

### 3. Configuración por tipo de acción
3.1 El sistema debe permitir definir qué flujo de validación aplica según el **tipo de acción**.  
3.2 La configuración debe garantizar que, al enviar una acción a validación, se active automáticamente el flujo correspondiente.

### 4. Configuración por entidad
4.1 El sistema debe permitir definir flujos específicos según la **entidad responsable**.  
4.2 Las reglas deben permitir diferenciar procesos entre distintas entidades.

### 5. Orden y secuencia del flujo
5.1 El administrador debe poder definir:
- Etapas del flujo.
- Roles validadores por etapa.
- Secuencia obligatoria de validación.

5.2 El sistema debe garantizar que las etapas se ejecuten en el orden configurado.

### 6. Aplicación automática del flujo
6.1 Al enviar una acción a validación, el sistema debe:
- Identificar el flujo configurado.
- Activar automáticamente las etapas correspondientes.

6.2 El usuario no debe intervenir manualmente en la selección del flujo durante el envío.

### 7. Auditoría y trazabilidad
7.1 El sistema debe registrar:
- Configuraciones realizadas.
- Usuario administrador responsable.
- Fecha y hora de los cambios.

7.2 El historial de cambios en los flujos debe estar disponible para auditoría.

### 8. Control de acceso y seguridad
8.1 Solo usuarios con rol administrador deben poder modificar flujos de validación.  
8.2 El sistema debe impedir configuraciones inconsistentes o incompletas.

### 9. Usabilidad y experiencia de usuario
9.1 La interfaz de configuración debe ser clara y guiada.  
9.2 El sistema debe mostrar validaciones y mensajes de ayuda durante la configuración.  
9.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El administrador puede **configurar de manera flexible los flujos de validación del PIGCCT**, definiendo reglas por tipo de acción o entidad, asegurando que cada acción siga el proceso institucional correcto con trazabilidad, control y coherencia normativa.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-192.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-192.png)


