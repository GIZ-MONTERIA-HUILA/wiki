# HU-PIGCCT-SYM-139  
## Épica: Autenticación, gestión de usuarios, y control de acceso del sistema PIGCCT  
### Registrar auditoría de acceso

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** sistema de auditoría y seguridad.  
> **Quiero:** registrar eventos de autenticación y acceso al sistema.  
> **Para:** mantener trazabilidad, detectar actividades sospechosas, cumplir requerimientos de seguridad y facilitar investigaciones cuando sea necesario.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Eventos de autenticación a registrar

El sistema debe registrar los siguientes eventos relacionados con autenticación:

#### 1.1 Inicio de sesión exitoso
- Usuario que inició sesión
- Fecha y hora exacta del inicio de sesión
- Dirección IP de origen
- Navegador y sistema operativo (user agent)
- Método de autenticación utilizado
- Token JWT generado (ID del token, no el token completo)
- Duración de sesión configurada

#### 1.2 Intento de inicio de sesión fallido
- Usuario o correo utilizado (si existe)
- Fecha y hora del intento
- Dirección IP de origen
- Razón del fallo (contraseña incorrecta, usuario no existe, cuenta bloqueada, etc.)
- Navegador y sistema operativo
- Número de intento (si es parte de serie de intentos)

#### 1.3 Cierre de sesión
- Usuario que cerró sesión
- Fecha y hora del cierre
- Tipo de cierre (manual por usuario, automático por timeout, forzado por administrador)
- Duración total de la sesión

#### 1.4 Cierre de sesión forzado
- Usuario cuya sesión fue cerrada
- Administrador que forzó el cierre
- Fecha y hora
- Razón del cierre forzado

---

### 2. Eventos de gestión de cuentas

#### 2.1 Bloqueo de usuario
- Usuario bloqueado
- Fecha y hora del bloqueo
- Razón del bloqueo (intentos fallidos, bloqueo manual, bloqueo automático)
- Administrador que bloqueó (si fue manual)
- IP desde donde se bloqueó (si fue automático)

#### 2.2 Desbloqueo de usuario
- Usuario desbloqueado
- Fecha y hora del desbloqueo
- Administrador que realizó el desbloqueo
- Justificación del desbloqueo
- IP del administrador

#### 2.3 Recuperación de contraseña
- Usuario que solicitó recuperación
- Fecha y hora de la solicitud
- Dirección IP de origen
- Correo electrónico al que se envió el enlace
- Token generado (ID, no el token completo)
- Estado de la solicitud (enviado, usado, expirado, fallido)

#### 2.4 Restablecimiento de contraseña
- Usuario que restableció contraseña
- Fecha y hora del restablecimiento
- Dirección IP desde donde se restableció
- Método utilizado (enlace de recuperación, cambio por administrador)
- Éxito o fallo de la operación

#### 2.5 Cambio de contraseña
- Usuario que cambió contraseña
- Fecha y hora del cambio
- Tipo de cambio (voluntario, obligatorio al primer inicio)
- Éxito de la operación

---

### 3. Estructura del registro de auditoría

3.1 Cada registro de auditoría debe incluir:

```json
{
  "id": "uuid",
  "timestamp": "2026-01-13T10:30:45.123Z",
  "event_type": "inicio_sesion_exitoso",
  "user_id": 123,
  "username": "usuario.ejemplo",
  "email": "usuario@entidad.gov.co",
  "ip_address": "192.168.1.100",
  "user_agent": "Mozilla/5.0...",
  "details": {
    // Información específica del evento
  },
  "severity": "info", // info, warning, error, critical
  "success": true
}
```

3.2 Los registros deben almacenarse en una tabla dedicada de auditoría.

---

### 4. Niveles de severidad

4.1 El sistema debe clasificar eventos según severidad:

- **INFO**: Operaciones normales (inicio de sesión exitoso, cierre de sesión)
- **WARNING**: Eventos que requieren atención (intento fallido, solicitud de recuperación)
- **ERROR**: Eventos problemáticos (múltiples intentos fallidos de mismo usuario)
- **CRITICAL**: Eventos críticos de seguridad (cuenta bloqueada, acceso sospechoso)

---

### 5. Almacenamiento de logs

5.1 Los registros de auditoría deben almacenarse:
- En base de datos relacional para consultas y reportes
- Opcionalmente, en archivos de log para respaldo
- Con retención mínima de 2 años (configurable)

5.2 Los logs deben ser inmutables (no se pueden editar ni eliminar salvo política de retención).

---

### 6. Información de contexto

6.1 Para cada evento, capturar información contextual:

**Información del usuario**:
- ID, username, correo
- Rol actual
- Entidad asociada

**Información de red**:
- Dirección IP (IPv4 o IPv6)
- Geolocalización aproximada (país, ciudad) si es posible
- ISP o proveedor de red

