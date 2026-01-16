# HU-PIGCCT-SYM-229  
## Épica: Usuario de consulta pública (sin autenticación)  
### Acceso público al visor

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** ciudadano o usuario interesado sin cuenta en el sistema.  
> **Quiero:** acceder al visor geográfico sin necesidad de autenticación.  
> **Para:** consultar información general del PIGCCT garantizando transparencia y acceso público a datos ambientales.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso directo sin autenticación
1.1 El sistema debe permitir acceder al visor geográfico desde la página principal sin requerir login.  
1.2 El botón o enlace de "Ver mapa público" debe estar visible en la página de inicio.  
1.3 Al hacer clic, el visor debe cargar inmediatamente sin solicitar credenciales.

### 2. Vista de mapa público
2.1 El visor público debe mostrar:
```
VISOR PÚBLICO PIGCCT

[Mapa del territorio con acciones validadas]

Capas disponibles:
☑ Acciones de mitigación validadas
☑ Acciones de adaptación validadas
☐ Límites administrativos
☐ Áreas protegidas

🔍 Buscar municipio...
```

2.2 Solo capas con información pública validada deben estar disponibles.

### 3. Información visible en el mapa
3.1 Al hacer clic en un punto del mapa, mostrar información pública:
```
Acción: Reforestación urbana Río del Oro

Tipo: Mitigación
Municipio: Neiva
Estado: Validado CAR
Eje estratégico: Bosques

Descripción general:
[Texto público de la acción]

[Ver más detalles públicos]
```

3.2 Sin mostrar información administrativa, financiera o de contacto.

### 4. Navegación y controles básicos
4.1 El visor público debe incluir controles básicos:
- Zoom in/out
- Búsqueda por municipio
- Activar/desactivar capas públicas
- Restablecer vista inicial
- Pantalla completa

4.2 Controles simplificados comparados con el visor autenticado.

### 5. Indicador de modo público
5.1 El visor debe mostrar claramente que se está en modo público:
```
[Banner superior]
📖 Modo Consulta Pública

Estás viendo información pública del PIGCCT.
Para acceder a funcionalidades completas, [Inicia sesión]
```

5.2 Invitación visible para usuarios que deseen autenticarse.

### 6. Filtros públicos limitados
6.1 Permitir filtros básicos en el visor público:
```
FILTROS

Tipo de acción:
☐ Mitigación
☐ Adaptación

Municipio:
[Selector de municipios]

Eje estratégico:
[Selector de ejes]

[Aplicar filtros] [Limpiar]
```

6.2 Sin filtros avanzados como estados de validación internos.

### 7. Leyenda simplificada
7.1 El visor público debe incluir leyenda clara:
```
LEYENDA

● Verde: Acciones de mitigación
● Azul: Acciones de adaptación

Solo se muestran acciones validadas
oficialmente por CAR.
```

7.2 Leyenda con información comprensible para ciudadanos.

### 8. Restricción de capas administrativas
8.1 El visor público NO debe mostrar:
- Acciones en borrador
- Acciones en proceso de validación
- Acciones rechazadas
- Información financiera detallada
- Datos de contacto de responsables
- Capas internas de gestión

8.2 Solo información oficialmente validada y de interés público.

### 9. Búsqueda de acciones públicas
9.1 Incluir buscador de acciones públicas:
```
🔍 Buscar acción...

[Texto de búsqueda]

Buscar por:
○ Nombre de acción
○ Municipio
○ Palabra clave

[Buscar]
```

9.2 Resultados limitados a acciones validadas y públicas.

### 10. Compartir ubicación del mapa
10.1 Permitir compartir una vista específica del mapa:
```
📤 Compartir esta vista

URL generada:
https://pigcct.example.com/visor-publico?lat=2.9273&lon=-75.2819&zoom=12

[Copiar enlace] [Compartir en redes]
```

10.2 URLs públicas accesibles sin autenticación.

---

### Resultado esperado

**Acceso público al visor geográfico** sin requerir autenticación, mostrando únicamente acciones validadas con información básica (tipo, municipio, descripción general), controles de navegación simplificados, filtros públicos limitados, leyenda clara, restricción de capas administrativas, búsqueda de acciones públicas, y capacidad de compartir vistas del mapa para garantizar transparencia y acceso ciudadano a información ambiental del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-229.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-229.png)
