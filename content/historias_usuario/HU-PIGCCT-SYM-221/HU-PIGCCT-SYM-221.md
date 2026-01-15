# HU-PIGCCT-SYM-221  
## Épica: Menú de apropiación y capacitación  
### Visualizar videos de uso

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario de la plataforma.  
> **Quiero:** visualizar videos tutoriales organizados por módulo.  
> **Para:** aprender visualmente cómo usar cada funcionalidad de forma práctica y guiada.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Biblioteca de videos organizada
1.1 Los videos deben estar organizados por módulos principales:
- **Visor geográfico**: Navegación, capas, consultas espaciales
- **Gestión de acciones**: Crear, editar, enviar a validación
- **Indicadores y seguimiento**: Asociar indicadores, registrar avances
- **Reportes y análisis**: Generar reportes, exportar datos
- **Validación**: Proceso de validación, aprobar/rechazar

1.2 Navegación clara entre categorías de videos.

### 2. Estructura de cada módulo
2.1 Cada módulo debe contener videos específicos:
```
📁 VISOR GEOGRÁFICO
  🎥 Introducción al visor (3:45)
  🎥 Cómo navegar el mapa (2:30)
  🎥 Activar y desactivar capas (1:50)
  🎥 Consultar información de una acción (2:15)
  🎥 Filtrar acciones por criterios (4:20)

📁 GESTIÓN DE ACCIONES
  🎥 Crear una nueva acción (5:30)
  🎥 Llenar información general (3:40)
  🎥 Definir territorio y cobertura (4:10)
  🎥 Asociar indicadores (3:20)
  🎥 Adjuntar documentos (2:00)
  🎥 Enviar a validación (2:45)
```

2.2 Videos cortos y enfocados en tareas específicas.

### 3. Reproductor de video integrado
3.1 Implementar reproductor de video con controles completos:
- Play/Pausa
- Barra de progreso
- Control de volumen
- Velocidad de reproducción (0.5x, 1x, 1.5x, 2x)
- Pantalla completa
- Subtítulos (si están disponibles)

3.2 Experiencia de visualización profesional.

### 4. Información de cada video
4.1 Mostrar metadata útil para cada video:
- Título descriptivo
- Duración
- Nivel: Básico, Intermedio, Avanzado
- Fecha de última actualización
- Descripción breve
- Número de visualizaciones

4.2 Ayuda al usuario a elegir el video apropiado.

### 5. Progreso de visualización
5.1 Registrar el progreso del usuario:
- Videos vistos: Marca de visto ✓
- Videos en progreso: Barra de progreso
- Videos no vistos: Sin marca

5.2 El usuario sabe qué ha visto y qué falta.

### 6. Búsqueda de videos
6.1 Buscador específico para videos:
- "¿Cómo crear una acción?"
- "Validación"
- "Reportes"

6.2 Resultados muestran videos relevantes con thumbnails.

### 7. Thumbnails y previsualizaciones
7.1 Cada video debe tener thumbnail atractivo:
- Captura representativa del contenido
- Título superpuesto
- Duración visible
- Badge de "Nuevo" si fue agregado recientemente

7.2 Thumbnails ayudan a identificar rápidamente el contenido.

### 8. Descargar videos
8.1 Permitir descargar videos para uso offline:
- Formato MP4 optimizado
- Resolución apropiada (720p o 1080p)
- Indicar tamaño del archivo

8.2 Útil para usuarios con conexión limitada.

### 9. Videos según rol
9.1 Filtrar o destacar videos según el rol del usuario:
- **Registrador**: Videos sobre registro de acciones
- **Validador**: Videos sobre proceso de validación
- **Consulta**: Videos sobre visor y reportes

9.2 Contenido relevante aparece primero.

### 10. Integración con YouTube o Vimeo
10.1 Los videos pueden alojarse en:
- Servidor propio
- YouTube (canal privado o público)
- Vimeo
- Plataforma LMS

10.2 Elegir la opción más apropiada según infraestructura.

---

### Resultado esperado

Una **biblioteca completa de videos tutoriales** organizada por módulos (visor, acciones, indicadores, reportes, validación), con reproductor integrado, controles completos, progreso de visualización, búsqueda de videos, thumbnails atractivos, descargas para uso offline, y filtrado por rol para mejorar el contenido educativo.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-221.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-221.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-221.png)
