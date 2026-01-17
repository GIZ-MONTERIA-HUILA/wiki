# HU-PIGCCT-SYM-158  
## Épica: Estado y validación (visualización)  
### Visualizar observaciones de validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** ver las observaciones realizadas por los validadores.  
> **Para:** corregir oportunamente la información y volver a enviar la acción a validación.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Ubicación de las observaciones
1.1 Las observaciones deben mostrarse en múltiples lugares:
- **Panel destacado** en la parte superior del formulario cuando se abre una acción rechazada
- **Pestaña "Estado"** del formulario con todas las observaciones
- **Notificación** al momento del rechazo
- **Listado de acciones**: Indicador de que hay observaciones pendientes

1.2 Las observaciones deben ser fácilmente accesibles y visibles.

### 2. Panel de observaciones en acción rechazada
2.1 Al abrir una acción rechazada, mostrar panel prominente:
```
⚠️ Esta acción fue rechazada y requiere correcciones

Rechazada por: María García (Validadora de Entidad)
Fecha de rechazo: 17/01/2026 09:15

OBSERVACIONES:
[Texto de las observaciones del validador]

Acciones disponibles:
[Botón: Corregir ahora] [Botón: Ver historial completo]
```

2.2 El panel debe ser imposible de ignorar pero no bloquear la vista del formulario.

### 3. Formato de las observaciones
3.1 Las observaciones deben mostrarse con formato claro:
- **Validador**: Nombre completo y rol
- **Fecha y hora**: Timestamp del rechazo
- **Texto de observaciones**: Formateado con párrafos y líneas si es extenso
- **Tipo de rechazo**: General o por campos específicos
- **Prioridad**: Normal, urgente (si aplica)

3.2 Uso de markdown o formato rico para mejorar legibilidad.

### 4. Observaciones generales vs específicas
4.1 Distinguir entre dos tipos de observaciones:
- **Generales**: Aplican a toda la acción
  - Ejemplo: "La acción carece de claridad en sus objetivos generales"
  
- **Por campo específico**: Señalan problemas en campos puntuales
  - Ejemplo: "Campo 'Presupuesto': El monto no es consistente con el alcance"

4.2 Las observaciones específicas deben vincularse visualmente al campo correspondiente.

### 5. Resaltado de campos con observaciones
5.1 Si una observación señala campos específicos, el sistema debe:
- Resaltar el campo con borde rojo o color distintivo
- Mostrar ícono de alerta junto al campo
- Desplegar la observación específica al pasar el cursor o hacer click
- Permitir navegar directamente al campo desde el panel de observaciones

5.2 Ejemplo visual:
```
[Campo: Fecha de inicio] ⚠️
[Observación emergente]: "La fecha es inconsistente con el cronograma"
```

### 6. Lista completa de observaciones en pestaña Estado
6.1 La pestaña "Estado" debe incluir sección dedicada a observaciones:
```
OBSERVACIONES DE VALIDACIÓN

1. Validación por entidad - 17/01/2026
   Validador: María García
   Estado: Rechazado
   
   Observaciones generales:
   - [Texto de observación 1]
   - [Texto de observación 2]
   
   Observaciones por campo:
   - Presupuesto: [observación específica]
   - Cronograma: [observación específica]

2. Validación por CAR - (Pendiente)
   Estado: No enviado aún
```

6.2 Organización clara y cronológica de todas las observaciones.

### 7. Historial de observaciones
7.1 Si una acción fue rechazada múltiples veces, mostrar historial completo:
```
Rechazo 1 - 15/01/2026
Validador: Pedro López
Observaciones: [texto]
Estado: Corregido y reenviado

Rechazo 2 - 17/01/2026 (ACTUAL)
Validador: María García
Observaciones: [texto]
Estado: Pendiente de corrección
```

7.2 Permite ver si hay problemas recurrentes o nuevos.

### 8. Respuestas a observaciones
8.1 El registrador debe poder agregar comentarios o respuestas a cada observación:
- "Corrección realizada: [explicación]"
- "Adjunto nuevo documento de respaldo"
- Marcar observaciones como "Atendida" con checkbox

8.2 Estas respuestas se incluyen en el evento de reenvío.

### 9. Checklist de correcciones
9.1 Convertir observaciones en checklist accionable:
```
Observaciones pendientes de corrección:
☐ Corregir presupuesto según observación de María García
☐ Actualizar cronograma con fechas realistas
☐ Adjuntar documento de respaldo solicitado
☐ Aclarar objetivos específicos de la acción
```

