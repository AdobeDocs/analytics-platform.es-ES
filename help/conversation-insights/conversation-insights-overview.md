---
title: Información general de Conversation Insights
description: Obtenga información acerca del valor y la terminología de Perspectivas de conversación y descubra cómo funciona Perspectivas de conversación.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%
---
# Perspectivas de conversación

Conversation Insights le permite analizar las conversaciones a partir de las experiencias de agente que ofrece a sus clientes. Estas experiencias del agente pueden basarse en modelos de lenguaje de gran tamaño (LLM) o en conversaciones humanas. Conversation Insights analiza las conversaciones a escala y proporciona contexto para estas conversaciones dentro del recorrido completo del cliente. A través de Conversation Insights, puede comprender el impacto de los agentes en los resultados reales del usuario.

Conversation Insights soluciona los problemas que podría experimentar. Por ejemplo:

* No tiene insight sobre lo que sucede cuando los clientes interactúan con agentes (LLM o humanos) en el contexto del recorrido.
* No tiene la capacidad de comprender lo siguiente:
  * lo que los agentes les dicen a los clientes a escala.
  * cómo los clientes interactúan con los agentes a escala.
  * ¿Cuál es el impacto general en los KPI como resultado de estas interacciones?
* Puede crear experiencias auténticas para adaptarse a las cambiantes preferencias de usuario.

Con Perspectivas de conversación puede comprender lo siguiente:

* Lo que los agentes les dicen a los usuarios.
* Lo que los usuarios piden a los agentes.
* Cómo afectan las conversaciones a los KPI.

Puede determinar el rendimiento de sus agentes con respecto a las directivas, la adherencia de los agentes a las directrices de marca y si el coste de funcionamiento de los agentes está justificado por los resultados.


## Conceptos

