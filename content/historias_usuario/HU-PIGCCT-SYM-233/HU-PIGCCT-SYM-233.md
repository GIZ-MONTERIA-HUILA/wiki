# HU-PIGCCT-SYM-233  
## Épica: Usuario de consulta pública (sin autenticación)  
### Restricción de funcionalidades

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de gestión del PIGCCT.  
> **Quiero:** impedir que usuarios de consulta pública creen, editen o validen información.  
> **Para:** garantizar que el acceso público sea exclusivamente de lectura y proteger la integridad de los datos.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Solo acceso de lectura
1.1 Los usuarios públicos (no autenticados) deben tener acceso exclusivamente de lectura.  
1.2 No se deben mostrar botones, formularios o enlaces para crear o modificar información.  
1.3 Todos los intentos de escritura deben bloquearse automáticamente.

### 2. Ocultamiento de botones de acción
2.1 El sistema NO debe mostrar a usuarios públicos:
```
BOTONES OCULTOS PARA PÚBLICO

✗ [Registrar nueva acción]
✗ [Editar]
✗ [Eliminar]
✗ [Validar]
✗ [Rechazar]
✗ [Enviar a validación]
✗ [Guardar]
✗ [Actualizar]
✗ [Cargar archivo]
```

2.2 Interfaz de solo lectura sin opciones de modificación.

### 3. Formularios deshabilitados
3.1 Si por error se muestra un formulario, debe estar completamente deshabilitado:
```
[Formulario de acción - Solo lectura]

Nombre de la acción: [Texto deshabilitado]
Tipo: [Selector deshabilitado]
Descripción: [Texto deshabilitado]

[Botones de guardar NO visibles]

Nota: Esta información es de solo consulta
```

3.2 Campos de formulario deshabilitados e indicación clara de solo lectura.

### 4. Validación en el backend
4.1 Aunque la interfaz oculte opciones, el backend debe validar permisos:
```python
# Validación en cada endpoint de escritura

if not usuario.autenticado:
    return HTTP 401 "Autenticación requerida"

if usuario.rol == "Público":
    return HTTP 403 "No tienes permisos para esta acción"

# Solo entonces procesar la solicitud
```

4.2 Doble protección: UI y backend.

### 5. Mensajes al intentar acciones no permitidas
5.1 Si un usuario público intenta una acción restringida, mostrar mensaje claro:
```
⚠️ ACCIÓN NO PERMITIDA

Esta funcionalidad requiere autenticación.

Para registrar, editar o validar información,
debes iniciar sesión con una cuenta autorizada.

[Solicitar cuenta] [Iniciar sesión]
```

5.2 Guiar al usuario sobre cómo obtener acceso.

### 6. Navegación restringida
6.1 El usuario público NO debe poder acceder a URLs de módulos administrativos:
```
URLs BLOQUEADAS PARA PÚBLICO:

✗ /admin/usuarios
✗ /acciones/crear
✗ /acciones/editar/:id
✗ /validaciones/procesar
✗ /configuracion
✗ /reportes-internos

Redirigir a página de acceso público o login
```

6.2 Protección a nivel de rutas del sistema.

### 7. Sin acceso a funciones de carga
7.1 El usuario público NO debe poder:
- Subir archivos o documentos
- Cargar imágenes
- Importar datos
- Exportar información no pública

7.2 Todas las funciones de modificación de datos bloqueadas.

### 8. Modo lectura en el visor
8.1 En el visor geográfico público, deshabilitar herramientas de edición:
```
HERRAMIENTAS DEL VISOR PÚBLICO

Permitidas:
✓ Navegación (zoom, pan)
✓ Búsqueda
✓ Consulta de información
✓ Filtros de lectura

NO permitidas:
✗ Dibujar en el mapa
✗ Agregar puntos
✗ Editar geometrías
✗ Eliminar elementos
✗ Cambiar estilos de capas
```

8.2 Solo herramientas de consulta visual.

### 9. Sin acceso a datos personales
9.1 El usuario público NO debe ver información de otros usuarios:
```
INFORMACIÓN OCULTA

✗ Lista de usuarios del sistema
✗ Roles y permisos
✗ Datos de contacto de registradores
✗ Información de validadores
✗ Histórico de cambios por usuario
```

9.2 Protección de datos personales de usuarios del sistema.

### 10. Invitación a registro
10.1 Incluir invitaciones para que usuarios públicos soliciten acceso si lo necesitan:
```
¿NECESITAS EDITAR INFORMACIÓN?

Si eres parte de una entidad responsable del PIGCCT
y necesitas registrar o validar información:

[Solicitar cuenta de usuario]

Tipos de cuenta disponibles:
- Registrador (entidades locales)
- Validador (CAR o entidades)
- Consulta avanzada
```

10.2 Facilitar el proceso para obtener permisos de escritura.

---

### Resultado esperado

**Restricción efectiva de funcionalidades de escritura** para usuarios públicos no autenticados, con acceso exclusivo de lectura, ocultamiento de botones de acción (crear, editar, validar), formularios deshabilitados, validación de permisos en backend, mensajes claros al intentar acciones no permitidas, bloqueo de URLs administrativas, sin acceso a funciones de carga, modo solo lectura en visor geográfico, protección de datos personales, e invitaciones para solicitar cuenta con permisos de escritura, garantizando integridad de datos del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-233.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-233.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-233.png)
