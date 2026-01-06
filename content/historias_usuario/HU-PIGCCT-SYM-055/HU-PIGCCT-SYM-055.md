# HU-PIGCCT-SYM-055  
## Épica: Administración de indicadores del PIGCCT  
### Registrar observaciones del indicador

---

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario administrador del sistema.  
> **Quiero:** registrar observaciones adicionales del indicador.  
> **Para:** documentar consideraciones técnicas, metodológicas o contextuales que faciliten su correcta interpretación, uso y seguimiento en el marco del PIGCCT.

---

## CRITERIOS DE ACEPTACIÓN

### 1. Registro de observaciones
1.1 El sistema debe disponer de un campo denominado **observaciones** asociado al indicador.  
1.2 El campo debe permitir el ingreso de texto libre.  
1.3 El registro de observaciones debe ser **opcional**.

---

### 2. Contenido y validaciones
2.1 El campo debe permitir registrar observaciones técnicas, metodológicas, supuestos, restricciones o aclaraciones relevantes.  
2.2 El sistema debe validar una longitud máxima configurable para evitar textos excesivamente extensos.  
2.3 El sistema debe permitir el uso de caracteres especiales y saltos de línea.

---

### 3. Visualización y edición
3.1 Las observaciones deben ser visibles en el formulario de creación y edición del indicador.  
3.2 El usuario administrador debe poder editar las observaciones en cualquier momento.  
3.3 El sistema debe mostrar las observaciones en los módulos de consulta y detalle del indicador.

---

### 4. Trazabilidad
4.1 El sistema debe conservar el historial de cambios realizados sobre el campo **observaciones**.  
4.2 Cada modificación debe registrar:
- Fecha del cambio.  
- Usuario que realizó la modificación.

---

### 5. Integridad con el indicador
5.1 Las observaciones deben estar directamente asociadas al indicador correspondiente.  
5.2 El sistema debe garantizar que el registro de observaciones no afecte la consistencia del resto de la información del indicador.

---

### Resultado esperado

El sistema permite documentar observaciones adicionales de los indicadores del PIGCCT, fortaleciendo la claridad, la trazabilidad y la correcta interpretación técnica y metodológica de la información.


## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-HU-pigcct-sym-055.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-HU-pigcct-sym-055.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-042-061.png)