9.2 El usuario puede marcar items completados antes de reenviar.

### 10. Notificación de nuevas observaciones
10.1 Cuando una acción es rechazada, notificar inmediatamente al registrador:
- **Notificación en el sistema**: Badge con contador
- **Correo electrónico**: Con texto completo de observaciones
- **Dashboard**: Resaltar acciones con observaciones pendientes

10.2 Asegurar que el registrador vea las observaciones oportunamente.

### 11. Priorización de observaciones
11.1 Los validadores pueden marcar observaciones como:
- **Crítica**: Debe corregirse obligatoriamente
- **Importante**: Debe atenderse
- **Sugerencia**: Mejora opcional

11.2 El sistema debe mostrar claramente la prioridad con íconos o colores.

### 12. Adjuntos en observaciones
12.1 Los validadores pueden adjuntar archivos o capturas a sus observaciones:
- "Ver archivo de ejemplo correcto"
- "Ver captura de error identificado"

12.2 Los registradores deben poder descargar y ver estos adjuntos.

### 13. Búsqueda y filtrado de observaciones
13.1 Si hay muchas observaciones, proporcionar herramientas de búsqueda:
- Filtrar por: Validador, fecha, prioridad, estado (atendida/pendiente)
- Buscar por texto: "presupuesto"
- Ordenar: Más recientes, más antiguas, por prioridad

13.2 Facilita encontrar observaciones específicas en acciones complejas.

### 14. Exportación de observaciones
14.1 Permitir exportar observaciones a formato imprimible:
- PDF con todas las observaciones
- Incluye: fecha, validador, texto, prioridad
- Útil para trabajo offline o reuniones

14.2 Botón "Exportar observaciones" en la pestaña Estado.

### 15. Indicador de observaciones no leídas
15.1 Marcar observaciones nuevas como "no leídas":
- Badge "Nueva" en observaciones recientes
- Cambiar a "leída" cuando el usuario las visualiza
- Contador: "3 observaciones nuevas"

15.2 Ayuda al usuario a enfocarse en lo nuevo.

### 16. Observaciones por componente
16.1 Organizar observaciones según el componente afectado:
```
Observaciones:
├── Acción principal (2)
│   └── "Falta claridad en objetivos"
│   └── "Presupuesto inconsistente"
├── Indicadores (1)
│   └── "Meta del indicador 2 es irrealista"
└── Adjuntos (1)
    └── "Falta documento de soporte técnico"
```

16.2 Estructura jerárquica clara para navegar observaciones complejas.

### 17. Tiempo estimado de corrección
17.1 El sistema puede estimar o el validador puede sugerir:
- "Tiempo estimado de corrección: 2 horas"
- "Complejidad: Media"

17.2 Ayuda al registrador a planificar su trabajo.

### 18. Observaciones resueltas
18.1 Una vez corregida y reenviada, mantener registro de observaciones previas marcadas como "Resueltas":
```
Observaciones resueltas:
✓ Presupuesto corregido - 17/01/2026 16:00
✓ Cronograma actualizado - 17/01/2026 16:15
```

18.2 Proporciona trazabilidad completa del proceso de corrección.

### 19. Comparación antes/después
19.1 Opcionalmente, mostrar cómo estaba el campo antes y cómo quedó después:
```
Campo: Presupuesto
Observación: "Monto inconsistente con alcance"

Valor anterior: $10,000,000
Valor corregido: $25,000,000
Justificación: "Se incluyó costo de consultoría externa"
```

19.2 Facilita la validación de que la corrección fue apropiada.

### 20. Accesibilidad de observaciones
20.1 Las observaciones deben ser accesibles:
- Texto alternativo en íconos de prioridad
- Lectores de pantalla deben anunciar observaciones nuevas
- Navegación por teclado entre observaciones
- Alto contraste en resaltados de campos con observaciones

20.2 Usuarios con discapacidad deben poder revisar observaciones efectivamente.

---

### Resultado esperado

Una **visualización completa y organizada de todas las observaciones** realizadas por validadores, con panel destacado en acciones rechazadas, vinculación de observaciones específicas a campos del formulario, historial completo de observaciones en múltiples rechazos, checklist de correcciones pendientes, sistema de priorización, notificaciones oportunas, y herramientas para responder y documentar las correcciones realizadas antes del reenvío.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-158.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-158.png)

