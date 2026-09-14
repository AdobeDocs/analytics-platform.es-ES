---
title: Implementar Perspectivas de conversación
description: Aprenda a instrumentar la aplicación o el servicio de agente para las perspectivas de conversación.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 8e446c15e998e660b42a09681fe78b885711e41f
workflow-type: tm+mt
source-wordcount: '2257'
ht-degree: 6%
---
# Implementar Perspectivas de conversación

Para producir datos de conversación como eventos de experiencia XDM y asegurarse de que estos eventos de experiencia de conversación terminen en Adobe Experience Platform como conjuntos de datos, instrumente la aplicación o el servicio del agente para utilizar Perspectivas de conversación.

Este artículo documenta los pasos de implementación necesarios.

>[!PREREQUISITES]
>
>Debe tener un entorno de Experience Platform (organización y zona protegida) disponible para recopilar los datos.
Su organización de Adobe debe estar habilitada para los grupos de campo de conversación y agéntico experimental.

## Esquema y conjuntos de datos

Configure conjuntos de datos para los eventos de conversación principales: solicitud, respuesta, comentarios. Estos conjuntos de datos se pueden basar en el mismo esquema (por ejemplo, un esquema genérico de Perspectivas de conversación) o en esquemas individuales.
Puede definir conjuntos de datos independientes para preguntas, respuestas y comentarios, o bien combinar datos en conjuntos de datos. Por ejemplo, utilice un conjunto de datos para preguntas y respuestas y otro conjunto de datos para comentarios. O bien, utilice un solo conjunto de datos para todos los eventos de conversación.

El esquema utilizado para los conjuntos de datos de mensajes, respuestas y comentarios debe ampliar el esquema base de XDM Experience Event con los grupos de campos obligatorios. Y puede ampliar el esquema base de evento de experiencia XDM con grupos de campos adicionales.

### Grupo de campos Información de agente

El grupo de campos **[!UICONTROL Información de agente]** es un grupo de campos obligatorio y usa el objeto `agenticExperience`.

+++ Detalles

