# HU-PIGCCT-SYM-160  
## Épica: Reglas de estado derivado  
### Controlar visibilidad según validación

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de control de acceso.  
> **Quiero:** mostrar una acción y sus relaciones solo si los eventos están aprobados.  
> **Para:** garantizar que únicamente información validada sea visible y utilizada en el sistema, manteniendo integridad y confiabilidad de los datos.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Principio de visibilidad basada en validación
1.1 El sistema debe implementar el principio: **"Solo mostrar información validada"**.  
1.2 Las acciones y sus elementos relacionados solo son visibles públicamente si han sido validadas.  
1.3 Información en borrador o en validación solo es visible para:
- El usuario que la creó
- Los validadores asignados
- Administradores

### 2. Visibilidad de acciones según estado
2.1 Aplicar reglas de visibilidad según el estado de la acción:
- **BORRADOR**: Solo visible para el registrador que la creó
- **EN_VALIDACION_ENTIDAD**: Visible para registrador y validadores de entidad
- **VALIDADO_ENTIDAD**: Visible para registrador, validadores de entidad y validadores CAR
- **EN_VALIDACION_CAR**: Visible para todos los usuarios anteriores y validadores CAR
- **VALIDADO_CAR**: Visible públicamente para todos los usuarios del sistema
- **RECHAZADO**: Visible para registrador y validadores que rechazaron

2.2 Estas reglas aseguran acceso apropiado en cada etapa.

### 3. Filtrado en listados
3.1 Al mostrar listados de acciones, aplicar filtros según el rol del usuario:
```sql
-- Para usuarios regulares (no validadores)
WHERE estado_accion = 'VALIDADO_CAR'

-- Para registrador
WHERE estado_accion = 'VALIDADO_CAR' 
   OR usuario_creador = [ID_USUARIO]

-- Para validadores de entidad
WHERE estado_accion IN ('VALIDADO_CAR', 'EN_VALIDACION_ENTIDAD', 'VALIDADO_ENTIDAD')
   OR usuario_creador = [ID_USUARIO]
```

3.2 Cada usuario ve solo las acciones apropiadas para su rol.

### 4. Visibilidad de indicadores asociados
4.1 Los indicadores asociados a una acción heredan la visibilidad de la acción principal.  
4.2 Si la acción está en borrador:
- Los indicadores asociados solo son visibles para el registrador
- No aparecen en reportes públicos
- No se incluyen en cálculos agregados

4.3 Los indicadores se vuelven visibles cuando la acción es validada.

### 5. Visibilidad de adjuntos
5.1 Los archivos adjuntos solo son accesibles si la acción está validada o el usuario tiene permisos.  
5.2 Intentar descargar un adjunto de una acción no validada debe:
- Verificar permisos del usuario
- Si no tiene permisos: Error 403 "No tienes permiso para acceder a este archivo"
- Si tiene permisos: Permitir descarga

5.3 Proteger adjuntos mediante validación de estado antes de servir el archivo.

### 6. Visibilidad en búsquedas y reportes
6.1 Las búsquedas globales solo deben retornar acciones validadas para usuarios regulares.  
6.2 Los reportes públicos o dashboards solo incluyen acciones en estado `VALIDADO_CAR`.  
6.3 Reportes administrativos pueden incluir acciones en todos los estados con indicador claro del estado.

### 7. API y endpoints
7.1 Los endpoints de API deben implementar las mismas reglas de visibilidad:
```
GET /api/acciones
- Sin rol validador: Solo retorna acciones validadas
- Con rol validador: Retorna acciones validadas + en validación

GET /api/acciones/{id}
- Verificar que el usuario tenga permiso para ver esa acción específica
- Retornar 404 si no tiene permiso (no revelar existencia)
```

7.2 Consistencia entre interfaz web y API.

### 8. Mensajes de acceso denegado
8.1 Si un usuario intenta acceder a una acción no validada sin permisos:
- **No revelar que existe**: Mostrar error 404 "Acción no encontrada"
- Evitar mensaje "No tienes permiso" que confirma la existencia

8.2 Esto previene que usuarios descubran acciones en borrador mediante URLs directas.

### 9. Auditoría de intentos de acceso
9.1 Registrar en logs intentos de acceso a acciones no validadas:
- Usuario que intentó acceder
- ID de la acción
- Fecha y hora
- Resultado: Permitido o denegado

9.2 Útil para detectar intentos de acceso no autorizado.

### 10. Visibilidad de eventos
10.1 Los eventos de una acción también deben respetar visibilidad:
- Eventos de acciones en borrador: Solo visibles para el registrador
- Eventos de acciones en validación: Visibles para validadores asignados
- Eventos de acciones validadas: Visibles públicamente (según configuración)

