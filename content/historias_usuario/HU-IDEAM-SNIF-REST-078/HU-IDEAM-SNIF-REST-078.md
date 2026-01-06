## HU-pigcct-sym-078

> **Identificador Historia de Usuario:** hu-pigcct-sym-078 \
> **Nombre Historia de Usuario:** Módulo de restauración - Prevención de Ataques XSS y SQL Injection.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** desarrollador de backend.  \
> **Quiero:**  sanitizar y escapar todas las entradas de usuario antes de procesarlas o almacenarlas.  \
> **Para:** : prevenir la ejecución de código malicioso (scripts) en el cliente o la manipulación de consultas a la base de datos (inyección).

## CRITERIOS DE ACEPTACIÓN

1.	**Sanitización de Entradas (XSS)**  
     1.1. Todos los campos de texto deben ser sanitizados o escapados en el servidor para eliminar cualquier intento de inyección de código HTML o JavaScript (Cross-Site Scripting).    
        1.2. Los campos que no admiten formatos avanzados no deben ejecutar código ni permitir la persistencia de scripts.

2.	**Protección de Base de Datos (SQLi)**  
    2.1. Todas las consultas a la base de datos que utilicen entradas de usuario deben ser implementadas mediante consultas parametrizadas o sentencias preparadas.     
    2.2. El backend debe rechazar las entradas que contengan patrones de inyección SQL conocidos.

3.	**Revalidación en el Servidor**  
    3.1. Esta validación de seguridad debe ejecutarse antes de la lógica de negocio, incluso si el cliente ya pasó las validaciones de tipo/longitud (Ver [HU-77](../HU-pigcct-sym-077/HU-pigcct-sym-077.md)).
    



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-078.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-078.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-078.png)

## ANEXOS

- Listado de funciones de sanitización de entradas utilizadas en el lenguaje de backend.