**Información del dispositivo**:
- User agent completo
- Navegador y versión
- Sistema operativo
- Tipo de dispositivo (desktop, mobile, tablet)

---

### 7. Detección de actividades sospechosas

7.1 El sistema debe detectar y marcar como sospechosas:

- **Múltiples intentos fallidos**: Más de N intentos en X minutos
- **Acceso desde ubicación inusual**: IP de país diferente al habitual
- **Acceso desde múltiples IPs**: Mismo usuario desde IPs muy diferentes simultáneamente
- **Horario inusual**: Acceso fuera del horario laboral típico del usuario
- **Cambios rápidos de dispositivo**: Sesiones desde dispositivos muy diferentes en corto tiempo

7.2 Actividades sospechosas deben generar alertas a administradores.

---

### 8. Reportes de auditoría

8.1 El sistema debe permitir generar reportes de auditoría con:

- Filtros por usuario, fecha, tipo de evento, severidad
- Exportación a Excel, PDF, CSV
- Visualizaciones gráficas de actividad
- Estadísticas de uso del sistema

8.2 Los reportes deben estar disponibles para administradores y auditores autorizados.

---

### 9. Consulta de logs

9.1 Proporcionar interfaz para que administradores consulten logs con:
- Búsqueda por usuario, IP, fecha
- Filtrado por tipo de evento
- Ordenamiento por fecha, severidad
- Vista detallada de cada evento

---

### 10. Alertas automáticas

10.1 El sistema debe generar alertas automáticas para:

- **Cuenta bloqueada**: Notificar a administradores y al usuario afectado
- **Múltiples intentos fallidos**: Alerta en tiempo real
- **Acceso desde nueva ubicación**: Notificar al usuario
- **Cambio de contraseña**: Confirmar al usuario por correo
- **Actividad sospechosa detectada**: Alerta urgente a seguridad

10.2 Las alertas pueden enviarse por correo, notificaciones en el sistema, o ambas.

---

### 11. Protección de datos personales

11.1 Los logs de auditoría deben cumplir con regulaciones de protección de datos:
- No almacenar contraseñas (ni siquiera hasheadas en los logs)
- No almacenar información sensible innecesaria
- Permitir anonimización para reportes estadísticos
- Implementar acceso restringido a logs

---

### 12. Integridad de logs

12.1 El sistema debe garantizar integridad de logs mediante:
- Hash de cada registro para detectar manipulaciones
- Almacenamiento en sistema de archivos de solo escritura
- Respaldos periódicos en ubicación segura
- Firma digital de archivos de log (opcional)

---

### 13. Rendimiento y escalabilidad

13.1 El registro de auditoría debe ser eficiente:
- Operaciones asíncronas para no bloquear autenticación
- Índices apropiados en tablas de auditoría
- Archivado automático de logs antiguos
- Particionamiento de tablas por fecha si es necesario

---

### 14. Cumplimiento normativo

14.1 Los logs deben satisfacer requerimientos de:
- Auditorías de seguridad
- Normativa de protección de datos
- Políticas institucionales de control de acceso
- Investigaciones de incidentes de seguridad

---

### 15. Dashboard de seguridad

15.1 Proporcionar dashboard con métricas en tiempo real:
- Usuarios activos actualmente
- Intentos fallidos en las últimas horas
- Cuentas bloqueadas hoy
- Alertas de seguridad pendientes
- Gráficos de actividad por hora/día

---

### 16. Retención y archivado

16.1 Implementar política de retención:
- Logs activos: últimos 3-6 meses en base de datos principal
- Logs archivados: 6 meses - 2 años en almacenamiento secundario
- Logs históricos: > 2 años, considerar eliminación segura o archivado permanente

16.2 El proceso de archivado debe ser automático.

---

### 17. Correlación de eventos

17.1 El sistema debe permitir correlacionar eventos relacionados:
- Seguir sesión completa de un usuario (inicio → actividad → cierre)
- Relacionar intentos fallidos que llevaron a bloqueo
- Trazar solicitudes de recuperación hasta restablecimiento

---

### 18. Exportación para análisis forense

18.1 Permitir exportación de logs en formato estándar para análisis:
- JSON para procesamiento automatizado
- CSV para análisis en Excel
- Formato compatible con herramientas SIEM si existe integración

---

### 19. Privacidad y acceso

19.1 Solo los siguientes roles deben acceder a logs de auditoría:
- Administradores del sistema
- Personal de seguridad autorizado
- Auditores externos (con permisos temporales)

19.2 El acceso a logs debe ser auditado también (meta-auditoría).

---

### Resultado esperado

Un **sistema robusto de auditoría** que registra todos los eventos de autenticación y gestión de cuentas (inicio de sesión, intentos fallidos, bloqueos, recuperación de contraseña, etc.) con información contextual completa, detecta actividades sospechosas, genera alertas apropiadas, permite consultas y reportes, garantiza integridad de logs, y cumple con requerimientos de seguridad y normativa.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-139.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-139.png)
