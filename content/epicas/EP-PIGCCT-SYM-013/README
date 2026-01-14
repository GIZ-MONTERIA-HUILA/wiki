# Épica: Asociación de indicadores y adjuntos

## 1. Descripción general
Esta épica define las **reglas y comportamientos para la asociación de indicadores y la gestión de adjuntos** dentro del formulario de acciones del PIGCCT. Su propósito es garantizar que dichas asociaciones se realicen únicamente cuando exista una acción válida, permitiendo el trabajo en estado borrador y asegurando la trazabilidad de todos los cambios mediante el registro de eventos en tablas relacionales.

## 2. Objetivo
Permitir que el usuario registrador asocie indicadores y adjunte evidencias a una acción del PIGCCT de forma controlada y progresiva, asegurando consistencia en las relaciones, flexibilidad en el trabajo en borrador y trazabilidad de los cambios previos a la validación.

## 3. Justificación / Valor de negocio
La asociación controlada de indicadores y adjuntos:
- Garantiza la integridad referencial entre acciones, indicadores y evidencias.
- Permite la construcción progresiva de la información sin forzar validaciones tempranas.
- Facilita la revisión y ajuste previo a la aprobación institucional.
- Asegura trazabilidad completa de los cambios mediante eventos.
- Reduce errores derivados de relaciones incompletas o inconsistentes.

## 4. Alcance
Incluye:
- Asociación de indicadores únicamente a acciones previamente guardadas.
- Almacenamiento de relaciones acción–indicador en estado borrador.
- Carga de adjuntos en acciones en estado borrador.
- Registro de eventos de creación y actualización asociados a indicadores, seguimientos y adjuntos.
- Soporte a la trazabilidad previa al proceso de validación.

No incluye:
- Reglas de validación o aprobación de indicadores.
- Cálculo, agregación o evaluación de indicadores.
- Versionado avanzado de adjuntos.
- Flujos de validación institucional (cubiertos por otra épica).

## 5. Actores / Roles
- **Usuario registrador**: Asocia indicadores, carga adjuntos y ajusta información en estado borrador.
- **Usuario validador**: Consulta indicadores y adjuntos asociados durante la validación.
- **Sistema**: Controla la existencia de la acción, la integridad de las relaciones y la generación de eventos.

## 6. Historias de usuario asociadas
- **HU-PIGCCT-SYM-147**: Asociar indicadores solo después de guardar la acción.  
- **HU-PIGGCT-SYM-148**: Guardar indicadores asociados en estado borrador.  
- **HU-PIGCCT-SYM-149**: Adjuntar archivos en estado borrador.  
- **HU-PIGCCT-SYM-150**: Registrar eventos en tablas relacionales.

## 7. Reglas de asociación y adjuntos

### 7.1 Asociación de indicadores
Permite:
- Asociar indicadores únicamente cuando la acción ya cuenta con un identificador válido.
- Guardar relaciones acción–indicador sin enviarlas a validación.
- Editar o ajustar indicadores mientras la acción esté en estado borrador.
- Mantener consistencia en las relaciones del modelo de datos.

### 7.2 Gestión de adjuntos en borrador
Permite:
- Cargar archivos asociados a una acción en estado borrador.
- Construir progresivamente la evidencia del proyecto.
- Mantener los adjuntos editables antes del envío a validación.
- Asociar los adjuntos a la acción correspondiente de forma trazable.

### 7.3 Registro de eventos
Permite:
- Generar eventos de tipo `create` o `update` para:
  - Indicadores asociados.
  - Registros de seguimiento.
  - Adjuntos.
- Almacenar los eventos en tablas relacionales.
- Utilizar estos eventos posteriormente en el proceso de validación.

## 8. Criterios de éxito
- No es posible asociar indicadores ni adjuntos sin una acción previamente guardada.
- Las relaciones acción–indicador pueden mantenerse en estado borrador.
- Los adjuntos pueden cargarse y modificarse antes del envío a validación.
- Cada creación o actualización genera un evento trazable.
- Los eventos en borrador no ingresan al flujo de validación.

## 9. Dependencias y supuestos
**Dependencias**
- Existencia del modelo de datos de acción, indicador y adjuntos.
- Definición clara de estados de la acción (borrador, enviado, validado).
- Integración con la épica de gestión de eventos y validación.

**Supuestos**
- La acción debe existir antes de crear relaciones.
- El usuario registrador conoce el flujo de trabajo en estado borrador.
- El sistema controla la integridad referencial y los permisos de edición.

## 10. Riesgos
- Intentos de asociación sin acción válida.
- Inconsistencias si los eventos no se registran correctamente.
- Acumulación de indicadores o adjuntos no enviados a validación.
- Dependencia estricta del estado borrador para permitir edición.

## 11. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de indicadores asociados en estado borrador.
  - Cantidad de adjuntos cargados antes de validación.
  - Número de eventos generados por acción.
  - Tiempo promedio entre asociación y envío a validación.
