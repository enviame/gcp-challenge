# Challenge CGP

¡Hola! Un gusto tenerte acá. El siguiente desafío busca conocer más acerca de tus conocimientos y habilidades en el uso de los recursos de Google Cloud Platform. Debido al constante crecimiento que está experimentando Envíame, necesitamos sumar a nuestro equipo a una persona capaz de facilitar el desarrollo y soporte de las aplicaciones desplegadas.

El desafío se compone de dos grandes temas a evaluar:

1. Permisos: IAM y cuentas de servicio.
2. Servicios de backend: App Engine, Cloud Functions, entre otros. Setup y monitoreo.

### Antes de comenzar

- Tienes 3 días para resolver este challenge
- Debes proveer un repositorio privado en GitHub con la respuesta de la parte 1, las instrucciones para revisar parte 2 y 3, asi mismo si utilizaste algún script para automatizar ciertos elementos, tambien te pedimos compartirlo en este repositorio.
- En el repositorio privado debes agregar como usuarios colaboradores a: **@rolivagon @rsebjara @vmolina-enviame @vham @rcarrascop**.


Sin más preámbulos, aquí vamos. Manos a la obra.

## Parte 1: Permisos (2 pts)

En ACME S.A. existen **múltiples células de desarrollo** que construyen software para distintas áreas de negocio. Cada una se compone de 2 a 5 desarrolladores y un líder técnico. Además, cada célula maneja varios proyectos en GCP con similares recursos, cada proyecto de GCP tiene un ambiente de stage y otro para producción. Los servicios que normalmente se usan son App Engine, Cloud Functions, SQL Cloud, Firestore, Storage, Pub/Sub, entre otros.

Adicionalmente, existen **células de soporte**, que si bien no desarrolla ni hace despliegues, acceden con permisos limitados de lectura a las bases de datos y registros de logs.

**Consideraciones**

- Cada célula debe contar con la mayor autonomía posible para desarrollar
- Se debe evitar dar permisos innecesarios o fuera de su alcance.
- Considerar que algunos servicios no se puedan emular de manera local y en ese caso se debe dar un acceso limitado al desarrollador para utilizar el servicio.

**Objetivo**

- Diseñar un sistema conceptual de permisos que permitan manejar varias células de desarrollo y de soporte
- Definir cuáles serían los roles, funciones, grupos, etc que considerarías en la solución
- Detallar el listado de permisos de GCP que tendría cada uno
- Te puedes apoyar dibujando diagramas 😉

**Alcance**

- No es necesario crear esta configuración en un ambiente real de GCP
- Esperamos que se entregue un documento con el diseño propuesto

## Parte 2: Servicios de backend (8 pts)

Una vez que aceptes este challenge, te daremos acceso a un proyecto especial en GCP y a un [repositorio](https://source.cloud.google.com/enviame-lab/gcp-challente-python) que contiene un proyecto básico en Python. Una vez que cuentes con estos recursos deberás realizar las siguientes actividades:

### Despliegue (5 pts)

- Desplegar el proyecto en algún servicio de backend de GCP. Puede ser Compute Engine, App Engine o Cloud Run. Deberás comentar las razones de tu decisión (1 punto).
- Para el correcto funcionamiento de la aplicación debes crear las instancias de bases de datos con las siguientes configuraciones (1 punto):
    - Instancia Redis: capa básica, región us-central1, capacidad 1 GB, versión 6.
    - Instancia MySQL: región us-central1, zona única, 1vCPU, memoria 3.75 GB, capacidad 10 GB SSD, versión 8.
- Configurar un pipeline de despliegue en el servicio de Cloud Build ( 3 pts):
    - El proyecto debe ejecutar las pruebas unitarias exitosamente antes del despliegue.
    - El activador en Cloud Build para el despliegue debe requerir aprobación de `tech-test@enviame.io.`

### Monitoreo (3 pts)

- Crear una alerta de monitoreo indicando alzas en la latencia del servicio desplegado en el punto anterior. Si la respuesta tarda más de N segundos, notificar a `tech-test@enviame.io`.
- El equipo de soporte necesita revisar logs relacionados al consumo del servicio. Se debe dar un acceso al usuario `tech-test@enviame.io`.

## Palabras al cierre

Esperamos de todo corazón que entregues una prueba exitosa. Cualquier duda que tengas, nos puedes escribir al correo  `tech-test@enviame.io` y te responderemos a la brevedad. ¡Que la fuerza esté contigo!