En un nivel superior en Perspectivas de conversación, una [conversación](#conversation) es una secuencia de [turnos](#turn) correlacionados. Cada turno puede haber enviado de forma independiente [prompt](#prompt), [response](#response) y [feedback](#feedback) eventos. Las [señales](#signal) son observaciones estructuradas que se derivan de la conversación, mientras que el conjunto de datos combinado reúne los eventos y señales de origen para la generación de informes.

Conversation Insights analiza las interacciones del agente en dos niveles:

* Nivel de [conversación](#conversation): la interacción completa entre un usuario y un agente, que contiene varias vueltas.
* [Activar](#turn) nivel: un ciclo de interacción dentro de esa conversación, que consiste en un mensaje de usuario y una respuesta del agente.

La aplicación o el servicio del agente emite eventos de experiencia relacionados con la conversación en Experience Platform. Los datos de evento de preguntas, respuestas y comentarios pueden llegar de forma independiente. Los servicios de Platform correlacionan y fusionan esos eventos en un registro de nivel de giro, enriquecen opcionalmente los datos con señales extraídas y hacen que los datos resultantes estén disponibles para los informes de Customer Journey Analytics.

### Conversación

Una conversación es la interacción completa entre un usuario y un agente. Puede contener una o varias vueltas.

Una conversación es el nivel de contenedor o agrupación. Ese contenedor es útil para preguntas como las siguientes:

* ¿Cuántas conversaciones ocurrieron?
* ¿Cuál fue el tema general de una conversación?
* ¿Cómo cambió la opinión a lo largo de una conversación?
* ¿Qué conversaciones finalmente llevaron a una conversión?

Para obtener detalles de implementación, consulte el objeto [conversación](./conversation-insights-implement.md#conversation) en la documentación de [Implementar perspectivas de conversación](./conversation-insights-implement.md).

### Turno

Un giro es un ciclo de interacción dentro de una conversación.

Un giro típico consiste en

* Mensaje de usuario
* Respuesta del agente
* (opcional) Comentarios del usuario

El turno es el objeto analítico principal para fines de elaboración de informes. El servicio de licuadora de conversación combina la información disponible de aviso, respuesta, comentarios y señales en registros de nivel de giro.

Para obtener detalles de implementación, consulte el objeto [turn](./conversation-insights-implement.md#turn) en la documentación de [Implementar perspectivas de conversación](./conversation-insights-implement.md).

### Preguntar

Una solicitud es la entrada enviada al agente. En la mayoría de los casos de clientes, esta entrada es la pregunta, la solicitud, la instrucción o el mensaje del usuario.

Una solicitud puede contener varios segmentos sin procesar. Por ejemplo, un usuario introduce texto e incluye una dirección URL.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`

El mensaje es la entrada principal de la que Conversation Insights puede derivar información analítica como la siguiente:

* La intención del usuario
* El asunto o tema
* El tono del usuario
* La opinión del usuario
* Otras señales admitidas

Para obtener detalles de implementación, consulte el objeto [prompt](./conversation-insights-implement.md#prompt) en la documentación de [Implementar perspectivas de conversación](./conversation-insights-implement.md).

### Respuesta

Una respuesta es el contenido devuelto por el agente u otra parte encuestada.

Una respuesta suele contener diferentes tipos de contenido. Por ejemplo:

* Respuesta principal
* Cita o referencia
* Vínculo
* Imagen
* Contenido promocional

Esta distinción es útil porque el análisis debe separar la respuesta principal de los vínculos de soporte, las citas, los anuncios u otros componentes de respuesta.

Para obtener detalles de implementación, consulte el objeto [response](./conversation-insights-implement.md#response) en la documentación de [Implementar Perspectivas de conversación](./conversation-insights-implement.md).

### Comentarios

Los comentarios son la evaluación explícita o la reacción del usuario a la interacción.

Los comentarios pueden contener:

* Texto de comentarios de forma libre
* Una clasificación numérica.
* Una clasificación de clasificación
* Uno o más motivos para la clasificación

Los comentarios no están necesariamente disponibles al mismo tiempo que el mensaje o la respuesta. Puede enviar los comentarios más adelante desde la aplicación o el servicio del agente, una vez que el usuario haya evaluado la respuesta.

Para obtener más información sobre la implementación, consulte el objeto [feedback](./conversation-insights-implement.md#feedback) en la documentación de [Implementar perspectivas de conversación](./conversation-insights-implement.md).

### Señal

Una señal es una observación analítica estructurada acerca del contenido de una conversación. El servicio de extracción de señales extrae señales.

Para obtener detalles de implementación, consulte el objeto [signal](./conversation-insights-implement.md#signal) en la documentación de [Implementar perspectivas de conversación](./conversation-insights-implement.md).


### Agente

Para identificar la aplicación o el servicio del agente, se requiere la información del agente para cada evento de Conversation Insights (solicitud, respuesta, comentarios, señal).

#### Invocaciones de aptitudes

Si la aplicación de experiencia del agente admite la invocación de habilidades que representan capacidades invocadas durante el procesamiento, puede agregar estas invocaciones de habilidades como parte del grupo de campos de información del agente.

Para obtener detalles de implementación, consulte el grupo de campos [información auténtica](./conversation-insights-implement.md#agentic-information-field-group) en la documentación de [Implementar perspectivas de conversación](./conversation-insights-implement.md).

## Funcionamiento

Conversation Insights se basa en tres funcionalidades principales:

* **Recopilación de datos**: permite a los usuarios comprender cómo realizan sus tareas LLM y los agentes. Se requiere la recopilación de datos para recopilar todos los puntos de datos necesarios.
* **Extracción de señales y fusión de conversaciones**: transforma las respuestas y mensajes no estructurados (también conocidos como giros) en puntos de datos que se pueden registrar, como intención y opinión. Para que los usuarios puedan informar sobre esos puntos de datos a escala.
* **Creación de informes**: para determinar la eficacia y el retorno de la inversión de un agente, analice las conversaciones a escala en el contexto del recorrido del cliente.

A continuación se muestra el proceso general de recopilación de datos, extracción de señales y fusión de conversaciones.

![Ilustración de cómo funciona Conversation Insights](assets/conversation-insights.png){zoomable="yes"}

| | Descripción |
|---|---|
| 1 | Instrumenta la aplicación o el servicio del agente para crear eventos que contengan los conjuntos de datos ![CommentText](/help/assets/icons2/CommentText.svg), respuestas ![CommentReply](/help/assets/icons2/CommentReply.svg) y comentarios ![Feedback](/help/assets/icons2/Feedback.svg).<br/>Para obtener más información sobre cómo instrumentar su aplicación o servicio de agente, consulte la [documentación de implementación](./conversation-insights-implement.md). |
| 2 | El servicio de extracción de señales extrae señales de los mensajes ![CommentText](/help/assets/icons2/CommentText.svg), las respuestas ![CommentReply](/help/assets/icons2/CommentReply.svg) y los conjuntos de datos de comentarios ![Feedback](/help/assets/icons2/Feedback.svg) como eventos de señal ![OnAir](/help/assets/icons/OnAir.svg) y almacena estos eventos de señal en un nuevo conjunto de datos.<br>Este paso se implementa como parte de la definición de una [configuración de Perspectivas de conversación](./conversation-insights-configure.md). |
| 3 | El servicio de mezcla de conversación combina los eventos de los mensajes ![CommentText](/help/assets/icons2/CommentText.svg), las respuestas ![CommentReply](/help/assets/icons2/CommentReply.svg), los comentarios ![Feedback](/help/assets/icons2/Feedback.svg) y las señales ![OnAir](/help/assets/icons/OnAir.svg) conjuntos de datos de eventos y genera los eventos ![Merge](/help/assets/icons/Merge.svg)combinados en un nuevo conjunto de datos.<br>Este paso se implementa como parte de la definición de una [configuración de Perspectivas de conversación](./conversation-insights-configure.md). |
| 4 | El conjunto de datos ![Merge](/help/assets/icons/Merge.svg) combinado pasa a formar parte de la conexión y los componentes definidos en el esquema utilizado para el conjunto de datos combinado pasan a formar parte de la vista de datos.<br>Este paso se implementa como parte de la definición de una [configuración de Perspectivas de conversación](./conversation-insights-configure.md). |

