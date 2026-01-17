# HU-PIGCCT-SYM-197  
## Épica: Navegación, Inicio y Acceso al Sistema PIGCCT  
### Catálogos territoriales

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** administrar los catálogos territoriales del PIGCCT.  
> **Para:** mantener actualizada y consistente la información de departamentos y municipios utilizada en los distintos módulos del sistema.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Acceso a la gestión de catálogos territoriales
1.1 El sistema debe permitir el acceso al módulo **Catálogos territoriales** únicamente a usuarios con rol **administrador**.  
1.2 El acceso debe estar disponible desde el módulo de **Catálogos**.  
1.3 El sistema no debe permitir el acceso a usuarios sin permisos administrativos.

### 2. Catálogos territoriales gestionados
2.1 El sistema debe permitir administrar como mínimo los siguientes catálogos:
- **Departamentos**.
- **Municipios**.

2.2 Los catálogos deben corresponder a la división político-administrativa oficial.

### 3. Gestión de departamentos
3.1 El administrador debe poder:
- Crear departamentos.
- Editar información básica.
- Activar o inactivar registros.

3.2 Cada departamento debe contar con un identificador único.

### 4. Gestión de municipios
4.1 El sistema debe permitir administrar municipios asociados a un departamento.  
4.2 Cada municipio debe estar obligatoriamente vinculado a un departamento válido.

4.3 El sistema debe validar la integridad de la relación municipio–departamento.

### 5. Estados de los registros territoriales
5.1 El sistema debe permitir definir el estado de los registros territoriales:
- Activo.
- Inactivo.

5.2 Los territorios inactivos:
- No deben estar disponibles para nuevas asociaciones.
- Deben conservar su información histórica.

### 6. Uso de los catálogos territoriales
6.1 Los catálogos territoriales deben ser utilizados en:
- Registro de PIGCCT.
- Definición de cobertura territorial.
- Formularios de acciones.
- Reportes territoriales.

6.2 El sistema debe impedir la selección de territorios inactivos en procesos operativos.

### 7. Validaciones y consistencia
7.1 El sistema debe validar:
- Duplicidad de registros.
- Coherencia jerárquica territorial.

7.2 El sistema debe impedir inconsistencias en la estructura territorial.

### 8. Auditoría y trazabilidad
8.1 El sistema debe registrar:
- Usuario creador o modificador.
- Fecha y hora de la operación.
- Cambios realizados.

8.2 Esta información debe estar disponible para auditoría institucional.

### 9. Usabilidad y experiencia de usuario
9.1 La gestión de catálogos territoriales debe ser clara y organizada.  
9.2 El sistema debe mostrar mensajes claros de confirmación o error.  
9.3 El diseño debe ser consistente con la identidad visual del sistema PIGCCT.

---

## Resultado esperado

El administrador puede **gestionar correctamente los catálogos territoriales del PIGCCT**, manteniendo actualizada la información de departamentos y municipios, garantizando consistencia territorial y asegurando su uso correcto en los procesos operativos y de reporte del sistema.


---

## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-197.png)


## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-197.png)


