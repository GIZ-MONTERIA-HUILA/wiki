# HU-PIGCCT-SYM-146  
## Épica: Botones del formulario y comportamiento  
### Mantener edición habilitada en estado borrador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario registrador.  
> **Quiero:** poder editar completamente una acción en estado borrador.  
> **Para:** facilitar la construcción progresiva del registro sin restricciones hasta que esté listo para validación.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación de estado borrador
1.1 El sistema debe identificar cuando una acción está en estado **"Borrador"**.  
1.2 El estado puede determinarse mediante:
- Campo `estado_accion = 'BORRADOR'` en la tabla accion
- Ausencia de fecha de envío en eventos asociados
- Combinación de ambos

1.3 El formulario debe indicar visualmente el estado actual de la acción.

### 2. Edición completa habilitada
2.1 Para acciones en estado borrador, el sistema debe permitir edición completa de:
- Todos los campos de todas las pestañas habilitadas
- Información general
- Territorio
- Articulación con el plan
- Programación y seguimiento
- Indicadores asociados
- Adjuntos

2.2 No debe haber campos bloqueados o de solo lectura.

### 3. Acceso a todas las funcionalidades
3.1 El usuario debe poder realizar todas las operaciones disponibles:
- Modificar cualquier campo
- Agregar nuevos indicadores
- Editar indicadores existentes
- Eliminar indicadores
- Cargar nuevos adjuntos
- Eliminar adjuntos
- Guardar cambios múltiples veces

### 4. Sin restricciones de validación completa
4.1 El sistema no debe requerir validación completa de todos los campos obligatorios mientras la acción esté en borrador.  
4.2 Puede mostrar advertencias o recordatorios sobre campos faltantes, pero no debe bloquear el guardado.  
4.3 Solo al momento de "Enviar a validación" se debe exigir completitud de datos.

### 5. Generación de eventos de actualización
5.1 Cada vez que se guarda un cambio en una acción en borrador, debe generarse un evento de tipo **update**.  
5.2 Los eventos deben capturar:
- Valor anterior
- Valor nuevo
- Usuario que modifica
- Fecha de modificación

5.3 Estos eventos permanecen sin fecha de envío hasta que la acción se envíe a validación.

### 6. Indicador visual de estado editable
6.1 El formulario debe mostrar claramente que la acción está en modo editable.  
6.2 Puede incluir:
- Badge o etiqueta: "Estado: Borrador - Editable"
- Mensaje informativo: "Puedes modificar esta acción libremente"
- Ausencia de iconos de bloqueo

6.3 El indicador debe ser visible en todas las pestañas.

### 7. Botones de acción disponibles
7.1 Para acciones en borrador, los siguientes botones deben estar disponibles:
- **Guardar borrador**: Para guardar cambios sin enviar
- **Enviar a validación**: Para completar y enviar (requiere validación completa)
- **Eliminar acción**: Para eliminar el borrador si ya no es necesario
- **Cancelar**: Para descartar cambios y salir

7.2 Los botones deben estar habilitados según corresponda.

### 8. Edición de indicadores asociados
8.1 El usuario debe poder modificar indicadores asociados a la acción en borrador:
- Cambiar valores meta
- Cambiar unidades de medida
- Cambiar descripción del indicador
- Agregar o quitar indicadores

8.2 Los cambios en indicadores deben generar eventos en la tabla `indicador_accion` o eventos relacionados.

### 9. Gestión de adjuntos
9.1 El usuario debe poder gestionar adjuntos libremente:
- Cargar nuevos archivos
- Reemplazar archivos existentes
- Eliminar archivos
- Cambiar descripciones de archivos

9.2 Los cambios en adjuntos deben registrarse apropiadamente.

### 10. Navegación libre entre pestañas
10.1 El usuario debe poder navegar entre todas las pestañas habilitadas sin restricciones.  
10.2 Los cambios en una pestaña deben conservarse al cambiar a otra.  
10.3 No es necesario "guardar" entre cambios de pestaña; el guardado es explícito mediante el botón.

### 11. Mensajes de advertencia informativos
11.1 El sistema puede mostrar mensajes informativos sobre campos faltantes:
```
"Recuerda: Para enviar a validación necesitarás completar [X campos]"
```

11.2 Estos mensajes no deben bloquear la edición o el guardado como borrador.  
11.3 Deben ser claros y orientadores, no restrictivos.

### 12. Comparación con estados no editables
12.1 El comportamiento en borrador debe contrastar con:
- **En validación**: Solo lectura, excepto para validadores
- **Validada**: Bloqueada, requiere nuevo evento para editar
- **Rechazada**: Puede requerir aprobación para reabrir

12.2 El sistema debe comunicar claramente cuándo la acción deja de ser editable.

### 13. Múltiples sesiones de edición
13.1 El usuario debe poder:
- Guardar el borrador y salir
- Regresar días después
- Continuar editando desde donde lo dejó
- Guardar nuevamente sin problemas

13.2 El borrador debe conservar toda la información entre sesiones.

### 14. Control de cambios
14.1 Internamente, el sistema debe mantener registro de todos los cambios mediante eventos.  
14.2 Aunque los eventos no estén enviados a validación, deben registrarse para auditoría.  
14.3 Esto permite rastrear la evolución de la acción desde su creación.

### 15. Transición de borrador a validación
15.1 Cuando el usuario decide enviar a validación:
- Se validan todos los campos obligatorios
- Se establece fecha de envío en los eventos
- Se cambia el estado de la acción a "En validación"
- La acción deja de ser editable para el registrador
- Se notifica a los validadores correspondientes

15.2 Antes de esta transición, la edición debe permanecer completamente libre.

---

### Resultado esperado

Una **acción en estado borrador completamente editable** que permite al usuario registrador modificar libremente todos los campos, agregar o editar indicadores y adjuntos, guardar cambios múltiples veces, y trabajar progresivamente hasta que considere que la acción está lista para ser enviada a validación.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-146.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-146.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-146.png)