| Ruta de campo (notación de puntos) | Tipo | Valor de ejemplo | Notas |
|---|---|---|---|
| `conciergeID` | string | `"concierge-abc123"` | **Nuevo.** Identificador único del conserje |
| `name` | string | `"Brand Concierge"` | Nombre del conserje que combina un conjunto de agentes |
| `version` | string | `"1.0.0"` | Versión del conserje que combina un conjunto de agentes |
| `environment` | string | `"prod"` | Entorno desde el que se originó este evento (dev, stage, prod) |
| `mode` | string | `"release"` | Modo en el que se encuentra el agente (prueba, previsualización, lanzamiento) |
| `agents[]` | matriz | Consulte el objeto del agente a continuación | Matriz de agentes utilizados |
| `agents[].agentID` | string | `"agent-001"` | **Nuevo.** Identificador único del agente, al que hace referencia `skills[].agentID` más abajo |
| `agents[].name` | string | `"Chatbot Assistant"` | Nombre del agente |
| `agents[].version` | string | `"2.1.3"` | Versión del agente |
| `agents[].score` | número | `0.92` | Puntuación de confianza del agente en sus valores devueltos |
| `agents[].skills[]` | matriz | Consulte el objeto de aptitud a continuación | **Obsoleto**: use la matriz de `skills[]` de nivel superior que aparece a continuación, que posee la lista ordenada completa de llamadas de aptitudes y vincula cada una a su agente mediante `agentID` |
| `agents[].skills[].name` | string | `"Intent Recognition"` | Nombre de aptitud (matriz obsoleta) |
| `agents[].skills[].version` | string | `"1.0.0"` | Versión de aptitud (matriz obsoleta) |
| `agents[].skills[].score` | número | `0.95` | Puntuación de confianza de aptitudes (0-1) (matriz obsoleta) |
| `agents[].skills[].parameters[]` | matriz | Consulte los parámetros siguientes | Parámetros enviados a la aptitud (pares clave-valor) (matriz obsoleta) |
| `agents[].skills[].parameters[].key` | string | `"language"` | Clave de parámetro |
| `agents[].skills[].parameters[].value` | string | `"en-US"` | Valor de parámetro |
| `skills[]` | matriz | Consulte el objeto Invocación de aptitud a continuación | **Nuevo, experimental.** Lista completa y ordenada de invocaciones de aptitudes para esta experiencia, en todos los agentes. Reemplaza la matriz obsoleta por agente `agents[].skills[]` |
| `skills[].skillID` | string | `"skill-intent-recognition"` | Identificador de la definición de aptitud invocada |
| `skills[].skillInvocationID` | string | `"inv-9f2a-001"` | Identificador único de esta invocación de aptitud individual, coherente incluso con las reentregas. Clave de deduplicación al combinar cabinas de aptitudes descendentes |
| `skills[].name` | string | `"Intent Recognition"` | Nombre de la aptitud a la que se llamó |
| `skills[].version` | string | `"1.0.0"` | Versión de la aptitud invocada |
| `skills[].agentID` | string | `"agent-001"` | Identificador del agente que invocó esta aptitud, que corresponde a `agents[].agentID`. La agrupación de consumidores clave utiliza para ordenar habilidades dentro de un agente, ya que los subagentes se ejecutan en paralelo |
| `skills[].invocationSource` | string | `"main"` | Ya sea invocado por el bucle agéntico principal (`main`) o por un subagente (`subagent`) |
| `skills[].score` | número | `0.95` | Puntuación resultante de la coincidencia de la aptitud |
| `skills[].failed` | booleano | `false` | Indicador que indica que la ejecución de la aptitud ha fallado |
| `skills[].errorReason` | string | `"timeout"` | Motivo del error de la aptitud, cuando `failed` es verdadero |
| `skills[].sequenceNumber` | entero | `1` | Índice de aumento monotónico de esta llamada de habilidad dentro de una ejecución de agente único, no global, ya que los subagentes funcionan en paralelo. Los consumidores solicitan `agentID`, después `sequenceNumber` y después `timestamp` como desempate. Opcional |
| `skills[].timestamp` | cadena (fecha y hora) | `"2026-09-11T00:03:15Z"` | Hora de invocación de la aptitud, ISO 8601 UTC. Clave de orden usada después de `sequenceNumber`. Los productores siempre deben rellenar esto |
| `skills[].skillSource` | string | `"inline"` | Cómo se entregó la definición de aptitud al tiempo de ejecución: `inline` (cargado en línea en el contexto) o `deferred` (cargado bajo demanda) |
| `skills[].executionContext` | string | `"inline"` | Donde la aptitud se ejecuta en relación con el agente que realiza la llamada: `inline` o `forked` (se ejecuta en un contexto de subagente ramificado) |
| `skills[].reasoning.narration` | string | `"Recognized an intent to verify a geography fact"` | Explicación en lenguaje natural de por qué se llamó a esta aptitud |
| `skills[].parameters[]` | matriz | Consulte los parámetros siguientes | Parámetros transferidos a la aptitud |
| `skills[].parameters[].key` | string | `"language"` | Clave de parámetro |
| `skills[].parameters[].value` | string | `"en-US"` | Valor de parámetro |

+++

Para implementar eventos que propaguen el grupo de campos Información de agente con datos, debe asegurarse de lo siguiente:

* Configuración del agente

  * Cada agente tiene una combinación única de Id. de agente, nombre y versión.
  * Las puntuaciones del agente se normalizaron entre `0.0` y `1.0`.
  * Usar `agentID` para hacer referencia a agentes por invocación de aptitud.

* Invocación de aptitudes

  * Emitir solo una entrada por llamada de aptitud, en todos los agentes, en lugar de anidar aptitudes en cada agente.
  * Rellene skillInvocationID para que la fusión descendente pueda eliminar los eventos duplicados.
  * Solicite a los consumidores correctamente. Agrupar por `agentID` y ordenar por `sequenceNumber`, volviendo a `timestamp`. Es necesario realizar el pedido porque los subagentes se pueden ejecutar en paralelo
  * Utilice `invocationSource` y `executionContext` para distinguir las habilidades principales frente a las de subagente, y la ejecución en línea frente a la ejecución bifurcada.
  * Evite utilizar la matriz `agents[].skills[]` obsoleta. Si ha utilizado la matriz en el pasado, trate la matriz como un objeto de solo lectura.

