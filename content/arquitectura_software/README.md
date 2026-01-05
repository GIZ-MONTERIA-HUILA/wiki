[Inicio](/README.md)

# Arquitectura de software

## Visión general

La arquitectura del **módulo de restauración del SNIF (Sistema Nacional de Información Forestal)**, se fundamenta en un modelo **cliente-servidor modular**, que integra componentes geográficos, servicios API REST y bases de datos espaciales.  
Su diseño busca garantizar **escalabilidad, mantenibilidad y seguridad**, permitiendo la interoperabilidad entre los distintos módulos del sistema.

## Componentes principales

- **Frontend:** Angular + ArcGIS API for Javascript.
- **Backend:** Node.js / NestJS.
- **Base de datos:** Alfanúmerica: PostgreSQL, Geográfica: PostgreSQL + SDE.
- **Servicios geográficos:** ArcGIS Server.
- **Autenticación:** Keycloak.
- **Orquestador:** Openshift.

## Consideraciones técnicas

- Escalabilidad horizontal de servicios.
- Autenticación y autorización con roles.
- Comunicación segura mediante **HTTPS** y **JWT**.
- Integración de servicios RESTful y geoespaciales.
- Despliegue en contenedores Openshift.

---

## Arquitectura del sistema

En este apartado se detallan los **componentes de la solución tecnológica** y cómo se relacionan entre sí.  
Proporciona una visión más interna y detallada de la **arquitectura del sistema**, mostrando los componentes y las dependencias entre ellos.

Bajo la **notación C4**, se visualiza la estructura interna del sistema y cómo los componentes interactúan entre sí para lograr la funcionalidad esperada.

En este punto, se detallan como componentes: **módulos**, **librerías**, **servicios**, **subsistemas** u otros elementos lógicos de orden funcional.

En el **diagrama de componentes**, estos se representan como **cajas rectangulares**, y las **dependencias** entre ellos se muestran mediante **flechas o líneas** que indican las relaciones.

Se incluyen detalles como **interfaces**, **puertos**, **protocolos**, **bases de datos** u otros elementos relevantes para comprender la estructura y las interacciones del sistema.

> [Nivel 1 — Contexto (System Context)](content/arquitectura_software/c4/nivel1.md)
>
> [Nivel 2 — Contenedores (Containers)](content/arquitectura_software/c4/nivel2.md)
>
> [Nivel 3 — Componentes (Components)](content/arquitectura_software/c4/nivel3.md)

## Enlaces relacionados

- [Historias de usuario](content/historias_usuario/)
- [Casos de prueba](casos_prueba/)
