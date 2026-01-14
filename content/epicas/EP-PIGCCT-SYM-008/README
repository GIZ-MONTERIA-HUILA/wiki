# Épica: Gestión de adjuntos y evidencias del PIGCCT

## 1. Descripción general
Esta épica aborda la **gestión integral de adjuntos y evidencias** asociados a los registros del Plan Integral de Gestión del Cambio Climático Territorial (PIGCCT), permitiendo cargar, asociar, validar, consultar y administrar archivos que respalden la formulación, ejecución y seguimiento de las acciones del plan. El sistema garantiza trazabilidad, control y consistencia de la información documental y geoespacial.

## 2. Objetivo
Permitir al sistema registrar, administrar y consultar archivos adjuntos asociados a los distintos registros del PIGCCT, asegurando que la evidencia documental y técnica esté correctamente relacionada, validada y disponible para consulta, auditoría y seguimiento.

## 3. Justificación / Valor de negocio
La gestión estructurada de adjuntos y evidencias:
- Fortalece la trazabilidad y respaldo técnico de las acciones del PIGCCT.
- Permite documentar de forma ordenada la formulación, ejecución y cierre de acciones.
- Facilita procesos de seguimiento, evaluación, auditoría y control.
- Garantiza consistencia y seguridad en el manejo de archivos.
- Soporta evidencias documentales, gráficas y geoespaciales del plan.

## 4. Alcance
Incluye:
- Carga de archivos adjuntos asociados a registros del sistema.
- Registro de metadatos del archivo (nombre, tipo, tamaño, ruta, fechas).
- Asociación de uno o varios adjuntos a una acción del PIGCCT.
- Validación de tamaño máximo configurable por parámetro del sistema.
- Validación de formatos de archivo permitidos.
- Edición de la descripción del adjunto.
- Actualización automática de la fecha de modificación.
- Activación e inactivación lógica de adjuntos.
- Listado y consulta de adjuntos asociados a un registro.
- Descarga de archivos adjuntos.
- Validación de la existencia del registro relacionado.
- Restricción de tipos de relación permitidos.
- Trazabilidad por esquema, módulo o ambiente mediante `relatedschema`.

No incluye:
- Versionamiento avanzado de documentos.
- Edición del contenido interno de los archivos.
- Gestión de repositorios documentales externos.

## 5. Actores / Roles
- **Usuario del sistema**: Carga, consulta y descarga adjuntos asociados a registros.
- **Administrador del sistema**: Gestiona la activación/inactivación de adjuntos y controla parámetros de validación.
- **Sistema**: Valida reglas, mantiene integridad referencial y asegura trazabilidad de los adjuntos.

## 6. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-105**: Cargar adjunto asociado a un registro.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-105/HU-PIGCCT-SYM-105.md)   
- [**HU-PIGCCT-SYM-106**: Asociar adjunto a una acción.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-106/HU-PIGCCT-SYM-106.md)     
- [**HU-PIGCCT-SYM-107**: Validar tamaño máximo del archivo.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-107/HU-PIGCCT-SYM-107.md)     
- [**HU-PIGCCT-SYM-108**: Validar formato del archivo.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-108/HU-PIGCCT-SYM-108.md)     
- [**HU-PIGCCT-SYM-109**: Editar descripción del adjunto.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-109/HU-PIGCCT-SYM-109.md)     
- [**HU-PIGCCT-SYM-110**: Actualizar fecha de modificación.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-110/HU-PIGCCT-SYM-110.md)     
- [**HU-PIGCCT-SYM-111**: Activar o inactivar adjunto.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-111/HU-PIGCCT-SYM-111.md)     
- [**HU-PIGCCT-SYM-112**: Listar adjuntos de un registro.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-112/HU-PIGCCT-SYM-112.md)     
- [**HU-PIGCCT-SYM-113**: Descargar adjunto.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-113/HU-PIGCCT-SYM-113.md)     
- [**HU-PIGCCT-SYM-114**: Validar existencia del registro relacionado.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-114/HU-PIGCCT-SYM-114.md)     
- [**HU-PIGCCT-SYM-115**: Restringir tipos de relación.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-115/HU-PIGCCT-SYM-115.md)     
- [**HU-PIGCCT-SYM-116**: Trazabilidad por esquema.](/content/epicas/EP-PIGCCT-SYM-008/historias_usuario/HU-PIGCCT-SYM-116/HU-PIGCCT-SYM-116.md)   

## 7. Criterios de éxito
- Todos los adjuntos están correctamente asociados a registros existentes.
- No existen adjuntos huérfanos en el sistema.
- Los archivos cumplen las validaciones de tamaño y formato.
- Es posible consultar y descargar los adjuntos asociados a una acción.
- Se mantiene trazabilidad completa de creación y modificación.
- La activación/inactivación no elimina información histórica.

## 8. Dependencias y supuestos
**Dependencias**
- Existencia previa de registros del PIGCCT (acciones u otros).
- Definición de parámetros del sistema para tamaño máximo y formatos permitidos.

**Supuestos**
- Los usuarios cargan archivos relevantes y veraces.
- El almacenamiento de archivos está correctamente configurado y disponible.
- Los esquemas y módulos están claramente definidos para el uso de `relatedschema`.

## 9. Riesgos
- Carga de archivos irrelevantes o de baja calidad técnica.
- Uso excesivo de almacenamiento por mala configuración de tamaños máximos.
- Asociación incorrecta de adjuntos a registros equivocados.
- Falta de criterios claros para activar o inactivar evidencias.

## 10. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de acciones con evidencias adjuntas.
  - Promedio de adjuntos por acción.
  - Porcentaje de adjuntos activos vs. inactivos.
  - Distribución de adjuntos por tipo de archivo.
