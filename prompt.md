### Prompt 1 (Chat GPT)

Eres un experto en producto y arquitectura, con experiencia en sistemas de gestión de candidatos.

Tenemos el reto de desarrollar el ATS (Applicant-Tracking System) del futuro para la startup LTI, por lo que inicialmente tenemos que dar respuestas a los siguientes 4 puntos. Adicionalmente comparto una serie de preguntas con las que se puede complementar la definicion de estos puntos.

1. Descripción breve del software LTI
2. valor añadido
3. Ventajas competitivas.
4. Explicación de las funciones principales.

#### Preguntas Complementarias

* ¿Qué funcionalidades básicas tiene un sistemas de gestión de candidatos?
Descríbemelas en un listado, ordenado de mayor a menor prioridad

* ¿Qué beneficios obtiene el cliente de un sistema de gestión de candidatos para considerar su uso?

* ¿Que alternativas tiene a usar un sistema de gestión de candidatos y cuando pueden ser relevantes?

* ¿Cómo es el customer journey normal de un cliente que usa un sistema de gestión de candidatos? Descríbeme paso a paso todas las interacciones

Las respuestas las entregas en formato .md para realizar documentacion, para enumerar en lugar de numeros usa viñetas
```
```

### Prompt 2 (Claude.ai)

Teniendo en cuenta el contexto anterior   "Pasa .md generado con el prompt 1"

Genera los 5 casos de uso mas relevantes y explicalos en forma detallada
Para CU genera diagrama de casos de uso en formato plantuml , aplicando buenas practicas
Dame la repuesta en formato .md

### Prompt 3 (Chat GPT)

*Eres un arquitecto de software experto. 

Identifica cuales son las  entidades del modelo de datos esenciales en un sistemas de gestión de candidatos y genera el modelo de datos que cubra entidades, atributos (nombre y tipo) y relaciones

La parte del texto damela en formato .md y adicional generame la imagen o diagrama

### Prompt 4 (Chat GPT)
En el diagrama no se ven reflejadas las relaciones, puedes general para plant uml 

### Prompt 5 (Chat GPT)
Generame el diseño del  sistema de gestión de candidatos a alto nivel, tanto explicado como diagrama, usand buenas practicas y aquitectura moderna

### Prompt 6 (Diagram GPT)

Adjunta respuesta del prompt anterior y pregunta leguaje de frontend, servicios de integracion y administrador de infraestructura

### Prompt 7 (Chat GPT)
Puedes diseñar 1 Diagrama C4 (Context, Containers, Components, Code)
Que llegue en profundidad a uno de los componentes del sistema 

Se agrega respuesta del prompt 5 en formato .md