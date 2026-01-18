# Épica: Administración de la tabla maestra de PIGCCT

## 1. Descripción general
Esta épica define la **administración de la tabla maestra de PIGCCT**, como el componente central para la gestión estructural y administrativa de los Planes Integrales de Gestión del Cambio Climático Territorial dentro del sistema.

La tabla maestra de PIGCCT constituye el eje de referencia para la asociación de acciones, indicadores, reportes y procesos de seguimiento, garantizando la integridad, trazabilidad y coherencia de la información territorial y temporal de los planes.

## 2. Objetivo
Disponer de un módulo administrativo que permita crear, consultar, actualizar, activar, inactivar y mantener el historial de los PIGCCT, asegurando unicidad por departamento y año, integridad referencial y disponibilidad del plan para su uso transversal en los demás módulos del sistema.

## 3. Justificación / Valor de negocio
La administración centralizada del PIGCCT:
- Garantiza la consistencia y unicidad de los planes territoriales.
- Evita duplicidad de información por departamento y vigencia.
- Permite una gestión ordenada del ciclo de vida del PIGCCT.
- Facilita el análisis histórico y comparativo entre planes.
- Asegura que los demás módulos trabajen sobre planes válidos y vigentes.
- Reduce errores administrativos y fortalece la gobernanza de la información.

## 4. Alcance
Incluye:
- Registro de nuevos PIGCCT.
- Validación de unicidad por departamento y año.
- Consulta y listado de PIGCCT.
- Filtros por departamento y estado.
- Edición de información administrativa del PIGCCT.
- Activación e inactivación de planes.
- Conservación y consulta del historial de PIGCCT.
- Relación con el catálogo oficial de departamentos.
- Disponibilidad del PIGCCT para su uso en otros módulos del sistema.

No incluye:
- Definición de acciones, indicadores o proyectos del PIGCCT.
- Procesos de validación técnica del contenido del plan.
- Análisis territorial o geográfico del PIGCCT.
- Eliminación física de registros históricos.
- Administración del catálogo de departamentos.

## 5. Actores / Roles
- **Administrador del sistema**: Crea, edita, activa, inactiva y gestiona el ciclo de vida del PIGCCT.
- **Usuario del sistema**: Consulta y filtra los PIGCCT registrados.
- **Usuarios de otros módulos**: Seleccionan el PIGCCT para asociar acciones, indicadores y reportes.
- **Sistema**: Valida unicidad, controla estados, asegura integridad referencial y expone el PIGCCT a otros módulos.

## 6. Principios de diseño
- Unicidad del plan por territorio y vigencia.
- Integridad referencial con catálogos oficiales.
- Trazabilidad histórica de los planes.
- No eliminación de información histórica.
- Simplicidad y claridad administrativa.
- Uso transversal del PIGCCT en el sistema.
- Separación entre estado administrativo y contenido del plan.

## 7. Estructura general del módulo
El módulo de administración del PIGCCT se organiza en:

1. Registro y creación de PIGCCT  
2. Validación de unicidad  
3. Listado general de planes  
4. Filtros territoriales y por estado  
5. Edición de información administrativa  
6. Gestión de estados (activo / inactivo)  
7. Consulta de historial de planes  
8. Integración con otros módulos  

## 8. Historias de usuario asociadas
- [**HU-PIGGCT-SYM-001**: Registrar PIGCCT.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-001/HU-PIGCCT-SYM-001.md)  
- [**HU-PIGGCT-SYM-002**: Validar unicidad del PIGCCT por departamento y año.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-002/HU-PIGCCT-SYM-002.md)  
- [**HU-PIGGCT-SYM-003**: Consultar listado de PIGCCT.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-003/HU-PIGCCT-SYM-003.md)    
- [**HU-PIGGCT-SYM-004**: Filtrar PIGCCT por departamento.](/content/epicas/EP-PIGCCT-SYM-00/historias_usuario/HU-PIGCCT-SYM-004/HU-PIGCCT-SYM-004.md)      
- [**HU-PIGGCT-SYM-005**: Filtrar PIGCCT activos.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-005/HU-PIGCCT-SYM-005.md)      
- [**HU-PIGGCT-SYM-006**: Editar información del PIGCCT.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-006/HU-PIGCCT-SYM-006.md)      
- [**HU-PIGGCT-SYM-007**: Actualizar estado del PIGCCT.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-007/HU-PIGCCT-SYM-007.md)      
- [**HU-PIGGCT-SYM-008**: Inactivar PIGCCT.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-008/HU-PIGCCT-SYM-008.md)      
- [**HU-PIGGCT-SYM-009**: Conservar historial de planes.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-009/HU-PIGCCT-SYM-009.md)      
- [**HU-PIGGCT-SYM-010**: Relación con catálogo de departamentos.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-010/HU-PIGCCT-SYM-010.md)      
- [**HU-PIGGCT-SYM-011**: Uso del PIGCCT en otros módulos.](/content/epicas/EP-PIGCCT-SYM-001/historias_usuario/HU-PIGCCT-SYM-011/HU-PIGCCT-SYM-011.md)      

## 9. Reglas funcionales del módulo

### Registro y unicidad
El sistema debe garantizar que no existan dos PIGCCT registrados para el mismo departamento y año, evitando duplicidades desde el momento de la creación.

### Gestión administrativa
El administrador puede actualizar la información descriptiva del PIGCCT sin afectar su trazabilidad ni la información asociada en otros módulos.

### Estados del PIGCCT
El sistema debe permitir activar o inactivar un PIGCCT sin eliminar el registro, asegurando la conservación de información histórica.

### Consulta e historial
Los PIGCCT inactivos deben permanecer disponibles para consulta histórica y análisis comparativo.

### Integración transversal
Solo PIGCCT válidos y registrados deben poder ser seleccionados desde otros módulos del sistema.

## 10. Criterios de éxito
- No existen PIGCCT duplicados por departamento y año.
- Los planes pueden activarse e inactivarse sin pérdida de información.
- El listado y los filtros funcionan correctamente.
- Los PIGCCT históricos permanecen accesibles.
- Otros módulos pueden consumir el PIGCCT sin inconsistencias.
- Se mantiene la integridad referencial con departamentos.

## 11. Dependencias y supuestos

**Dependencias**
- Catálogo oficial y actualizado de departamentos.
- Definición clara de vigencias y periodos del PIGCCT.
- Integración con módulos de acciones, indicadores y reportes.
- Roles y permisos correctamente configurados.

**Supuestos**
- Cada departamento puede tener múltiples PIGCCT en distintos años.
- El PIGCCT es la entidad base del sistema.
- No se permite la eliminación física de planes.
- Los usuarios comprenden la diferencia entre activo e inactivo.

## 12. Riesgos
- Registro incorrecto de vigencias o departamentos.
- Uso de PIGCCT inactivos en módulos operativos.
- Errores de integridad referencial.
- Falta de claridad en la gestión de estados.
- Dependencia de datos administrativos incompletos.

## 13. Estado y seguimiento
- **Estado actual**: En definición 
- **Indicadores de seguimiento**:
  - Número de PIGCCT registrados.
  - Cantidad de planes activos vs inactivos.
  - Incidentes de duplicidad detectados.
  - Uso del PIGCCT en otros módulos.
  - Consultas a historial de planes.