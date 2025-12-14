El documento del proyecto debe ser un documento que sintetice los aspectos del proyecto elegido para su desarrollo con respecto a los temas vistos en clases. 

Debe tener claramente identificados los nombres y apellidos de cada componente, grupo al que pertenecen (1, 2, o 3 mañana o tarde), curso académico, nombre del proyecto (seguir la política de nombres). Use este [[modelo de portada]] para el documento del proyecto y alójelo en su repositorio o en otro sitio accesible y que tenga posibilidad de verse el último momento de edicación. Puede usar el repositorio del proyecto usando para ello el lenguaje de [markdown](https://guides.github.com/features/mastering-markdown/) que ofrece github. En todo caso, debe ser un documento elaborado en formato [wiki]. 

Será un documento presentado de manera profesional guardando la forma en los estilos y contenidos y con el máximo nivel de rigor académico y profesional.

Tenga en cuenta los siguientes aspectos: 

* Siempre diferencie claramente las secciones y subsecciones y para ello use etiquetas de encabezado como las que se disponen en los lenguajes tipo _markdown_

# Apartados del documento 

El documento del proyecto tendrá (al menos) que sintetizar los siguientes apartados:

## Indicadores del proyecto

(_debe dejar enlaces a evidencias que permitan de una forma sencilla analizar estos indicadores, con gráficas y/o con enlaces_)

Miembro del equipo  | Horas | Commits | LoC | Test | Issues | Work Item| Dificultad
------------- | ------------- | ------------- | ------------- | ------------- | ------------- |  ------------- |  ------------- | 
[Basallote Braza, David](https://github.com/orgs/DavidBBSA) | HH | XX | YY | ZZ | II | Trending datasets | H/M/L |
[Chaves Cumbreras, David](https://github.com/davchacum) | HH | XX | YY | ZZ | II | Download counter for datasets | H/M/L |
[Gago Vázquez, Francisco](https://github.com/frangago71) | HH | XX | YY | ZZ | II | Comments on datasets | H/M/L |
[González Vázquez, Guillermo](https://github.com/guigonvaz) | HH | XX | YY | ZZ | II | Two-factor authentication (2FA) | H/M/L |
[Herrera Luján, Marco Antonio](https://github.com/Marco2026) | HH | XX | YY | ZZ | II | Advanced dataset search | H/M/L |
[Rodríguez Muñoz, Rafael](https://github.com/rafaelroodrgz) | HH | XX | YY | ZZ | II | Automatic dataset recommendations | H/M/L |


[Apellidos, nombre](https://github.com/nombredeusuariodegithub) | HH | XX | YY | ZZ | II | Descripción breve | H/M/L |
**TOTAL** | tHH  | tXX | tYY | tZZ | tII | Descripción breve | H (X)/M(Y)/L(Z) |

La tabla contiene la información de cada miembro del proyecto y el total de la siguiente forma: 
  * Horas: número de horas empleadas en el proyecto
  * Commits: solo contar los commits hechos por miembros del equipo, no lo commits previos
  * LoC (líneas de código): solo contar las líneas producidas por el equipo y no las que ya existían o las que se producen al incluir código de terceros
  * Test: solo contar los test realizados por el equipo nuevos
  * Issues: solo contar las issues gestionadas dentro del proyecto y que hayan sido gestionadas por el equipo
  * Work Item: principal WI del que se ha hecho cargo el miembro del proyecto
  * Dificultad: señalar el grado de dificultad en cada caso. Además, en los totales, poner cuántos se han hecho de cada grado de dificultad entre paréntesis. 

## Integración con otros equipos
No aplica, nuestro proyecto es individual.

## Resumen ejecutivo 
Este trabajo, realizado para la asignatura de Evolución y Gestión de la Configuración (EGC), presenta una evolución y adaptación significativa de UVLHub. Hemos tomado como base este repositorio, originalmente diseñado para la gestión de Feature Models y archivos .uvl, y lo hemos modificado para aplicarlo a un dominio totalmente diferente: la gestión de datos y estadísticas de la NBA. El objetivo ha sido demostrar la flexibilidad de la arquitectura original reutilizándola para otro contexto de compartición de documentos, a la vez que enriquecemos la plataforma mejorando el login y la búsqueda de datasets y añadiendo nuevas funcionalidades, como la pantalla de trending datasets o el módulo de comentarios para fomentar el debate entre los aficionados.

El sistema base está construido sobre Flask (Python). Siguiendo la metodología de trabajo establecida en la asignatura, hemos mantenido la arquitectura modular del proyecto para integrar las nuevas funcionalidades y el cambio de dominio sin afectar a la estabilidad del sistema. En esta línea, hemos usado Rosemary, la herramienta de línea de comandos (CLI) nativa de este ecosistema. Su utilización nos ha permitido generar el esqueleto del código (rutas, servicios y repositorios) alineándonos con los estándares del proyecto base, lo que ha facilitado enormemente la organización de carpetas y la configuración inicial.

A nivel funcional, la transformación de la plataforma ha sido total. Hemos implementado listas de tendencias (Trending Datasets), recomendaciones automáticas de datasets y filtros de búsqueda avanzada. Además, hemos un nuevo sistema de comentarios. Paralelamente, hemos elevado la complejidad técnica y la seguridad del sistema integrando Autenticación en Dos Pasos (2FA) y desarrollando herramientas críticas de infraestructura como Fakenodo —un simulador local de Zenodo para eliminar dependencias externas—, además de añadir métricas como contadores de descargas y automatizar el aseguramiento de la calidad mediante flujos de trabajo de integración y despliegue continuo (CI/CD).

En el Frontend (desarrollado con Jinja2 y Bootstrap), el trabajo se ha materializado en la creación de múltiples interfaces nuevas para dar soporte a las funcionalidades añadidas. Concretamente, hemos diseñado y desarrollado la pantalla de comentarios, la pantalla de Trending Datasets, la sección de búsqueda avanzada, el apartado de datasets recomendados y las vistas necesarias para la configuración y validación del doble factor de autenticación (2FA), gestionando toda la estructura visual y la presentación de los datos.

Uno de los puntos fuertes del trabajo ha sido la flexibilidad en la gestión del entorno de desarrollo. No nos hemos limitado a una única forma de despliegue, sino que hemos configurado el proyecto para que sea completamente funcional en tres escenarios distintos: mediante contenedores usando Docker y Docker Compose, utilizando virtualización gracias a Vagrant, y también en modo local nativo mediante flask run. Esta versatilidad garantiza que la aplicación pueda desplegarse y funcionar correctamente independientemente de la infraestructura o las preferencias del desarrollador.

Por último, la calidad del software se ha garantizado mediante una estrategia de testing integral. Hemos utilizado pytest para ejecutar una batería de tests unitarios y de integración, asegurando la corrección de la lógica interna y la comunicación entre módulos. Para la validación de la interfaz y los flujos de usuario completos (end-to-end), hemos implementado pruebas automatizadas con Selenium, e incluso hemos realizado pruebas de carga y rendimiento del servidor utilizando Locust. 

En definitiva, hemos cogido un proyecto complejo y lo hemos evolucionado con éxito hacia NBAHub, aplicando herramientas de gestión de configuración y estrategias de despliegue flexibles para mantener el control sobre el desarrollo. El resultado es una plataforma transformada que integra funcionalidades sociales y de descubrimiento, cumpliendo con los objetivos planteados.

## Descripción del sistema (1.500 palabras aproximadamente)
Se explicará el sistema desarrollado desde un punto de vista funcional y arquitectónico. Se hará una descripción tanto funcional como técnica de sus componentes y su relación con el resto de subsistemas. Habrá una sección que enumere explícitamente cuáles son los cambios que se han desarrollado para el proyecto.

Este documento describe el sistema desarrollado en el repositorio EGC-G2-M/nba-hub, un proyecto diseñado para proporcionar una plataforma centralizada para la consulta y gestión de información relevante de la NBA (National Basketball Association). El sistema aborda las necesidades de usuarios interesados en acceder a estadísticas, resultados y datos de jugadores y equipos de manera eficiente.
### 1. Perspectiva Funcional del Sistema
Desde un punto de vista funcional, el sistema se enfoca en la presentación y la interacción con la información, actuando como un punto de acceso a diversos datos del mundo del baloncesto. El sistema implementa las siguientes funcionalidades:

#### 1.1 Visualización de Estadísticas
Permite a los usuarios consultar estadísticas detalladas de jugadores (puntos, asistencias, rebotes, etc.) y equipos. Esto incluye la capacidad de filtrar y ordenar los datos.

#### 1.2 Búsqueda avanzada
Permite buscar información específica (jugadores, equipos, temporadas) a través de un motor de búsqueda intuitivo.

#### 1.3 Descarga de datasets
Permite a los usuarios descargar aquellos datasets de estadísticas que les interesen.

#### 1.4 Interacción en datasets
El sistema implementa funcionalidades para tener un conteo de número de descargas y visualizar aquellos con mayor número de descargas.

#### 1.5 Comentarios en datasets
El sistema permite a los usuarios añadir comentarios a los datasets.

### 2. Arquitectura del sistema
El sistema implementa una arquitectura Cliente-Servidor, estructurada bajo un patrón MVC (Modelo-Vista-Controlador)

#### 2.1 Capas arquitectónicas
La arquitectura puede dividirse conceptualmente en tres capas principales:

- Capa de Presentación (Frontend):
        Responsable de la interfaz de usuario (UI/UX) y de la interacción directa con el usuario final. Transmite las peticiones al backend y renderiza los datos recibidos. Interactúa directamente con la Capa de Aplicación a través de la API.
- Capa de Aplicación (Backend/API):
        Contiene la lógica de negocio principal del sistema. Recibe las peticiones del frontend, procesa los datos, realiza la validación y llama a la capa de datos para recuperar o manipular la información. Se comunica con la Capa de Presentación y con la Capa de Datos.
- Capa de Datos:
        Almacena, gestiona y recupera toda la información persistente, incluyendo estadísticas, metadatos de partidos, perfiles, etc. Es accedida únicamente por la Capa de Aplicación.

### 3. Descripción Técnica de los Componentes y Subsistemas

### Visión global del proceso de desarrollo (1.500 palabras aproximadamente)
Debe dar una visión general del proceso que ha seguido enlazándolo con las herramientas que ha utilizado. Ponga un ejemplo de un cambio que se proponga al sistema y cómo abordaría todo el ciclo hasta tener ese cambio en producción. Los detalles de cómo hacer el cambio vendrán en el apartado correspondiente.  

### Entorno de desarrollo (800 palabras aproximadamente)
Debe explicar cuál es el entorno de desarrollo que ha usado, cuáles son las versiones usadas y qué pasos hay que seguir para instalar tanto su sistema como los subsistemas relacionados para hacer funcionar el sistema al completo. Si se han usado distintos entornos de desarrollo por parte de distintos miembros del grupo, también debe referenciarlo aquí. 

### Ejercicio de propuesta de cambio
Se presentará un ejercicio con una propuesta concreta de cambio en la que a partir de un cambio que se requiera, se expliquen paso por paso (incluyendo comandos y uso de herramientas) lo que hay que hacer para realizar dicho cambio. Debe ser un ejercicio ilustrativo de todo el proceso de evolución y gestión de la configuración del proyecto. 

Crear issue usando la plantilla de issues desde github.
<img width="1076" height="895" alt="image" src="https://github.com/user-attachments/assets/bb344c76-cb5f-46eb-840e-6319aafbc334" />
<img width="1320" height="895" alt="image" src="https://github.com/user-attachments/assets/84bf0d35-38a9-4b22-b390-5635d0e72199" />
<img width="1320" height="895" alt="image" src="https://github.com/user-attachments/assets/f0373d02-d70c-4215-a862-9a8d8d94fa14" />


Crear rama en local para trabajar en esa issue.
git branch prueba
git checkout prueba

Mandar la rama al repositorio de github.
git push -u origin prueba

Hacer el cambio.

Hacer el commit del cambio usando la plantilla de commit.
git add --all
git config commit.template .github/COMMIT_TEMPLATE/commit_template.txt
git commit

Hacer push.
git push

Hacer merge a trunk.
git checkout trunk
git pull trunk
git merge --no--ff prueba
git push

Hacer merge a main.
git checkout main
git pull main
git merge --no-ff trunk
git push

### Conclusiones y trabajo futuro
Se enunciarán algunas conclusiones y se presentará un apartado sobre las mejoras que se proponen para el futuro (curso siguiente) y que no han sido desarrolladas en el sistema que se entrega
