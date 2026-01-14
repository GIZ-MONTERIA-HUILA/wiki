# Épica: Gestión territorial de la acción (municipios)

## 1. Descripción general
Esta épica aborda la **gestión del alcance territorial de las acciones del PIGCCT**, permitiendo definir, registrar y consultar los municipios y/o la cobertura departamental en los que se implementa cada acción. La correcta delimitación territorial es clave para el análisis espacial del plan, la coherencia con el PIGCCT asociado y la posterior desagregación de resultados a nivel municipal y departamental.

## 2. Objetivo
Permitir al sistema registrar de manera consistente y validada el alcance territorial de cada acción del PIGCCT, asegurando coherencia con el departamento del plan, trazabilidad municipal y disponibilidad de información territorial para análisis, seguimiento y reportes.

## 3. Justificación / Valor de negocio
La gestión territorial de las acciones:
- Permite identificar con precisión dónde se implementan las intervenciones climáticas.
- Facilita análisis comparativos entre municipios y a nivel departamental.
- Mejora la planeación territorial y la focalización de esfuerzos.
- Fortalece la articulación entre gestión climática y ordenamiento territorial.
- Proporciona insumos clave para reportes territoriales y tableros geográficos.

## 4. Alcance
Incluye:
- Definición del alcance territorial de la acción (municipal o departamental).
- Selección del departamento de referencia (asociado al PIGCCT).
- Selección múltiple de municipios dentro del departamento.
- Opción de cobertura total del departamento.
- Registro de la relación acción–municipio.
- Identificación explícita de acciones con cobertura departamental.
- Validaciones de coherencia territorial e integridad del modelo.
- Consulta y visualización de la cobertura territorial de las acciones.
- Uso de la información territorial en análisis de seguimiento y reportes.

No incluye:
- Análisis geoespacial avanzado (cubierto en módulos o herramientas externas).

## 5. Actores / Roles
- **Usuario del sistema**: Define y consulta el alcance territorial de las acciones.
- **Administrador del sistema**: Configura y valida reglas territoriales.
- **Sistema**: Aplica validaciones de coherencia, evita duplicidades y garantiza integridad referencial.

## 6. Historias de usuario asociadas
- [**HU-PIGCCT-SYM-082**: Seleccionar alcance territorial de la acción.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-082/HU-PIGCCT-SYM-082.md)   
- [**HU-PIGCCT-SYM-083**: Seleccionar departamento de referencia.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-083/HU-PIGCCT-SYM-083.md)     
- [**HU-PIGCCT-SYM-084**: Seleccionar uno o varios municipios.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-084/HU-PIGCCT-SYM-084.md)     
- [**HU-PIGCCT-SYM-085**: Seleccionar todo el departamento.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-085/HU-PIGCCT-SYM-085.md)    
- [**HU-PIGCCT-SYM-086**: Registrar relación acción–municipio.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-086/HU-PIGCCT-SYM-086.md)     
- [**HU-PIGCCT-SYM-087**: Registrar cobertura departamental.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-087/HU-PIGCCT-SYM-087.md)     
- [**HU-PIGCCT-SYM-088**: Validar coherencia con el PIGCCT.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-088/HU-PIGCCT-SYM-088.md)     
- [**HU-PIGCCT-SYM-089**: Evitar duplicidad de municipios.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-089/HU-PIGCCT-SYM-089.md)     
- [**HU-PIGCCT-SYM-090**: Consultar cobertura territorial de la acción.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-090/HU-PIGCCT-SYM-090.md)     
- [**HU-PIGCCT-SYM-091**: Identificar acciones de cobertura departamental.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-091/HU-PIGCCT-SYM-091.md)     
- [**HU-PIGCCT-SYM-092**: Usar cobertura territorial en análisis de seguimiento.](/content/epicas/EP-PIGCCT-SYM-006/historias_usuario/HU-PIGCCT-SYM-092/HU-PIGCCT-SYM-092.md)   

## 7. Criterios de éxito
- Cada acción tiene un alcance territorial claramente definido.
- No existen acciones asociadas a municipios fuera del departamento del PIGCCT.
- Las acciones con cobertura total del departamento son identificables fácilmente.
- No se presentan duplicidades en la relación acción–municipio.
- La información territorial es utilizable en análisis y reportes.

## 8. Dependencias y supuestos
**Dependencias**
- Catálogo oficial de departamentos y municipios actualizado.
- Existencia de acciones previamente registradas y asociadas a un PIGCCT.

**Supuestos**
- La división político-administrativa no cambia durante el período de seguimiento.
- El nivel municipal es suficiente para el análisis territorial requerido.

## 9. Riesgos
- Definiciones ambiguas del alcance territorial de las acciones.
- Errores en la selección de municipios por parte del usuario.
- Dificultad para analizar acciones con cobertura parcial vs. total.
- Cambios administrativos futuros que requieran ajustes en el modelo territorial.

## 10. Estado y seguimiento
- **Estado actual**: En definición
- **Indicadores de seguimiento**:
  - Número de acciones con cobertura municipal vs. departamental.
  - Distribución de acciones por municipio.
  - Porcentaje de acciones con información territorial completa.
