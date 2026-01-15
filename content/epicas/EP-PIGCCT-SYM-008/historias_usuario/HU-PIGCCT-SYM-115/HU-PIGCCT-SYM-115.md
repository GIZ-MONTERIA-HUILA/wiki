# HU-PIGCCT-SYM-115  
## Épica: Gestión de adjuntos y evidencias del PIGCCT  
### Restringir tipos de relación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** que el sistema restrinja los valores permitidos en el campo `relatedtable` de la tabla de adjuntos.  
> **Para:** permitir únicamente asociaciones válidas y autorizadas, prevenir errores de configuración, garantizar la integridad estructural del sistema y facilitar el mantenimiento y evolución de la arquitectura de datos del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Definición de lista blanca de tablas autorizadas
1.1 El sistema debe mantener una **lista blanca** de tablas que pueden tener adjuntos asociados.  
1.2 La lista debe incluir todas las entidades del PIGCCT que requieren evidencia documental, por ejemplo:
- `accion`: Acciones del plan.
- `medida`: Medidas de adaptación o mitigación.
- `indicador`: Indicadores de seguimiento.
- `eje`: Ejes temáticos del plan.
- `proyecto`: Proyectos específicos.
- `capacitacion`: Actividades de capacitación.
- `reunion`: Actas de reuniones.
- Otras entidades según diseño del sistema.

1.3 La lista debe ser configurable y gestionable por administradores del sistema.

### 2. Almacenamiento de la configuración
2.1 La lista de tablas autorizadas debe almacenarse en:
- Tabla de configuración del sistema.
- Archivo de configuración.
- Constantes en el código (menos flexible).

2.2 El método recomendado es una tabla de configuración para permitir actualización sin redespliegue.  
2.3 Cada entrada debe contener:
- Nombre de la tabla (`relatedtable`).
- Descripción funcional (ej: "Acciones del PIGCCT").
- Estado (activa/inactiva).
- Esquema al que pertenece (`relatedschema`).

### 3. Validación durante la asociación de adjuntos
3.1 Antes de permitir asociar un adjunto, el sistema debe validar que el valor de `relatedtable` esté en la lista autorizada.  
3.2 Si el valor no está autorizado, el sistema debe:
- Bloquear la operación inmediatamente.
- No permitir el almacenamiento del archivo.
- No crear registro en la tabla `adjuntos`.

3.3 La validación debe ocurrir antes de cualquier procesamiento costoso.

### 4. Mensaje de error claro
4.1 Al detectar un valor de `relatedtable` no autorizado, el sistema debe mostrar un mensaje de error.  
4.2 Ejemplo para usuarios:  
_"Error: No es posible asociar adjuntos a este tipo de registro. Contacte al administrador si considera que esto es un error."_

4.3 Ejemplo para desarrolladores/logs:  
_"Validación fallida: relatedtable 'tabla_no_autorizada' no está en la lista blanca de tablas permitidas."_

### 5. Validación al agregar nuevas tablas
5.1 Al agregar una nueva tabla a la lista autorizada, el sistema debe validar:
- Que la tabla exista realmente en el esquema especificado.
- Que el nombre esté correctamente escrito.
- Que no esté ya registrada.

5.2 Si la validación falla, debe informarse claramente al administrador.

### 6. Impacto en inactivación de tablas
7.1 Si se inactiva una tabla de la lista autorizada, el sistema debe:
- Bloquear nuevas asociaciones de adjuntos a esa tabla.
- Mantener acceso de solo lectura a adjuntos existentes.
- Informar claramente que la tabla está inactiva para nuevas asociaciones.

7.2 Los adjuntos existentes NO deben eliminarse ni ocultarse automáticamente.

### 8. Consulta de tablas autorizadas para usuarios
8.1 Los usuarios pueden consultar qué tipos de registros permiten adjuntos.  
8.2 Esta información puede mostrarse:
- En la ayuda del sistema.
- En un tooltip o mensaje informativo.
- En documentación técnica.

8.3 Ejemplo: _"Puede asociar adjuntos a: Acciones, Medidas, Indicadores, Proyectos."_

### 9. Validación a nivel de API y servicios
9.1 La restricción debe aplicarse en todos los puntos de entrada:
- APIs REST/GraphQL.
- Formularios web.
- Servicios backend.
- Importaciones masivas.

9.2 No debe ser posible eludir la validación mediante llamadas directas a la API.

### 10. Auditoría de intentos rechazados
10.1 El sistema debe registrar en logs todos los intentos de asociar adjuntos a tablas no autorizadas.  
10.2 El registro debe incluir:
- Usuario que intentó la operación.
- Tabla no autorizada especificada.
- Fecha y hora.
- Contexto adicional (ID de registro, acción intentada).

10.3 Esta información es útil para:
- Detectar errores en el código o configuración.
- Identificar necesidades de agregar nuevas tablas.
- Detectar posibles intentos maliciosos.

### 11. Compatibilidad con evolución del sistema
11.1 La arquitectura debe permitir agregar nuevas tablas fácilmente a medida que el sistema evoluciona.  
11.2 No debe requerirse modificar código de validación cada vez que se agrega una nueva entidad con adjuntos.  
11.3 La lista blanca debe ser el único punto de configuración necesario.

### 12. Documentación de tablas autorizadas
12.1 El sistema debe mantener documentación actualizada de:
- Qué tablas están autorizadas.
- Qué tipo de adjuntos se asocian típicamente a cada tabla.
- Reglas de negocio específicas por tabla.

12.2 Esta documentación debe estar accesible para desarrolladores y administradores.

### 13. Validación en migraciones de datos
13.1 Al migrar datos de sistemas legacy, debe validarse que todos los `relatedtable` existentes estén autorizados.  
13.2 Si se encuentran valores no autorizados, debe decidirse:
- Agregar las tablas a la lista autorizada.
- Corregir los datos erróneos.
- Registrar excepciones históricas.

13.3 No deben migrarse datos con referencias inválidas.

### 14. Pruebas automatizadas
14.1 El sistema debe incluir pruebas que verifiquen:
- Rechazo de tablas no autorizadas.
- Aceptación de todas las tablas en la lista blanca.
- Funcionamiento correcto al agregar/inactivar tablas.
- Consistencia entre esquemas si hay múltiples.

14.2 Las pruebas deben ejecutarse en cada despliegue.

### 15. Manejo de casos especiales
15.1 Puede definirse un rol de **superadministrador** que pueda asociar adjuntos a cualquier tabla bajo su responsabilidad.  
15.2 Estas operaciones excepcionales deben quedar claramente auditadas con justificación.  
15.3 Debe documentarse el riesgo de eludir las restricciones.

---

### Resultado esperado

Un **sistema de restricción robusto** que limita las asociaciones de adjuntos únicamente a tablas autorizadas y validadas, previniendo errores de configuración, garantizando integridad estructural, facilitando el mantenimiento del sistema y permitiendo evolución controlada de la arquitectura de datos del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-115.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-115.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-115.png)
