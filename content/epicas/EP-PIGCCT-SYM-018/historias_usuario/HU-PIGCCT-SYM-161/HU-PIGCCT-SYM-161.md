# HU-PIGCCT-SYM-161  
## Épica: Consistencia entre acción y relaciones  
### Validar consistencia antes del envío

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de validación.  
> **Quiero:** validar que no existan eventos pendientes en tablas relacionadas antes de permitir el envío.  
> **Para:** garantizar que se envíe a validación un paquete completo y coherente de información sin elementos incompletos o inconsistentes.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Principio de consistencia
1.1 El sistema debe garantizar que todos los elementos relacionados con una acción estén en estado coherente antes de enviar a validación.  
1.2 No debe permitirse enviar una acción si hay:
- Eventos pendientes de completar
- Indicadores sin valores proyectados
- Relaciones sin eventos asociados
- Inconsistencias entre la acción y sus dependencias

1.3 La validación de consistencia es obligatoria antes de cada envío.

### 2. Validación de eventos de la acción principal
2.1 Antes de enviar, verificar que la acción principal tenga un evento válido:
- Existe evento de tipo 'create' o 'update'
- El evento tiene toda la información requerida
- No hay campos obligatorios vacíos en el evento

2.2 Si falta el evento de la acción, bloquear el envío con mensaje claro.

### 3. Validación de indicadores asociados
3.1 Verificar que todos los indicadores asociados a la acción tengan eventos correspondientes:
- Cada registro en `indicador_accion` debe tener un evento en la tabla `evento`
- Los eventos de indicadores deben tener `accion_id_principal` correcto
- Los indicadores deben tener valores proyectados diligenciados

3.2 Si un indicador no tiene evento o está incompleto, mostrar error específico.

### 4. Validación de valores de indicadores
4.1 Para cada indicador asociado, validar que tenga valores proyectados:
- Meta definida
- Unidad de medida especificada
- Fecha objetivo establecida

4.2 Si faltan valores proyectados, indicar cuáles indicadores están incompletos:
```
"No se puede enviar: Los siguientes indicadores carecen de valores proyectados:
- Indicador 'Hectáreas reforestadas': Falta meta
- Indicador 'Familias beneficiadas': Falta fecha objetivo"
```

### 5. Validación de adjuntos
5.1 Si existen adjuntos asociados, validar que:
- Cada adjunto tenga su evento correspondiente
- Los archivos estén cargados correctamente (no solo metadata)
- Los adjuntos tengan descripción y tipo de documento

5.2 Adjuntos obligatorios (si aplica según tipo de acción) deben estar presentes.

### 6. Validación de territorio
6.1 Verificar que la información de territorio esté completa:
- Departamento seleccionado
- Municipio(s) seleccionado(s)
- Cobertura territorial definida
- Coordenadas geográficas si son requeridas

6.2 La información territorial es crítica y debe estar completa.

### 7. Validación de programación
7.1 Verificar que la programación de la acción esté completa:
- Fecha de inicio válida y coherente
- Presupuesto definido y mayor a cero
- Cronograma con hitos si es requerido
- Fuente de financiación especificada

7.2 Sin programación completa, no se puede validar la viabilidad de la acción.

### 8. Validación de articulación con el plan
8.1 Verificar que la acción esté articulada con el plan de cambio climático:
- Eje estratégico seleccionado
- Medida asociada identificada
- Objetivos vinculados
- Alineación con metas del plan

8.2 La articulación es fundamental para coherencia del sistema.

### 9. Detección de eventos huérfanos
9.1 Identificar eventos que referencian registros eliminados o inexistentes:
- Eventos con `id_registro_evento` que no existe en su tabla
- Eventos sin `accion_id_principal` válido
- Referencias rotas en el sistema de eventos

9.2 Estos eventos huérfanos deben reportarse y corregirse antes de enviar.

### 10. Validación de relaciones bidireccionales
10.1 Verificar coherencia en relaciones bidireccionales:
- Si la acción referencia un indicador, el indicador debe existir
- Si un indicador está asociado, debe haber registro en `indicador_accion`
- Conteos coinciden: "3 indicadores asociados" = 3 registros en tabla

10.2 Prevenir inconsistencias por operaciones parcialmente fallidas.

### 11. Reporte detallado de inconsistencias
11.1 Si se detectan problemas, generar reporte detallado:
```
"Validación fallida - Se encontraron los siguientes problemas:

ACCIÓN PRINCIPAL:
✓ Información general completa
✗ Falta presupuesto

INDICADORES:
✓ 3 indicadores asociados
✗ Indicador 'Hectáreas reforestadas' sin valores proyectados

ADJUNTOS:
✓ 5 archivos cargados

TERRITORIO:
✓ Departamento y municipio definidos

Debes corregir los elementos marcados con ✗ antes de enviar"
```

11.2 Listado claro y accionable de qué corregir.

### 12. Validación transaccional
12.1 La validación de consistencia debe ejecutarse en una transacción de solo lectura.  
12.2 Asegurar que durante la validación no cambien los datos (usar niveles de aislamiento apropiados).  
12.3 Si detecta cambios concurrentes, solicitar re-validar.

### 13. Cache de validación
13.1 Opcionalmente, cachear el resultado de validación por un tiempo breve (ej: 5 minutos).  
13.2 Si el usuario hace cambios, invalidar el cache.  
13.3 Esto mejora performance sin comprometer exactitud.

### 14. Validación progresiva
14.1 Mostrar indicadores de validación mientras el usuario trabaja:
- Checkbox verde: Sección completa
- Exclamación amarilla: Sección con advertencias
- X roja: Sección incompleta

14.2 El usuario sabe en tiempo real qué falta para poder enviar.

### 15. Bloqueo de envío
15.1 Si la validación falla, el botón "Enviar a validación" debe:
- Estar deshabilitado visualmente
- Mostrar tooltip explicativo: "Completa los campos requeridos"
- Al hacer click, mostrar el reporte de inconsistencias

15.2 No permitir envío hasta que todo esté correcto.

### 16. Validación en backend
16.1 Además de validación en frontend, el backend debe re-validar antes de cambiar estado.  
16.2 Si la validación backend falla, retornar error con detalles:
```json
{
  "error": "Validación de consistencia fallida",
  "codigo": "INCONSISTENCIA_DATOS",
  "detalles": {
    "accion": ["Falta presupuesto"],
    "indicadores": ["Indicador 2 sin valores proyectados"],
    "adjuntos": []
  }
}
```

16.3 Defensa en profundidad contra datos inconsistentes.

### 17. Auditoría de validaciones
17.1 Registrar cada validación de consistencia en logs:
- Usuario que intentó enviar
- Fecha y hora
- Resultado: Éxito o falló
- Detalles de inconsistencias encontradas (si aplica)

17.2 Útil para analizar problemas comunes y mejorar la UX.

### 18. Notificación de problemas comunes
18.1 Si el sistema detecta patrones de errores frecuentes:
- "Muchos usuarios olvidan diligenciar valores proyectados"
- Ofrecer tutorial o ayuda contextual
- Mejorar la interfaz para hacer estos campos más obvios

18.2 Mejora continua basada en datos reales.

---

### Resultado esperado

Una **validación exhaustiva de consistencia** que verifica todos los elementos de una acción y sus relaciones antes de permitir el envío a validación, con reporte detallado de inconsistencias encontradas, bloqueo del envío hasta que se corrijan los problemas, validación tanto en frontend como backend, y auditoría de validaciones para identificar problemas frecuentes y mejorar la experiencia del usuario.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-161.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-161.png)

