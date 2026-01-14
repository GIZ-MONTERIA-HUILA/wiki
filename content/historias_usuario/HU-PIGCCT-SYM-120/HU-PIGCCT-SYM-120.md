# HU-PIGCCT-SYM-120  
## Épica: Gestión de eventos y validación de información del PIGCCT  
### Registrar evento para tablas dependientes

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión de eventos.  
> **Quiero:** registrar correctamente eventos en tablas dependientes (adjuntos, indicador_accion, indicador_accion_valor).  
> **Para:** mantener el contexto de la acción asociada y garantizar la trazabilidad completa del proceso de validación en todo el modelo de datos.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación de tablas dependientes
1.1 El sistema debe identificar cuando se crea o actualiza un registro en las siguientes **tablas dependientes**:
- adjuntos
- indicador_accion
- indicador_accion_valor

1.2 Estas tablas se consideran dependientes porque requieren una relación con la tabla **acción**.

### 2. Uso de campos _principal para la acción
2.1 Cuando se registra un evento sobre una tabla dependiente, el sistema debe diligenciar los **campos _principal** con la información de la tabla **acción**:
- **esquema_principal**: Esquema donde se encuentra la tabla acción.
- **tabla_principal**: Debe contener el valor **"accion"**.
- **id_objeto_principal**: Debe contener el **id_accion** asociado al registro de la tabla dependiente.

2.2 Estos campos deben permitir identificar rápidamente a qué acción pertenece el evento, independientemente de la tabla donde ocurrió la modificación.

### 3. Uso de campos _relacionado para la tabla afectada
3.1 El sistema debe diligenciar los **campos _relacionado** con la información de la tabla realmente afectada:
- **esquema_relacionado**: Esquema de la tabla dependiente afectada.
- **tabla_relacionado**: Nombre de la tabla dependiente (ej: "adjuntos", "indicador_accion", "indicador_accion_valor").
- **id_objeto_relacionado**: ID del registro específico creado o actualizado en la tabla dependiente.

3.2 Estos campos deben permitir identificar exactamente qué registro de la tabla dependiente fue modificado.

### 4. Regla de registro dual
4.1 El sistema debe aplicar la siguiente regla para eventos en tablas dependientes:
- **Campos _principal**: Siempre apuntan a la tabla acción y su id_accion correspondiente.
- **Campos _relacionado**: Siempre apuntan a la tabla dependiente realmente afectada y su ID específico.

4.2 Esta dualidad debe mantenerse consistentemente en todos los eventos de tablas dependientes.

### 5. Validación de relación con acción
5.1 El sistema debe validar que el registro de la tabla dependiente efectivamente esté relacionado con una acción válida.  
5.2 Antes de crear el evento, debe verificar:
- Que el id_accion exista en la tabla acción.
- Que el registro de la tabla dependiente tenga correctamente configurada su clave foránea hacia acción.

5.3 Si la validación falla, el sistema debe registrar un error y notificar al administrador.

### 6. Ejemplo de registro de evento para adjuntos
6.1 Al crear un adjunto asociado a una acción, el evento debe registrarse así:
```
tabla_principal = "accion"
id_objeto_principal = [id_accion del adjunto]
tabla_relacionado = "adjuntos"
id_objeto_relacionado = [id_adjunto]
tipo_afectacion_enm = "create"
```

### 7. Ejemplo de registro de evento para indicador_accion
7.1 Al actualizar un indicador_accion, el evento debe registrarse así:
```
tabla_principal = "accion"
id_objeto_principal = [id_accion asociado]
tabla_relacionado = "indicador_accion"
id_objeto_relacionado = [id_indicador_accion]
tipo_afectacion_enm = "update"
```

### 8. Consulta de eventos por contexto
8.1 El sistema debe permitir consultar:
- **Todos los eventos de una acción** (usando tabla_principal = "accion" AND id_objeto_principal = [id_accion]).
- **Eventos específicos de una tabla dependiente** (usando tabla_relacionado = [nombre_tabla]).
- **Eventos de un registro específico de tabla dependiente** (usando tabla_relacionado = [nombre_tabla] AND id_objeto_relacionado = [id]).

8.2 Las consultas deben ser eficientes y estar soportadas por índices apropiados.

### 9. Trazabilidad completa
9.1 El modelo de registro dual debe permitir:
- Ver todos los cambios relacionados con una acción (perspectiva de proceso).
- Ver el historial específico de un adjunto, indicador, o valor (perspectiva de objeto).

9.2 Esta dualidad facilita diferentes necesidades de auditoría y seguimiento.

### 10. Integridad y coherencia
10.1 El sistema debe garantizar que la relación entre los campos _principal y _relacionado sea siempre coherente.  
10.2 No debe ser posible crear eventos donde:
- tabla_principal ≠ "accion" cuando se trata de tablas dependientes.
- id_objeto_principal no corresponda efectivamente al id_accion asociado al registro dependiente.

### 11. Documentación del modelo
11.1 La documentación técnica debe explicar claramente la diferencia entre campos _principal y _relacionado.  
11.2 Debe incluir ejemplos para cada tabla dependiente.

---

### Resultado esperado

**Eventos correctamente registrados** para tablas dependientes, con campos _principal apuntando a la tabla acción para mantener el contexto del proceso, y campos _relacionado identificando la tabla y registro realmente afectado, garantizando trazabilidad completa y facilitando consultas tanto por contexto de acción como por objeto específico.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-120.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-120.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-120.png)
