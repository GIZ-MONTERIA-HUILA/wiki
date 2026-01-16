# HU-PIGCCT-SYM-228  
## Épica: Reportes y tableros de control  
### Control de acceso a reportes

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** administrador del sistema.  
> **Quiero:** restringir la generación y descarga de reportes según el rol del usuario.  
> **Para:** proteger información sensible y garantizar el acceso apropiado según permisos.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Definición de permisos por rol
1.1 El sistema debe definir permisos de reportes por rol:
```
ROL: Administrador
✓ Generar todos los reportes
✓ Acceso a datos de todos los territorios
✓ Exportar en todos los formatos
✓ Acceso a reportes con información sensible

ROL: Validador CAR
✓ Generar reportes de su jurisdicción
✓ Acceso a datos de validación
✓ Exportar PDF y Excel
✗ Sin acceso a reportes financieros detallados

ROL: Validador Entidad
✓ Generar reportes de su entidad
✓ Acceso a acciones de su entidad
✓ Exportar PDF y Excel
✗ Sin acceso a datos de otras entidades

ROL: Registrador
✓ Generar reportes de sus propias acciones
✗ Sin acceso a reportes consolidados
✗ Solo exportar PDF básico

ROL: Consulta
✓ Ver tableros públicos
✗ Sin capacidad de generar reportes
✗ Sin exportación de datos
```

1.2 Los permisos deben configurarse en el módulo de administración de usuarios.

### 2. Restricción de opciones de reporte
2.1 El sistema debe mostrar solo las opciones de reporte permitidas por rol:
- Administrador: Ve todas las opciones de reporte
- Validador: Ve solo reportes de su ámbito
- Registrador: Ve solo sus propias acciones
- Consulta: No ve botones de generación de reportes

2.2 Opciones no permitidas no deben mostrarse en la interfaz.

### 3. Filtrado automático por jurisdicción
3.1 El sistema debe filtrar automáticamente los datos según el rol:
```
Usuario: validador_entidad_neiva@example.com
Rol: Validador Entidad
Entidad: Alcaldía de Neiva

Reportes generados automáticamente filtrados por:
- Municipio: Neiva
- Acciones de: Alcaldía de Neiva

Usuario no puede:
- Generar reportes de otros municipios
- Ver acciones de otras entidades
```

3.2 Filtros aplicados de manera transparente pero restrictiva.

### 4. Validación al solicitar reporte
4.1 Al solicitar un reporte, el sistema debe validar permisos:
```python
# Ejemplo de validación
if usuario.rol == "Consulta":
    return "No tienes permisos para generar reportes"

if usuario.rol == "Registrador":
    if reporte.tipo == "consolidado":
        return "Solo puedes generar reportes de tus acciones"

if usuario.rol == "Validador Entidad":
    if reporte.municipio != usuario.municipio:
        return "Solo puedes generar reportes de tu municipio"
```

4.2 Mensajes claros cuando se deniega un reporte por permisos.

### 5. Marca de agua según sensibilidad
5.1 Reportes con información sensible deben incluir marca de agua:
```
Para Administrador:
[Sin marca de agua]

Para Validador:
[MARCA DE AGUA: "USO OFICIAL - VALIDACIÓN"]

Para Registrador:
[MARCA DE AGUA: "USO RESTRINGIDO"]
```

5.2 La marca de agua debe indicar el nivel de sensibilidad del reporte.

### 6. Restricción de formatos de exportación
6.1 El sistema debe restringir formatos según el rol:
```
Administrador:
✓ PDF  ✓ Excel  ✓ CSV  ✓ JSON

Validador:
✓ PDF  ✓ Excel  ✗ CSV  ✗ JSON

Registrador:
✓ PDF  ✗ Excel  ✗ CSV  ✗ JSON

Consulta:
✗ Ninguno
```

6.2 Excel y CSV solo para roles que necesitan análisis de datos.

### 7. Ocultamiento de información sensible
7.1 Según el rol, ocultar información sensible en reportes:
```
Información sensible según rol:

Administrador: Ve todo

Validador CAR:
- ✗ Datos financieros detallados
- ✗ Información personal de registradores

Validador Entidad:
- ✗ Datos de otras entidades
- ✗ Información de validación CAR

Registrador:
- ✗ Datos consolidados
- ✗ Información de otros registradores
```

7.2 Campos sensibles deben aparecer como "---" o "Restringido" para roles sin permiso.

### 8. Log de acceso a reportes
8.1 El sistema debe registrar cada generación de reporte:
```
LOG DE REPORTES

| Fecha/Hora | Usuario | Rol | Tipo de reporte | Resultado | IP |
|------------|---------|-----|-----------------|-----------|-----|
| 2026-01-15 14:30 | admin@example.com | Admin | General PIGCCT | ✓ Generado | 192.168.1.10 |
| 2026-01-15 14:35 | validador@neiva.gov.co | Validador | Acciones Neiva | ✓ Generado | 192.168.1.45 |
| 2026-01-15 14:40 | consulta@example.com | Consulta | General PIGCCT | ✗ Denegado | 192.168.1.89 |
```

8.2 Log debe incluir intentos exitosos y denegados.

### 9. Alertas de intento de acceso no autorizado
9.1 Si un usuario intenta generar un reporte sin permisos, alertar al administrador:
```
ALERTA DE SEGURIDAD

Usuario: consulta_usuario@example.com
Rol: Consulta
Acción: Intentó generar reporte consolidado
Fecha: 15/01/2026 14:40
Resultado: Acceso denegado

[Ver detalles] [Revisar permisos del usuario]
```

9.2 Alertas automáticas para monitorear intentos de acceso no autorizado.

### 10. Reportes anónimos o públicos
10.1 Permitir configurar ciertos reportes como públicos:
```
CONFIGURACIÓN DE REPORTE

Reporte: Indicadores generales PIGCCT

Nivel de acceso:
○ Privado (solo administradores)
○ Interno (usuarios autenticados)
● Público (cualquier persona)

☑ Ocultar información sensible en versión pública
☑ Incluir marca de agua "INFORMACIÓN PÚBLICA"

[Guardar configuración]
```

10.2 Reportes públicos disponibles sin autenticación.

---

### Resultado esperado

**Sistema de control de acceso robusto para reportes** con definición granular de permisos por rol, restricción de opciones según permisos, filtrado automático por jurisdicción, validación al solicitar reportes, marcas de agua según sensibilidad, restricción de formatos de exportación, ocultamiento de información sensible, logs detallados de acceso, alertas de intentos no autorizados, y configuración de reportes públicos para proteger información sensible del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-228.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-228.png)
