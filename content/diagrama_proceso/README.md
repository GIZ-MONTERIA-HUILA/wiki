[Inicio](/README.md)

# Alcance general del proceso – Diagrama de proceso PIGCCT

El diagrama de proceso del **Sistema de Monitoreo y Seguimiento de los PIGCCT** representa de manera integral el ciclo de vida de la información asociada a la planeación, implementación, seguimiento, validación y análisis de los **Planes Integrales de Gestión del Cambio Climático Territoriales (PIGCCT)**, desde su configuración administrativa inicial hasta su visualización territorial, generación de reportes y consulta pública.

El proceso está diseñado bajo principios de **integridad de la información, trazabilidad, control institucional, validación multinivel y enfoque territorial**, garantizando que los datos utilizados para la toma de decisiones sean consistentes, auditables y alineados con los marcos normativos nacionales.

---

<img src="assets/bpmn.png" class="zoomable" />

## 1. Configuración y administración estructural del PIGCCT

El proceso inicia con la **administración de la tabla maestra del PIGCCT**, donde el administrador del sistema registra los planes asociados a los departamentos, asegurando:

- Unicidad por departamento y año.
- Relación válida con el catálogo nacional de departamentos.
- Gestión de estados activos e inactivos sin pérdida de información histórica.

A partir del PIGCCT, se estructura jerárquicamente el plan mediante:

- **Ejes** (estratégicos y transversales),
- **Medidas** (líneas estratégicas, líneas de acción y medidas),
- **Indicadores**, que permiten medir productos, gestión e impactos.

Cada nivel mantiene integridad referencial con el nivel superior, y puede ser activado o inactivado conservando trazabilidad histórica.

---

## 2. Alineación estratégica y catálogos transversales

Las medidas del PIGCCT se alinean estratégicamente mediante relaciones N:M con catálogos maestros como:

- Medios de implementación,
- Líneas estratégicas e instrumentales del PNCC,
- Enfoques diferenciales,
- Dimensiones,
- Objetivos de Desarrollo Sostenible (ODS).

Este componente permite analizar la coherencia del PIGCCT con políticas nacionales, agendas internacionales y enfoques transversales, habilitando filtros y análisis estratégicos posteriores.

---

## 3. Registro y gestión de acciones territoriales

Sobre la estructura del plan, los usuarios registradores crean **acciones territoriales**, que representan proyectos o intervenciones concretas en el territorio. El proceso incluye:

- Registro de información general, financiera y programática.
- Definición de cobertura territorial (municipios específicos o todo el departamento).
- Asociación jerárquica guiada a ejes, medidas e indicadores.
- Definición de vigencias y periodicidad de evaluación.

El sistema genera automáticamente los **seguimientos programados** por indicador, garantizando consistencia entre planeación y monitoreo.

---

## 4. Seguimiento, programación y control de avances

Cada acción genera registros de seguimiento según la frecuencia y vigencias definidas. El proceso distingue claramente entre:

- **Valores proyectados** (planeación),
- **Valores ejecutados** (avance real).

El sistema controla:

- La coherencia temporal y numérica de los valores,
- La edición de campos según la etapa del proceso,
- El cálculo de avances por acción e indicador.

Este diseño permite un monitoreo progresivo, estructurado y comparable en el tiempo.

---

## 5. Gestión de adjuntos y evidencias

El proceso incorpora un módulo transversal de **gestión documental**, que permite asociar evidencias a acciones y sus componentes, asegurando:

- Validación de formatos y tamaños,
- Relación explícita con el esquema, tabla y registro correspondiente,
- Activación e inactivación de adjuntos sin pérdida histórica,
- Descarga y consulta controlada según rol.

---

## 6. Flujo de eventos y validación institucional

Uno de los ejes centrales del proceso es el **modelo de eventos**, que garantiza trazabilidad y control institucional.  
Cada creación o modificación relevante genera un evento que:

- Registra valores anteriores y nuevos,
- Se asocia siempre a la acción como objeto principal,
- Inicia un flujo de validación secuencial.

El proceso de validación contempla:

1. **Validación por la entidad responsable**,
2. **Validación por la CAR**,  
   asegurando doble control antes de que la información sea visible y usable en el sistema.

Los registros validados quedan bloqueados para edición directa; cualquier cambio genera un nuevo evento y reinicia el ciclo de validación.

---

## 7. Control de acceso, roles y visibilidad

El proceso está gobernado por un esquema de **roles y permisos**, gestionado mediante autenticación y autorización:

- Registradores,
- Validadores de entidad,
- Validadores CAR,
- Administradores,
- Usuarios de consulta,
- Consulta pública sin autenticación.

La visibilidad de la información depende del rol y del estado de validación, garantizando que solo información aprobada sea utilizada para análisis, reportes y visualización pública.

---

## 8. Navegación, formularios y experiencia de usuario

El diagrama incorpora la lógica de interacción del usuario mediante:

- Formularios guiados por pestañas,
- Guardado progresivo y validaciones en tiempo real,
- Habilitación dinámica de secciones según estado y rol,
- Botones globales de acción (guardar, enviar, cancelar).

Este enfoque reduce errores, mejora la calidad de los datos y facilita la adopción institucional del sistema.

---

## 9. Análisis territorial, visor geográfico y estadísticas

La información validada alimenta el **visor geográfico del PIGCCT**, permitiendo:

- Visualizar acciones por municipio o cobertura departamental,
- Aplicar filtros temáticos, territoriales y temporales,
- Analizar avances mediante mapas, gráficos y tableros sincronizados.

El proceso soporta tanto análisis internos como visualización pública de información agregada y validada.

---

## 10. Reportes, tableros y consulta pública

Finalmente, el proceso culmina en la generación de:

- Tableros de control adaptados por rol,
- Reportes territoriales, estratégicos y comparativos,
- Exportación en formatos PDF y Excel,
- Consulta pública transparente de información agregada.

---

## Síntesis del alcance

En conjunto, el diagrama de proceso describe un **flujo integral, modular y trazable**, que cubre:

- La estructuración del PIGCCT,
- La gestión operativa de acciones,
- El seguimiento técnico de indicadores,
- La validación institucional multinivel,
- La visualización territorial y rendición de cuentas.

Este proceso garantiza que el Sistema PIGCCT sea una herramienta confiable para la planeación, el monitoreo y la evaluación de las acciones de cambio climático a nivel territorial.
