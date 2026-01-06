## HU-pigcct-sym-077

> **Identificador Historia de Usuario:** hu-pigcct-sym-077 \
> **Nombre Historia de Usuario:** Módulo de restauración - Estándares de Seguridad en Formularios y Transmisión de Datos

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  \
> **Quiero:**  implementar controles de seguridad en todos los formularios y en la transmisión de datos al servidor.  \
> **Para:** : prevenir ataques comunes (XSS, SQL Injection) y proteger la integridad de la información sensible del SNIF.

## CRITERIOS DE ACEPTACIÓN

1.	**Defensa Profunda (Defense in Depth)**     
    1.1. Todos los datos ingresados deben ser revalidados en el servidor (backend), independientemente de las validaciones realizadas en el cliente (frontend).     
    1.2. El backend debe rechazar cualquier dato que sea inválido, modificado o manipulado fuera de los controles del cliente.

2.	**Protección contra Inyección**     
    2.1. El sistema debe implementar mecanismos de prevención activa contra ataques XSS y SQL Injection en todas las entradas de usuario (Ver [HU-78](../HU-pigcct-sym-078/HU-pigcct-sym-078.md)).  
    2.2. Se debe asegurar el uso de consultas parametrizadas en todas las interacciones con la base de datos.

3.	**Manejo de Información Sensible**  
    3.1. La información sensible (contraseñas, tokens) debe estar protegida tanto en la interfaz como en el transporte y almacenamiento (Ver [HU-79](../HU-pigcct-sym-079/HU-pigcct-sym-079.md) y [HU-80](../HU-pigcct-sym-080/HU-pigcct-sym-080.md)).



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-077.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-077.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-077.png)

## ANEXOS

- Checklist de seguridad OWASP Top 10 aplicable a formularios.

