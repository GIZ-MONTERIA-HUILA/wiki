# HU-PIGCCT-SYM-222  
## Épica: Menú de apropiación y capacitación  
### Contenido según rol

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario con un rol específico en el sistema.  
> **Quiero:** ver contenido de apropiación específico para mi rol.  
> **Para:** enfocarme en las funcionalidades y responsabilidades que son relevantes para mi trabajo.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Identificación de roles del sistema
1.1 El sistema debe reconocer los siguientes roles:
- **Registrador**: Crea y edita acciones
- **Validador de entidad**: Valida acciones de su entidad
- **Validador CAR**: Valida acciones a nivel regional
- **Consulta**: Solo visualiza información
- **Administrador**: Gestiona el sistema

1.2 Cada rol tiene necesidades de capacitación diferentes.

### 2. Contenido para Registrador
2.1 Los registradores deben ver contenido enfocado en:
```
CONTENIDO PARA REGISTRADOR

📚 Guías principales:
- Cómo crear una acción
- Llenar todos los campos obligatorios
- Asociar indicadores
- Adjuntar documentos
- Guardar borradores
- Enviar a validación

🎥 Videos destacados:
- Crear tu primera acción (5:30)
- Definir territorio y cobertura (4:10)
- Qué hacer si tu acción es rechazada (3:45)

❓ Preguntas frecuentes:
- ¿Puedo editar una acción enviada?
- ¿Cuánto demora la validación?
- ¿Qué significa "estado borrador"?
```

2.2 Enfoque en el ciclo de vida de registro de acciones.

### 3. Contenido para Validador de Entidad
3.1 Los validadores de entidad deben ver contenido enfocado en:
```
CONTENIDO PARA VALIDADOR DE ENTIDAD

📚 Guías principales:
- Proceso de validación de acciones
- Criterios de validación
- Cómo aprobar una acción
- Cómo rechazar con observaciones
- Seguimiento de acciones validadas

🎥 Videos destacados:
- Introducción al rol de validador (4:00)
- Revisar y validar una acción (6:20)
- Redactar observaciones efectivas (3:30)

❓ Preguntas frecuentes:
- ¿Qué debo revisar en una acción?
- ¿Cuándo debo rechazar vs aprobar?
- ¿Puedo validar parcialmente?
```

3.2 Enfoque en el proceso de revisión y validación.

### 4. Contenido para Validador CAR
4.1 Los validadores CAR deben ver contenido enfocado en:
```
CONTENIDO PARA VALIDADOR CAR

📚 Guías principales:
- Validación a nivel regional
- Criterios adicionales de CAR
- Revisión de acciones pre-validadas por entidades
- Aprobación final
- Generación de reportes consolidados

🎥 Videos destacados:
- Rol del validador CAR (3:50)
- Revisar acciones pre-validadas (5:10)
- Criterios de validación CAR (4:40)

❓ Preguntas frecuentes:
- ¿Qué reviso si la entidad ya validó?
- ¿Puedo devolver a la entidad?
- ¿Cómo rechazo a nivel CAR?
```

4.2 Enfoque en validación de segundo nivel.

### 5. Contenido para rol de Consulta
5.1 Los usuarios con rol de consulta deben ver contenido enfocado en:
```
CONTENIDO PARA CONSULTA

📚 Guías principales:
- Navegar el visor geográfico
- Consultar acciones validadas
- Filtrar por territorio o categoría
- Generar reportes
- Exportar datos

🎥 Videos destacados:
- Introducción al visor (3:45)
- Cómo buscar acciones (2:30)
- Generar y descargar reportes (4:15)

❓ Preguntas frecuentes:
- ¿Por qué no veo todas las acciones?
- ¿Cómo exporto a Excel?
- ¿Puedo descargar mapas?
```

5.2 Enfoque en consulta y visualización de datos.

### 6. Contenido para Administrador
6.1 Los administradores deben ver contenido enfocado en:
```
CONTENIDO PARA ADMINISTRADOR

📚 Guías principales:
- Gestión de usuarios y permisos
- Configuración del sistema
- Monitoreo de actividad
- Mantenimiento de catálogos
- Respaldos y seguridad

🎥 Videos destacados:
- Administración de usuarios (5:00)
- Configurar permisos por rol (4:30)
- Dashboard administrativo (3:20)

❓ Preguntas frecuentes:
- ¿Cómo creo un nuevo usuario?
- ¿Cómo reseteo una contraseña?
- ¿Cómo hago respaldo?
```

6.2 Enfoque en gestión y administración del sistema.

### 7. Filtrado automático de contenido
7.1 Al acceder al menú de apropiación, filtrar automáticamente:
- Mostrar primero contenido relevante para el rol del usuario
- Ocultar o minimizar contenido no relevante
- Permitir ver "todo el contenido" si el usuario lo desea

7.2 Experiencia personalizada por defecto.

### 8. Contenido común para todos los roles
8.1 Algunos contenidos son relevantes para todos:
- Inicio de sesión y seguridad
- Recuperación de contraseña
- Actualizar perfil
- Contactar soporte

8.2 Este contenido aparece para todos los usuarios.

### 9. Cambio de perspectiva
9.1 Si un usuario tiene múltiples roles, permitir cambiar de perspectiva:
```
Ver contenido para:
○ Mi rol principal: Registrador
○ Mi rol secundario: Validador
○ Todo el contenido
```

9.2 Flexibilidad para usuarios con múltiples responsabilidades.

### 10. Onboarding específico por rol
10.1 El tour inicial debe adaptarse al rol:
- **Registrador**: Enfatizar formulario de acciones
- **Validador**: Enfatizar módulo de validación
- **Consulta**: Enfatizar visor y reportes

10.2 Primera experiencia relevante desde el inicio.

---

### Resultado esperado

Un **sistema de capacitación personalizado por rol** que muestra contenido específico y relevante para registradores, validadores de entidad, validadores CAR, usuarios de consulta y administradores, con filtrado automático de contenido, opciones de cambio de perspectiva para usuarios con múltiples roles, y onboarding adaptado a las responsabilidades de cada rol en el sistema.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-222.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-222.png)
