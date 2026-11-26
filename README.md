# SDD, AI, Scrum y Kiro - Johan Suarez

## 1. Spec-Driven Development (SDD)

El primer mapa mental presenta el desarrollo guiado por especificaciones, un enfoque que busca definir el comportamiento, los requisitos y las restricciones de un sistema antes de comenzar su implementación con inteligencia artificial. La especificación funciona como una referencia tanto para el desarrollador como para el agente de IA, permitiendo que ambos trabajen sobre los mismos objetivos.

A diferencia del Vibe Coding, que se basa principalmente en generar código mediante prompts y realizar correcciones de manera iterativa, SDD propone un proceso más estructurado que integra la definición de requisitos, el diseño técnico, la implementación y las pruebas. Esto permite reducir la ambigüedad, facilitar la validación de las funcionalidades y disminuir el retrabajo. La IA se encarga de asistir en la implementación, mientras que el desarrollador mantiene el control sobre las decisiones y la calidad del producto.

## 2. La IA ha matado a Scrum

El segundo mapa mental sintetiza la transformación de Scrum con la llegada de la inteligencia artificial generativa. En el video se cuestiona cómo los sprints, las ceremonias, los roles y los artefactos tradicionales deben adaptarse a un contexto en el que los equipos pueden implementar funcionalidades en menos tiempo y trabajar con agentes de IA.

Una de las ideas principales es el modelo de doble carril, que diferencia dos enfoques:

- **Discovery:** busca explorar ideas, validar necesidades del negocio y construir prototipos rápidamente mediante técnicas como el Vibe Coding.
- **Delivery:** se enfoca en transformar las ideas validadas en soluciones preparadas para producción, considerando aspectos de arquitectura, calidad, seguridad y mantenibilidad mediante prácticas de ingeniería de software.

El video también plantea una evolución de las responsabilidades de los equipos, donde la supervisión de los agentes, la definición de especificaciones y la validación del código adquieren mayor importancia. Esto no implica necesariamente que Scrum deba desaparecer, sino que sus prácticas pueden requerir una adaptación a las nuevas dinámicas de desarrollo.

## 3. Entorno de desarrollo seleccionado: Kiro

Kiro es un entorno de desarrollo asistido por inteligencia artificial de AWS, basado en VS Code, que permite aplicar Spec-Driven Development. A partir de una necesidad expresada en lenguaje natural, el agente ayuda a definir los requisitos, elaborar un diseño técnico y organizar las tareas antes de comenzar a generar código. El desarrollador puede revisar y ajustar los documentos generados durante el proceso.

### 3.1. Funcionamiento y características principales

En el flujo de desarrollo basado en especificaciones, Kiro genera tres documentos principales, que normalmente se almacenan en `.kiro/specs/`:

| Documento | Función |
| --- | --- |
| `requirements.md` | Define las funcionalidades, historias de usuario y criterios de aceptación que debe cumplir el sistema. |
| `design.md` | Describe la arquitectura, los componentes y las decisiones técnicas para implementar los requisitos. |
| `tasks.md` | Divide el desarrollo en tareas concretas que pueden ser ejecutadas por el agente y revisadas por el desarrollador. |

Además de las Specs, Kiro ofrece **Steering**, para establecer reglas y estándares del proyecto; **Agent Hooks**, para automatizar acciones ante determinados eventos, como la modificación de archivos; y **MCP (Model Context Protocol)**, para integrar herramientas y fuentes de información externas. También permite trabajar mediante instrucciones directas en el chat para realizar cambios puntuales o explorar ideas rápidamente.

### 3.2. Experimentación con Kiro

Para experimentar con la herramienta, se seleccionó el desarrollo de una API REST para gestionar tareas utilizando Python y FastAPI. La aplicación contempla operaciones para crear, consultar, actualizar, completar y eliminar tareas, utilizando almacenamiento en memoria para mantener el proyecto sencillo.

El ejercicio consiste en definir la necesidad inicial mediante un prompt, revisar los documentos de especificación generados por Kiro y ejecutar las tareas de implementación. Posteriormente, se plantea validar los endpoints mediante Swagger y ejecutar las pruebas con `pytest` para comprobar que el código cumpla los requisitos establecidos.

Como prueba adicional, se propone incorporar un campo de prioridad a las tareas y permitir su filtrado. Esto permitirá analizar cómo el agente gestiona los cambios de requerimientos y mantiene la coherencia entre las especificaciones, el diseño, el código y las pruebas.

### 3.3. ¿Cómo apoya Kiro el proceso de desarrollo?

Kiro puede asistir en diferentes etapas del ciclo de vida del software, desde la identificación de las necesidades del negocio hasta el mantenimiento de la aplicación.

| Etapa | ¿Cómo ayuda Kiro? | Beneficio |
| --- | --- | --- |
| Análisis de requisitos | Organiza las necesidades del negocio y genera criterios de aceptación. | Reduce la ambigüedad y facilita la comprensión del alcance. |
| Diseño | Propone componentes, arquitectura y decisiones técnicas. | Permite estructurar la solución antes de implementarla. |
| Planificación | Descompone las funcionalidades en tareas de desarrollo. | Facilita la organización y el seguimiento del trabajo. |
| Implementación | Genera y modifica código considerando las especificaciones y el contexto del proyecto. | Reduce el trabajo repetitivo y agiliza el desarrollo. |
| Testing y QA | Asiste en la generación de pruebas, la identificación de errores y la validación de requisitos. | Facilita el aseguramiento de la calidad del software. |
| Despliegue | Puede asistir en la creación de Dockerfiles y configuraciones de CI/CD. | Reduce el trabajo manual en la preparación del despliegue. |
| Mantenimiento | Ayuda a diagnosticar errores, refactorizar código y actualizar la documentación. | Facilita la incorporación de cambios y la evolución del sistema. |

El principal valor diferencial de Kiro es que incorpora la IA desde las etapas iniciales del desarrollo, en lugar de limitarse a la generación de código. Esto permite que el desarrollador se concentre más en las decisiones técnicas, las necesidades del negocio y la validación del producto. Sin embargo, sigue siendo necesaria la supervisión humana para asegurar que las soluciones generadas cumplan los requisitos y los estándares de calidad y seguridad del proyecto.

