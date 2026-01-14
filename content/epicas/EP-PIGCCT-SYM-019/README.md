# Épica: Formulario de Registro y Gestión de Acciones del PIGCCT

## 1. Descripción general
Esta épica define el **formulario integral para el registro y gestión de acciones del PIGCCT**, como el componente central mediante el cual las entidades registran, organizan y estructuran la información de los proyectos territoriales. El formulario está diseñado bajo un enfoque guiado por pestañas, con validaciones en tiempo real y guardado progresivo, asegurando consistencia, usabilidad y control según el rol del usuario, la etapa del proceso y el estado de validación.

## 2. Objetivo
Disponer de un formulario estructurado, intuitivo y robusto que permita registrar y gestionar acciones del PIGCCT de manera progresiva, garantizando que la información sea completa, coherente y organizada antes de su envío a los procesos de validación institucional.

## 3. Justificación / Valor de negocio
El formulario de registro:
- Facilita el diligenciamiento de acciones complejas de carácter territorial.
- Reduce errores mediante validaciones tempranas y controladas.
- Permite el guardado progresivo sin pérdida de información.
- Mejora la experiencia de usuario con un flujo guiado y predecible.
- Garantiza coherencia entre información general, territorial, programática e indicadores.
- Aumenta la calidad y confiabilidad de los datos usados para seguimiento y reporte del PIGCCT.

## 4. Alcance
Incluye:
- Diseño del formulario basado en pestañas (tabs).
- Validaciones en tiempo real para campos críticos.
- Guardado progresivo de la información.
- Habilitación y bloqueo de campos según rol, etapa del proceso y estado de validación.
- Registro de información general, territorial y programática.
- Asociación de indicadores y registro de valores proyectados.
- Gestión de adjuntos como evidencia de la acción.
- Visualización de estado, campos obligatorios y errores.

No incluye:
- El envío a validación institucional.
- Las reglas de estado derivado.
- El bloqueo de edición posterior al envío.
- La gestión de eventos y auditoría.
- La lógica de validación institucional.

## 5. Actores / Roles
- **Usuario registrador**: Diligencia y actualiza la información de la acción.
- **Usuario administrador**: Gestiona configuraciones específicas del formulario.
- **Sistema**: Aplica validaciones, controla la habilitación de campos y soporta el flujo guiado.

## 6. Principios de diseño del formulario
- Formulario guiado por pestañas (tabs).
- Validaciones en tiempo real.
- Guardado progresivo.
- Campos habilitados o deshabilitados según:
  - Rol del usuario.
  - Etapa del proceso.
  - Estado de validación.
- Indicadores claros y visibles de:
  - Estado de la acción.
  - Campos obligatorios.
  - Errores y advertencias.

## 7. Estructura general del formulario
El formulario se organiza en las siguientes pestañas:

1. Información general  
2. Territorio  
3. Articulación con el plan  
4. Programación y seguimiento  
5. Indicadores asociados  
6. Adjuntos  
7. Estados y validación  

## 8. Historias de usuario asociadas
- **HU-PIGCCT-SYM-163**: Diligenciar información general  
- **HU-PIGCCT-SYM-164**: Definir cobertura territorial  
- **HU-PIGCCT-SYM-165**: Asociar la acción con indicadores  
- **HU-PIGCCT-SYM-166**: Definir programación de la acción  
- **HU-PIGCCT-SYM-167**: Registrar valores proyectados  
- **HU-PIGCCT-SYM-168**: Adjuntar evidencias  

## 9. Reglas funcionales por sección

### Información general
Permite registrar los datos básicos que identifican y caracterizan la acción, necesarios para definir el proyecto territorial. El sistema controla que los campos críticos estén diligenciados antes de permitir el avance en el formulario.

### Territorio
Permite definir el alcance geográfico de la acción, controlando dinámicamente la selección de cobertura territorial para evitar inconsistencias entre departamento y municipios.

### Articulación con el plan
Permite asociar la acción con los componentes estratégicos del PIGCCT mediante flujos guiados y dependientes, asegurando relaciones válidas entre ejes, medidas e indicadores.

### Programación y seguimiento
Permite definir fechas, vigencias, recursos y forma de evaluación de la acción. El sistema valida la coherencia temporal y soporta la generación y recalculo controlado de seguimientos.

### Indicadores asociados
Permite registrar los valores proyectados de los indicadores vinculados a la acción, mediante tablas automáticas con edición controlada y guardado parcial.

### Adjuntos
Permite cargar y gestionar documentos que respaldan la información registrada, con controles claros para su administración.

### Estados y validación
Permite visualizar el estado actual de la acción dentro del proceso institucional, sin habilitar directamente acciones de validación.

## 10. Criterios de éxito
- El formulario guía correctamente al usuario a través de todas las secciones.
- No se permite avanzar con información crítica incompleta.
- La información se guarda de forma progresiva sin pérdida de datos.
- Las validaciones previenen errores funcionales y territoriales.
- El estado de la acción es visible y comprensible.

## 11. Dependencias y supuestos
**Dependencias**
- Disponibilidad de catálogos y estructuras del PIGCCT.
- Definición previa de campos críticos y reglas de validación.
- Integración con modelos territoriales e indicadores.

**Supuestos**
- El formulario es el único medio de registro de acciones.
- Los usuarios siguen el flujo definido por pestañas.
- Las validaciones cubren los principales escenarios de error.
- El sistema mantiene coherencia entre la interfaz y el modelo de datos.

## 12. Riesgos
- Complejidad excesiva del formulario.
- Sobrecarga de validaciones que afecte la usabilidad.
- Mensajes de error poco claros para el usuario.
- Dependencia de catálogos externos no actualizados.
- Abandono del registro por flujos poco intuitivos.

## 13. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Tiempo promedio de diligenciamiento de una acción.
  - Porcentaje de acciones completadas sin errores.
  - Número de correcciones requeridas antes del envío a validación.
