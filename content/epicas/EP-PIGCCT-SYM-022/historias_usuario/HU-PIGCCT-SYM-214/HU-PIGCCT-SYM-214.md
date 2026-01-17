# HU-PIGCCT-SYM-214
## Épica: Visor geográfico del PIGCCT 
### Acceder al detalle de la acción desde el visor
---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario autorizado del sistema.  
> **Quiero:** acceder al detalle de una acción directamente desde el visor geográfico.  
> **Para:** profundizar en su información administrativa, técnica y de seguimiento del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Control de acceso por permisos
1.1 El acceso al detalle de la acción está habilitado únicamente para usuarios con permisos autorizados.

1.2 El sistema valida los permisos del usuario antes de permitir el acceso al detalle.

1.3 Los usuarios sin permisos visualizan la acción en el mapa, pero no pueden acceder a su detalle completo.

### 2. Acceso desde el visor geográfico
2.1 Desde el popup o panel informativo de la acción, el usuario autorizado puede acceder al detalle de la acción mediante un botón o enlace.

2.2 El acceso es claro, visible y coherente con el diseño del visor.

2.3 El sistema permite acceder al detalle sin perder el contexto del visor geográfico.

### 3. Información del detalle de la acción
3.1 El detalle muestra información administrativa de la acción (identificación, responsables, estado).

3.2 Se visualiza información técnica asociada a la acción.

3.3 Se presentan datos de seguimiento, avance y cumplimiento de indicadores.

3.4 La información presentada corresponde a la versión más reciente y validada según el rol del usuario.

### 4. Navegación y experiencia de usuario
4.1 El sistema permite regresar fácilmente al visor geográfico desde el detalle de la acción.

4.2 La transición entre visor y detalle es fluida y consistente.

### 5. Integración con filtros y contexto
5.1 El detalle de la acción respeta los filtros activos aplicados en el visor.

5.2 La acción consultada corresponde exactamente a la seleccionada en el mapa.

5.3 El sistema mantiene el contexto territorial al regresar al visor.

### 6. Rendimiento y seguridad
6.1 El acceso al detalle se realiza sin tiempos de carga excesivos.

6.2 La información sensible se protege de acuerdo con los permisos del usuario.

6.3 El sistema registra el acceso a la información según las políticas de auditoría.

---

## Resultado esperado

El usuario autorizado puede acceder de manera segura y ágil al detalle de una acción desde el visor geográfico, consultando información administrativa y de seguimiento sin perder el contexto territorial, fortaleciendo el análisis y la gestión del PIGCCT.

---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-214.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-214.png)


## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-214.png)