10.2 El historial de eventos respeta las reglas de acceso.

### 11. Notificaciones y visibilidad
11.1 Las notificaciones solo se envían a usuarios que tienen visibilidad sobre la acción:
- Crear acción: Solo al registrador
- Enviar a validación: Al registrador y validadores asignados
- Validar: Al registrador y validadores involucrados
- Publicar como validada: Potencialmente a grupos de interés

11.2 No enviar notificaciones a usuarios sin permisos de visualización.

### 12. Enlaces compartidos
12.1 Los enlaces a acciones deben verificar permisos al abrirse:
```
https://sistema.com/acciones/123
```

12.2 Si el usuario que abre el enlace no tiene permisos, mostrar error apropiado.  
12.3 Opcionalmente, generar enlaces temporales con token para compartir acciones no validadas con revisores externos.

### 13. Datos agregados y estadísticas
13.1 Estadísticas públicas solo deben incluir acciones validadas:
- "Total de acciones: 150" → Solo cuenta validadas
- "Presupuesto total: $500M" → Solo suma acciones validadas

13.2 Dashboards administrativos pueden mostrar todas las acciones con filtros por estado.

### 14. Validación en capas
14.1 Implementar validación de visibilidad en múltiples capas:
- **Frontend**: Ocultar elementos no permitidos en la UI
- **Backend API**: Validar permisos en cada endpoint
- **Base de datos**: Usar vistas (views) que filtran según usuario
- **Archivos**: Validar antes de servir adjuntos

14.2 Defensa en profundidad asegura que no se filtre información.

### 15. Roles y permisos
15.1 Definir claramente qué roles pueden ver qué estados:
```
Rol: Usuario regular
- Ve: VALIDADO_CAR

Rol: Registrador
- Ve: Todas sus acciones en cualquier estado + VALIDADO_CAR de otros

Rol: Validador entidad
- Ve: EN_VALIDACION_ENTIDAD, VALIDADO_ENTIDAD de su entidad + VALIDADO_CAR

Rol: Validador CAR
- Ve: EN_VALIDACION_CAR, VALIDADO_ENTIDAD, VALIDADO_CAR

Rol: Administrador
- Ve: Todo en todos los estados
```

15.2 Matriz de permisos clara y documentada.

### 16. Excepciones y casos especiales
16.1 Definir casos donde información no validada puede ser visible:
- **Vista previa antes de enviar**: Registrador puede compartir con colegas
- **Revisión técnica**: Expertos pueden revisar antes de validación formal
- **Auditoría**: Auditores externos pueden necesitar ver todo

16.2 Estas excepciones requieren permisos especiales y quedan registradas.

### 17. Transición de visibilidad
17.1 Cuando una acción cambia de estado, actualizar visibilidad automáticamente:
- Acción validada → Notificar a usuarios de la entidad
- Publicar en feed de novedades
- Incluir en reportes públicos desde ese momento

17.2 La transición debe ser inmediata y consistente.

### 18. Testing de reglas de visibilidad
18.1 Crear tests automatizados que verifiquen:
- Usuario sin permisos no puede ver acciones no validadas
- Registrador ve sus propias acciones en cualquier estado
- Validadores ven solo acciones asignadas a ellos
- Usuarios regulares solo ven acciones validadas

18.2 Tests de seguridad críticos para mantener integridad.

### 19. Documentación de políticas
19.1 Documentar claramente las políticas de visibilidad:
- Para usuarios: "Solo verás acciones completamente validadas"
- Para registradores: "Tus acciones en borrador son privadas"
- Para validadores: "Puedes ver acciones asignadas a tu rol"

19.2 Transparencia sobre qué información es visible y cuándo.

### 20. Reversión de validación (caso especial)
20.1 Si una acción validada necesita ser revertida (caso excepcional):
- Cambiar estado a RECHAZADO o BORRADOR
- Inmediatamente ocultar de vistas públicas
- Notificar a usuarios que tenían acceso
- Registrar la reversión en auditoría

20.2 Mecanismo de emergencia para corregir publicaciones incorrectas.

---

### Resultado esperado

Un **sistema de control de visibilidad robusto** que garantiza que solo información validada es visible públicamente, con reglas claras por rol y estado, filtrado automático en listados y búsquedas, protección de adjuntos y documentos, validación en múltiples capas (frontend, backend, base de datos), auditoría de accesos, y manejo apropiado de excepciones, asegurando la integridad y confiabilidad de la información mostrada a diferentes tipos de usuarios.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-160.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-160.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-160.png)