* Parámetros de aptitud

  * Los parámetros utilizan el tipo de datos de valor clave XDM de Adobe y utilizan tipos de parámetros comunes para la configuración de idioma, los umbrales y las configuraciones de modelo. Por ejemplo, `"key":"language", "value":"en-US"`.

+++ Ejemplo de uso del grupo de campos Información de agente 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### Grupo de campos Evento de conversación

El grupo de campos **[!UICONTROL Evento de conversación]** es un grupo de campos obligatorio y usa el objeto `conversation`.

El objeto de conversación captura datos para:

#### Conversación

Un(a) `conversationID` único(a) identifica una conversación. Por ejemplo: `conversationID = "conv-001"`. El esquema también admite `conversationName`. Un nombre legible en lenguaje natural que describe el contexto general de la conversación, como: `France Geography Q&A`.

`conversationID` permite que todos los eventos de turnos relacionados se agrupen en la misma experiencia de conversación.

#### Turno

Un giro es un ciclo de interacción dentro de una conversación.

`turnID` Un(a) `turnID` único(a) identifica un turno. Por ejemplo:

`conversationID = "conv-001"`
`turnID = "turn-001"`

Se usan los mismos `conversationID` y `turnID` para correlacionar el aviso, la respuesta y los comentarios asociados con ese turno. Esa correlación funciona en registros que se entregan por separado o que terminan en diferentes conjuntos de datos.


#### Preguntar

Una solicitud es la entrada enviada al agente. En la mayoría de los casos de clientes, esta entrada es la pregunta, la solicitud, la instrucción o el mensaje del usuario.

La solicitud utiliza la siguiente representación: `conversation.prompt`

Los campos de solicitud importantes incluyen:

| Campo | Significado |
|---|---|
| `prompt.source` | Quién o qué produjo el mensaje, normalmente usuario final. |
| `prompt.raw[]` | Uno o más segmentos de contenido sin procesar. |
| `prompt.raw[].text` | El texto o contenido real del mensaje. |
| `prompt.raw[].purpose` | El propósito del contenido, como la entrada del usuario o el vínculo. |

Una solicitud puede contener varios segmentos sin procesar. Por ejemplo, un usuario introduce texto e incluye una dirección URL.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### Respuesta

Una respuesta es el contenido devuelto por el agente u otra parte encuestada.

`conversation.response` Un(a) `responseID` único representa la respuesta.

Los campos de respuesta importantes incluyen:

| Campo | Significado |
|---|---|
| `response.source` | Quién o qué produjo la respuesta. |
| `response.raw[]` | Uno o más segmentos de contenido de respuesta. |
| `response.raw[].text` | El texto o contenido de la respuesta. |
| `response.raw[].purpose` | El propósito del segmento de contenido. |

Los tipos de fuentes documentados incluyen:

| Fuente | Significado |
|---|----|
| `bot` | Respuesta automatizada del agente. |
| `canned` | Respuesta predefinida o con plantilla. |
| `concierge` | Respuesta del agente humano. |
| `end-user` | Contenido humano generado por el usuario, cuando corresponda. |

#### Comentarios

Los comentarios son la evaluación explícita o la reacción del usuario a la interacción.

La estructura de comentarios incluye: `conversation.feedback`.

Ejemplos:

* `feedback.raw[].text: "Great help"`
* feedback.rating.score: 1
* feedback.rating.Classification: &quot;Pulgares hacia arriba&quot;
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

El rango de puntuación de clasificación documentado es de `-1.0` a `1.0`.

Un evento de comentarios puede representarse como un evento de solo comentarios mediante: `eventType = "conversation.feedback"`.

Cuando los comentarios se apliquen a un turno en particular, conserva los `conversationID` y `turnID` adecuados para que el mezclador de conversaciones pueda asociar los comentarios con la interacción relevante.


