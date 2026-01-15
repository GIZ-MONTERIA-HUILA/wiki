# HU-PIGCCT-SYM-230  
## Épica: Usuario de consulta pública (sin autenticación)  
### Información pública limitada

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** ciudadano consultando información pública del PIGCCT.  
> **Quiero:** visualizar únicamente información validada y agregada.  
> **Para:** conocer resultados oficiales sin acceso a detalles administrativos o financieros sensibles.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Filtrado automático de información pública
1.1 El sistema debe filtrar automáticamente y mostrar solo:
- Acciones con estado "Validado CAR"
- Indicadores agregados públicos
- Estadísticas consolidadas
- Información no sensible

1.2 Todo lo demás debe permanecer oculto para usuarios no autenticados.

### 2. Acciones validadas únicamente
2.1 Al consultar acciones, mostrar solo las validadas oficialmente:
```
ACCIONES PÚBLICAS

Mostrando: 89 acciones validadas

[Lista de acciones]
- Reforestación urbana Río del Oro (Validado CAR)
- Sistema de alerta temprana municipal (Validado CAR)
- ...

Nota: Solo se muestran acciones oficialmente validadas
```

2.2 Acciones en borrador, en validación o rechazadas no deben aparecer.

### 3. Información básica de cada acción
3.1 Para cada acción pública, mostrar campos no sensibles:
```
ACCIÓN: Reforestación urbana Río del Oro

Información pública:
- Tipo: Mitigación
- Municipio: Neiva
- Eje estratégico: Bosques
- Estado: Validado CAR
- Fecha de validación: 10/12/2025
- Descripción: [Texto público]

Impacto esperado:
- Área de intervención: 50 hectáreas
- CO2 capturado estimado: 2,500 tCO2eq
- Población beneficiada: 15,000 habitantes

[Ver ubicación en el mapa]
```

3.2 Sin información financiera, de contacto o administrativa.

### 4. Ocultamiento de información sensible
4.1 El sistema debe ocultar automáticamente:
```
INFORMACIÓN OCULTA PARA PÚBLICO

✗ Presupuesto detallado
✗ Fuentes de financiación específicas
✗ Nombres y contactos de responsables
✗ Documentos internos de validación
✗ Observaciones de validadores
✗ Estados intermedios de validación
✗ Datos personales de registradores
✗ Cronogramas detallados internos
```

4.2 Solo información agregada y no sensible debe ser visible.

### 5. Indicadores agregados
5.1 Mostrar indicadores consolidados públicos:
```
INDICADORES PÚBLICOS DEL PIGCCT

Mitigación:
- Total acciones validadas: 45
- Reducción estimada CO2: 125,000 tCO2eq
- Área de intervención: 2,300 hectáreas

Adaptación:
- Total acciones validadas: 44
- Población beneficiada: 250,000 habitantes
- Municipios participantes: 12
```

5.2 Sin desglose financiero o por entidad ejecutora.

### 6. Estadísticas sin detalles administrativos
6.1 Al consultar estadísticas, mostrar datos agregados:
```
ESTADÍSTICAS PÚBLICAS

Avance del PIGCCT:
- 89 acciones validadas
- 12 municipios participantes
- 4 ejes estratégicos activos
- Última actualización: 15/01/2026

Distribución por tipo:
- Mitigación: 51%
- Adaptación: 49%
```

6.2 Sin información sobre estados de validación o borradores.

### 7. Mapas con información agregada
7.1 En el visor, mostrar información resumida por territorio:
```
MUNICIPIO: NEIVA

Información pública:
- Acciones validadas: 24
- Tipos: 15 mitigación, 9 adaptación
- Ejes más desarrollados: Energía, Bosques

[Ver listado de acciones]
```

7.2 Sin información sobre entidades ejecutoras específicas.

### 8. Documentos públicos únicamente
8.1 Si hay documentos, mostrar solo los marcados como públicos:
```
DOCUMENTOS PÚBLICOS

- Resumen ejecutivo PIGCCT Huila (PDF)
- Informe anual de avance 2025 (PDF)
- Guía de acciones de mitigación (PDF)

Nota: Solo documentos de acceso público
```

8.2 Documentos internos, actas o presupuestos no deben listarse.

### 9. Mensaje sobre información limitada
9.1 Incluir mensaje claro sobre las limitaciones:
```
ℹ️ INFORMACIÓN PÚBLICA

Estás consultando información de acceso público del PIGCCT.

Se muestra:
✓ Acciones oficialmente validadas
✓ Estadísticas agregadas
✓ Documentos públicos

No se muestra:
✗ Información financiera detallada
✗ Datos en proceso de validación
✗ Información administrativa interna

Para acceso completo, [Solicitar cuenta]
```

9.2 Transparencia sobre qué se muestra y qué no.

### 10. Sin acceso a módulos administrativos
10.1 El usuario público NO debe ver en el menú:
```
MENÚ PÚBLICO (Simplificado)

📍 Visor público
📊 Estadísticas públicas
📥 Reportes públicos
❓ Preguntas frecuentes
📧 Contacto

[NO VISIBLE para público]
✗ Registrar acciones
✗ Validar acciones
✗ Administración
✗ Tableros de control completos
✗ Gestión de usuarios
```

10.2 Menú simplificado solo con opciones públicas.

---

### Resultado esperado

**Acceso limitado a información pública validada** mostrando únicamente acciones con estado "Validado CAR", indicadores agregados, estadísticas consolidadas sin detalles administrativos, ocultamiento automático de información financiera y sensible, indicadores públicos sin desglose por entidad, mapas con datos resumidos, documentos públicos únicamente, mensajes claros sobre limitaciones, y menú simplificado sin módulos administrativos para garantizar transparencia controlada.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-230.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-230.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-230.png)
