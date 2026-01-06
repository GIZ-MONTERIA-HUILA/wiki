## HU-pigcct-sym-079

> **Identificador Historia de Usuario:** hu-pigcct-sym-079 \
> **Nombre Historia de Usuario:** Módulo de restauración - Enmascaramiento de Contraseñas y Campos Sensibles.

> **Área Proyecto:** Subdirección de Ecosistemas e Información Ambiental \
> **Nombre proyecto:** Realizar la construcción temática, mejoras informáticas y optimización del Módulo de restauración del SNIF del IDEAM. \
> **Líder funcional:** Wilmer Espitia Muñoz\
> **Analista de requerimiento de TI:** Sergio Alonso Anaya Estévez

## DESCRIPCIÓN HISTORIA DE USUARIO

> **Como:** usuario del sistema.  \
> **Quiero:**  que mi contraseña se oculte mientras la digito.  \
> **Para:** : proteger mi información sensible de miradas de terceros ("shoulder surfing") cuando uso el sistema en público o compartido.

## CRITERIOS DE ACEPTACIÓN

1.	**Comportamiento del Campo de Contraseña**  
    1.1. Todos los campos designados para contraseñas deben ser de tipo password.   
    1.2. El campo debe enmascarar los caracteres por defecto, mostrando puntos, asteriscos o cualquier carácter oculto al digitar la contraseña.    
    1.3. El sistema debe ofrecer, opcionalmente, un botón/ícono de "mostrar/ocultar contraseña" para mejorar la usabilidad (permitir ver lo que se está tecleando).

2.	**Persistencia y Almacenamiento**   
    2.1. Al enviar la contraseña, esta debe ser transmitida utilizando protocolos seguros (**HTTPS/SSL/TLS**) y nunca debe ser visible en los logs del servidor ni en la interfaz.  
    2.2. El almacenamiento en la base de datos debe utilizar funciones hash seguras (Ver *AUTENTICACIÓN*).

    



## DIAGRAMA DE SECUENCIA

![IMAGEN DIAGRAMA DE SECUENCIA](assets/secuencia-hu-pigcct-sym-079.png)

## DIAGRAMA DE FLUJO DEL PROCESO

![IMAGEN DIAGRAMA DE FLUJO DEL PROCESO](assets/actividades-hu-pigcct-sym-079.png)

## PROTOTIPO PRELIMINAR

![PROTOTIPO PRELIMINAR](assets/wireframe-hu-pigcct-sym-079.png)

## ANEXOS

- Estándar de implementación para el botón de mostrar/ocultar contraseña.