#### Señal

Una señal es una observación analítica estructurada acerca del contenido de una conversación. El servicio de extracción de señales extrae señales.

Una señal tiene los siguientes campos.

| Campo | Significado |
|---|----|
| `scope` | El rango de entrada utilizado para derivar la señal, como el turno o la conversación hasta la fecha. |
| `name` | El identificador de señal, como sujetos, intenciones, tonos o opinión. También se admiten nombres de señal definidos por el productor. |
| `type` | El tipo de valor: cadena, número o booleano. |
| `values[]` | Uno o más valores asociados con la señal. |
| `stringValue` | Un valor de señal de cadena, como una intención, un tono o un asunto. |
| `numberValue` | Un valor de señal numérica, como una puntuación de opinión. |
| `booleanValue` | Un valor de señal true/false. |
| `confidence` | Confianza opcional del productor en el valor de la señal, normalmente entre 0 y 1. |
| `qualifiers[]` | Descriptores opcionales que agregan contexto a un valor de señal. |
| `metadata[]` | Metadatos clave/valor definidos por el productor opcionales. |


#### Conversación

Consulte a continuación todos los detalles de un objeto de conversación.

+++ Detalles 

| Ruta de campo (notación de puntos) | Tipo | Valor de ejemplo | Notas |
|---|---|---|---|
| `conversationID` | string | `"conv-001"` | Agrupa varios turnos |
| `conversationName` | string | `"France Geography Q&A"` | **Nuevo.** Nombre dado a una conversación que representa su contexto general |
| `turnID` | string | `"turn-001"` | ID único para este turno |
| `prompt.source` | string | `"end-user"` | Source del mensaje, otras opciones pueden incluir un valor almacenado en caché, un valor conservado, etc. |
| `prompt.raw[]` | matriz | Consulte el objeto sin procesar a continuación | Datos sin procesar |
| `prompt.raw[].text` | string | `"What is the capital of France?"` | Contenido de texto real |
| `prompt.raw[].purpose` | string | `"User Input"` | Objetivo de este segmento de texto |
| `response.source` | string | `"bot"` | Source de respuesta |
| `response.raw[]` | matriz | Consulte el objeto sin procesar a continuación | Datos de respuesta sin procesar |
| `response.raw[].text` | string | `"The capital of France is Paris."` | Contenido de texto de respuesta |
| `response.raw[].purpose` | string | `"main"` | Objetivo del segmento de respuesta, otras opciones pueden incluir vínculos, imágenes, etc. |
| `feedback.source` | string | `"end-user"` | Source de comentarios |
| `feedback.raw[]` | matriz | Consulte el objeto sin procesar a continuación | Datos de comentarios sin procesar |
| `feedback.raw[].text` | string | `"Great help"` | Texto de comentarios |
| `feedback.raw[].purpose` | string | `"free-form text"` | Objetivo del segmento de comentarios, otras opciones pueden incluir capturas de pantalla, medios, etc. |
| `feedback.rating.score` | número | `1` | Puntuación numérica de -1,0 a 1,0 |
| `feedback.rating.classification` | string | `"Thumbs Up"` | Clasificación de clasificación |
| `feedback.rating.reasons[]` | matriz | `["Accurate", "Quick response"]` | Matriz de motivos de clasificación |
| `signals[]` | matriz | Consulte el objeto de señal a continuación | Señales derivadas basadas en este evento y la conversación hasta la fecha. Cada entrada es una señal con un solo nombre y su propio ámbito |
| `signals[].scope` | string | `"turn"` | Ámbito de las entradas de las que se deriva este conjunto de señales (turno, conversación hasta la fecha, últimos N giros, comentarios) |
| `signals[].attributes` | objeto | Consulte los atributos a continuación | **Obsoleto.** Contenedor de atributos de señal. Cada atributo es un objeto con valor o valores en él. Esto es para satisfacer la necesidad anticipada de admitir la población de información de ML/agente utilizada para generar la señal. |
| `signals[].attributes.subjects` | objeto | Consulte los temas siguientes | **Obsoleto.** Contenedor de asuntos |
| `signals[].attributes.subjects.values[]` | matriz | Consulte los valores de asunto a continuación | **Obsoleto.** Matriz de valores de asunto |
| `signals[].attributes.subjects.values[].phrase` | string | `"product pricing"` | **Obsoleto.** Frase o palabra clave extraída de la entrada dentro del ámbito definido |
| `signals[].attributes.subjects.values[].qualifiers[]` | matriz | `["important", "urgent"]` | **Obsoleto.** Lista de calificadores para la frase |
| `signals[].attributes.intents` | objeto | Consulte Intenciones a continuación | **Obsoleto.** Contenedor de intenciones |
| `signals[].attributes.intents.values[]` | matriz | `["make a purchase", "learn more"]` | **Obsoleto.** Intenciones derivadas de la entrada con ámbito |
| `signals[].attributes.tones` | objeto | Ver tonos a continuación | **Obsoleto.** Contenedor de tonos |
| `signals[].attributes.tones.values[]` | matriz | `["thrilled", "contemplative"]` | **Obsoleto.** Tonos derivados de la entrada con ámbito |
| `signals[].attributes.sentiment` | objeto | Consulte la opinión a continuación | **Obsoleto.** contenedor de opinión |
| `signals[].attributes.sentiment.value` | número | `0.71` | **Obsoleto.** Puntuación de -1 (negativa) a 1 (positiva) que indica opinión |
| `signals[].name` | string | `"sentiment"` | **Nuevo** (reemplaza el contenedor `attributes` obsoleto). Identificador de esta señal, por ejemplo, &quot;sujetos&quot;, &quot;intenciones&quot;, &quot;tonos&quot;, &quot;opinión&quot; o cualquier nombre definido por el productor: los productores pueden agregar nuevos tipos de señal sin cambiar el esquema |
| `signals[].type` | string | `"number"` | **Nuevo.** Tipo de datos de los valores de esta señal (`string`, `number` o `boolean`): indica a los consumidores qué campo de valor escrito se rellena en cada entrada de `values[]` |
| `signals[].values[]` | matriz | Consulte el objeto values a continuación | Uno o más valores para esta señal |
| `signals[].values[].stringValue` | string | `"curious"` | Se rellena cuando `type` es &quot;cadena&quot;, un valor categórico como intención, tono o frase extraída |
| `signals[].values[].numberValue` | número | `0.71` | Se rellena cuando `type` es &quot;número&quot;; por ejemplo, una puntuación de opinión de -1 a 1 o una intensidad |
| `signals[].values[].booleanValue` | booleano | `true` | Se rellena cuando `type` es &quot;booleano&quot; (un indicador verdadero/falso) |
| `signals[].values[].confidence` | número | `0.9` | **Nuevo.** Confianza que el productor asigna a este valor, de 0 a 1 |
| `signals[].values[].qualifiers[]` | matriz | `["important", "urgent"]` | Descriptores adicionales para este valor, similares a las palabras clave pero más significativos |
| `signals[].values[].metadata[]` | matriz | Consulte los parámetros siguientes | **Nuevo.** Metadatos definidos por el productor para este valor como pares clave/valor, p. ej. contexto sobre el ML/agente que generó la señal |

