# Épica: Gestión de eventos y validación de información del PIGCCT

## 1. Descripción general
Esta épica aborda la **gestión de eventos y el proceso de validación institucional de la información** registrada en el PIGCCT. Permite controlar, auditar y validar los cambios realizados por usuarios no administradores sobre los registros del sistema, garantizando que solo la información aprobada por los roles correspondientes sea visible y utilizada para análisis, seguimiento y toma de decisiones.

El modelo se basa en la generación automática de eventos ante operaciones de creación y actualización, y en un flujo de validación escalonado por entidad y por la CAR.

## 2. Objetivo
Permitir al sistema registrar eventos asociados a la creación y modificación de información, gestionar su validación por distintos niveles institucionales y asegurar que únicamente los registros validados sean visibles y utilizables dentro del PIGCCT.

## 3. Justificación / Valor de negocio
La gestión de eventos y validación:
- Garantiza la calidad, integridad y confiabilidad de la información del PIGCCT.
- Asegura control institucional sobre los datos registrados.
- Permite trazabilidad completa de quién, cuándo y cómo se modificó la información.
- Facilita auditorías, revisiones técnicas y procesos de control.
- Evita el uso de información no validada en análisis y reportes oficiales.

## 4. Alcance
Incluye:
- Generación automática de eventos al crear registros por usuarios no administradores.
- Generación de eventos al actualizar registros existentes.
- Registro de eventos con referencia a la acción como objeto principal.
- Manejo de eventos en tablas dependientes manteniendo el contexto de la acción.
- Envío de eventos a validación.
- Validación por parte de la entidad responsable.
- Validación posterior por parte de la CAR.
- Control de visibilidad de registros según estado de validación.
- Visualización de registros pendientes por parte de usuarios involucrados.
- Bloqueo de edición directa de registros ya validados.
- Consulta del historial de eventos asociados a una acción.
- Comparación entre valores anteriores y nuevos durante la validación.

Aplica a las siguientes tablas:
- acción  
- indicador_accion  
- indicador_accion_valor  
- adjuntos  

No incluye:
- Flujos de validación externos al sistema.
- Aprobaciones automáticas sin intervención humana.
- Versionamiento histórico completo de registros (más allá del evento).

## 5. Actores / Roles
- **Usuario del sistema (registrador)**: Crea y actualiza información y envía eventos a validación.
- **Validador de entidad**: Revisa, valida o rechaza eventos en primera instancia.
- **Validador CAR**: Realiza la validación final de la información aprobada por la entidad.
- **Administrador del sistema**: Supervisa el proceso y define reglas de control.
- **Sistema**: Genera eventos, controla estados, bloquea ediciones y mantiene trazabilidad.

## 6. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-117**: Generar evento al crear un registro.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-117/HU-PIGCCT-SYM-117.md)     
- [**HU-PIGCCT-SYM-118**: Generar evento al actualizar un registro.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-118/HU-PIGCCT-SYM-118.md)       
- [**HU-PIGCCT-SYM-119**: Registrar evento con referencia a objeto principal.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-119/HU-PIGCCT-SYM-119.md)       
- [**HU-PIGCCT-SYM-120**: Registrar evento para tablas dependientes.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-120/HU-PIGCCT-SYM-120.md)       
- [**HU-PIGCCT-SYM-121**: Enviar evento a validación.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-121/HU-PIGCCT-SYM-121.md)       
- [**HU-PIGCCT-SYM-122**: Validar evento por la entidad.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-122/HU-PIGCCT-SYM-122.md)       
- [**HU-PIGCCT-SYM-123**: Validar evento por la CAR.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-123/HU-PIGCCT-SYM-123.md)       
- [**HU-PIGCCT-SYM-124**: Condicionar visualización por validación.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-124/HU-PIGCCT-SYM-124.md)       
- [**HU-PIGCCT-SYM-125**: Visualizar registros en estado pendiente.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-125/HU-PIGCCT-SYM-125.md)       
- [**HU-PIGCCT-SYM-126**: Bloquear edición de registros validados.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-126/HU-PIGCCT-SYM-126.md)       
- [**HU-PIGCCT-SYM-127**: Consultar historial de eventos.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-127/HU-PIGCCT-SYM-127.md)       
- [**HU-PIGCCT-SYM-128**: Comparar valor anterior y nuevo.](/content/epicas/EP-PIGCCT-SYM-009/historias_usuario/HU-PIGCCT-SYM-128/HU-PIGCCT-SYM-128.md)     

## 7. Criterios de éxito
- Todos los cambios realizados por usuarios no administradores generan eventos.
- Ningún registro no validado es visible o utilizable en el sistema.
- El flujo de validación por entidad y CAR se cumple de forma secuencial.
- Los registros validados no pueden ser editados directamente.
- Existe trazabilidad completa de los cambios realizados.
- Los validadores pueden comparar valores anteriores y nuevos.

## 8. Dependencias y supuestos
**Dependencias**
- Existencia de acciones registradas en el sistema.
- Definición clara de roles de validación (entidad y CAR).
- Configuración de estados del registro y del evento.

**Supuestos**
- Los validadores cuentan con criterios técnicos claros para aprobar o rechazar información.
- Los eventos representan fielmente los cambios realizados.
- El sistema mantiene consistencia entre tablas principales y dependientes.

## 9. Riesgos
- Retrasos en la validación que limiten la disponibilidad de información.
- Sobrecarga de eventos en acciones con múltiples actualizaciones.
- Falta de claridad en los criterios de validación.
- Uso indebido de información pendiente si falla el control de visibilidad.

## 10. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de eventos generados por tipo (create / update).
  - Tiempo promedio de validación por entidad y CAR.
  - Porcentaje de registros validados vs. pendientes.
  - Número de eventos rechazados por inconsistencias.