+++


El servicio de extracción de señales rellena el objeto `signals` para el conjunto de datos de señales.

El contenedor `signals[].attributes.{subjects,intents,tones,sentiment}` anterior está obsoleto.


### Grupos de campo adicionales

Puede agregar grupos de campos opcionales al esquema que utiliza para los conjuntos de datos de solicitud, respuesta y comentarios. Por ejemplo:

* **Detalles web** grupo de campos. Para capturar los detalles de la página web en la que se incrustó la conversación.
* **Detalles de Commerce** grupo de campos. Para recopilar los detalles del producto recomendado mencionado como parte de la conversación.



El cliente es responsable de producir los eventos de conversación de origen. Posteriormente, Adobe Platform realiza la extracción de señales y la mezcla de datos. El cliente no necesita implementar los servicios de extracción o fusión de señales.

Este documento cubre los requisitos de entrada del MVP de Conversation Insights y la Actualización del esquema agéntico actual. No incluye las funciones de Conversation Insights 1.0 ni los requisitos de la versión posterior.

### Tipo de evento

Debe establecer uno de los siguientes valores para `eventType` (cadena) para cada evento de conversación:

| Valor | Explicación |
|---|---|
| `conversation turn` | Turno de conversación completo con petición y respuesta |
| `conversation recommendation` | Recomendación basada en la conversación |
| `conversation feedback` | Evento de solo comentarios |


### Tipo de Source

Debe establecer uno de los siguientes valores para `source` para cada objeto `prompt`, `response` o `feedback` en un evento:

| Valor | Descripción |
|---|---|
| `end-user` | Entrada de usuario humano |
| `bot` | Respuesta automatizada del agente |
| `canned` | Respuesta predefinida/con plantilla |
| `concierge` | Respuesta del agente humano |

### Tipo de propósito (texto sin procesar)

Debe establecer uno de los siguientes valores para el atributo `purpose` en cualquier elemento del objeto `raw` en un objeto `prompt`, `response` o `feedback`.

| Valor | Descripción |
|---|---|
| `User Input` | Entrada principal del usuario |
| `main` | Contenido de respuesta principal |
| `advertisement` | Contenido promocional |
| `citation` | Vínculos de origen/referencia |
| `link` | Vínculos externos |
| `image` | Referencias de imagen |
| `enum picker` | Selección de comentarios estructurada |


### Ejemplo

Consulte a continuación un ejemplo de uso del grupo de campos Evento de conversación en varios escenarios.

+++ Detalles 

>[!BEGINTABS]

>[!TAB Ejemplo del evento Turn]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB Ejemplo de evento de respuesta]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB Ejemplo de evento de comentarios]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB Ejemplo de evento de recomendaciones de productos]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## Recopilación de datos

Utilice la siguiente estrategia de recopilación de datos para las Perspectivas de conversación.


### Tipos de eventos

El servicio o la aplicación del agente envía un evento lo antes posible. Asegúrese de que la aplicación o el servicio no espere una respuesta antes de enviar el mensaje con la información disponible en el momento del evento.

Esta recomendación implica que:

* Los objetos de solicitud, respuesta y comentarios se rellenan de forma independiente y no se deben forzar para que formen parte de un solo evento.
* Se esperan varios eventos con los mismos `conversationID` y `turnID` en los conjuntos de datos.

### Correlación de eventos

La aplicación o el servicio del agente debe conservar los identificadores estables en todos los eventos relacionados.

| Ruta de campo | Descripción |
|---|---|
| `conversation.conversationID` | Identificador único de la conversación general. |
| `conversation.turnID` | Identificador único de un giro individual dentro de la conversación. |
| `_id` | Identificador de registro de evento de experiencia. |
| `timestamp` | Hora a la que se produjo el evento. |
| `eventType` | Identifica el tipo de evento de conversación. |

* Se debe usar el mismo(a) `conversationID` para todos los eventos que pertenecen a la misma conversación.

* Se debe usar el mismo `turnID` para el aviso, la respuesta y cualquier comentario asociado con el mismo turno. Pueden existir varios eventos con el mismo `turnID` en los conjuntos de datos de mensajes, respuestas y comentarios.

La aplicación o el servicio del agente genera ID que permanecen estables durante los reintentos o la reentrega. Esto permite que el procesamiento descendente asocie correctamente los eventos y evite los eventos duplicados no deseados.

## Extracción de señal

La extracción de señales se produce después de la recopilación de datos. La aplicación o el servicio del agente no rellenan señales adicionales.

+++ Ejemplo de evento de giro con señales

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## Combinación de datos

El servicio de mezcla de conversaciones combina eventos de conjuntos de datos de mensajes, respuestas, comentarios y eventos de señal en un conjunto de datos de eventos de conversación combinados dedicado. Ese conjunto de datos se utiliza en Customer Journey Analytics como parte de una conexión. Los componentes de ese conjunto de datos se agregan a las vistas de datos especificadas para una configuración de Perspectivas de conversación.
