---
title: Integración de LLM Optimizer
description: Integración de LLM Optimizer con Customer Journey Analytics
feature: Experience Platform Integration
role: User
feature_v2: id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
source-git-commit: 3aa4e0c98e9a3e4163dad992e598638892fc88cd
workflow-type: tm+mt
source-wordcount: 2539
ht-degree: 2%

---


# Integración de LLM Optimizer

[Adobe LLM Optimizer](https://experienceleague.adobe.com/es/docs/llm-optimizer/using/home){target="_blank"} es una aplicación generativa con prioridad de IA para la optimización de motores generativos, diseñada para ayudar a las marcas a mejorar su visibilidad, precisión e influencia en entornos de búsqueda impulsados por IA. LLM Optimizer proporciona perspectivas sobre la presencia de marca en respuestas generadas por IA, ofrece recomendaciones de contenido prescriptivo y automatiza las correcciones de optimización.

La IA se ha convertido en un canal de descubrimiento principal. Los agentes de LLM, como ChatGPT, Claude, Copilot y Perplexity, rastrean el contenido de la marca.

>[!PREREQUISITES]
>
>Debe tener una oferta de LLM Optimizer de pago aprovisionada y conectada a la configuración de Experience Platform a través del conector administrado.


>[!IMPORTANT]
>
>Como parte de esta integración, algunos procesos temporales de datos de LLM Optimizer se producen en Estados Unidos. En última instancia, los datos se almacenan en la región designada, según la configuración del contrato de Customer Journey Analytics.


## Casos de uso

Puede beneficiarse de la integración entre Customer Journey Analytics y LLM Optimizer de dos maneras:

* **Integración entrante**: utilice los datos de LLM Optimizer en Customer Journey Analytics para medir el tráfico impulsado por LLM (rastreadores de bots, solicitudes RAG, actividad del agente) junto con los datos web, móviles y de otro tipo existentes. Por ejemplo, puede realizar lo siguiente:

  * Mida el tráfico impulsado por LLM por fuente de agente junto con los canales tradicionales.

  * Identificar el contenido que consume mucho los LLM pero que no tiene el rendimiento suficiente en la conversión humana.

  * Detectar dónde fallan las solicitudes del agente LLM en las rutas críticas.

  * Comparar la demanda de bots LLM de una página con las conversiones e ingresos de esa página en los datos web, coincidiendo en los niveles de URL y host.

* **Integración saliente**: envíe datos de rendimiento de Customer Journey Analytics a LLM Optimizer para que pueda optimizar la visibilidad de IA para las fuentes de LLM que le envían tráfico valioso, como ChatGPT o Perplexity. Por ejemplo, puede realizar lo siguiente:

  * Vea qué fuentes de LLM envían visitantes humanos que siguen convirtiendo o generando ingresos. Customer Journey Analytics mide esto a partir del tráfico web al que se hace referencia, no del conjunto de datos de bots.
  * Clasifique las fuentes de LLM según el valor descendente de los visitantes humanos que envían y, a continuación, centre su trabajo de visibilidad de la IA en las fuentes que funcionan mejor.


## Integración entrante

El tráfico LLM llega a su sitio de dos maneras. Customer Journey Analytics mide cada trayecto desde una fuente de datos diferente.

La primera forma es con una persona que lee una respuesta de IA y luego hace clic en el sitio. Esa visita ejecuta la misma JavaScript que recopila el resto de los datos web. Por lo tanto, los datos web de Customer Journey Analytics existentes incluyen la visita y el dominio de referencia que le envió el usuario, por ejemplo, chatgpt.com. Customer Journey Analytics no etiqueta estas visitas como tráfico de IA por sí solo. Para identificarlos y agruparlos, se crea un campo derivado en la conexión que coincide con los dominios de referencia de IA y, a continuación, se generan segmentos e informes sobre ese campo. Consulte [Campos derivados](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. No necesita el conjunto de datos de LLM Optimizer para este tráfico humano.

La segunda forma es un bot o agente que solicite sus páginas directamente. Esto incluye rastreadores que crean un índice de IA y recuperaciones en directo que se producen cuando un usuario envía un mensaje a un asistente de IA. Estas solicitudes no ejecutan ningún JavaScript, por lo que los datos web existentes no los registran. El conjunto de datos de LLM Optimizer captura este tráfico desde la capa de CDN. El resto de esta sección describe ese conjunto de datos.

### Incorporación del conjunto de datos en Customer Journey Analytics

El conector administrado de LLM Optimizer envía los datos a Experience Platform como un conjunto de datos de resumen. Para medirlo en Customer Journey Analytics, debe completar dos pasos de configuración:

1. Cree una conexión que incluya el conjunto de datos de LLM Optimizer. Consulte [Crear o editar una conexión](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}.
2. Cree una vista de datos sobre esa conexión. La vista de datos hace que las dimensiones y métricas siguientes estén disponibles en Analysis Workspace. Ver [Crear o editar una vista de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}.

El conjunto de datos:

* Utiliza [conjuntos de datos de resumen](/help/data-views/summary-data.md) basados en la clase Métricas de resumen de XDM.
* Agrupa datos por dirección URL y host, hora y características de solicitud como tipo de bot, proveedor de CDN y estado.

>[!NOTE]
>
>El conjunto de datos de LLM Optimizer contiene datos agregados. No contiene ninguna PII, como un identificador de usuario, indicadores o respuestas.
>

Como es un conjunto de datos de resumen, puede tratarlo como un conjunto de datos de búsqueda y unirlo a un conjunto de datos de evento en una clave de URL completa.

LLM Optimizer proporciona esta clave en la dimensión **URL de CDN**. Combina el host y la ruta solicitada en una sola URL completa normalizada, de forma similar a como Customer Journey Analytics almacena los datos web. El éxito de la unión depende de su propia recopilación de datos. El conjunto de datos de evento necesita un campo de dirección URL completo equivalente o un campo que se pueda analizar y normalizar para que coincida con la dirección URL que proporciona LLM Optimizer. Cuando ambos lados se resuelven en la misma dirección URL completa, el registro de LLM Optimizer coincide con la página correspondiente de los datos web.

### Acerca del conjunto de datos

LLM Optimizer lee los registros de acceso de CDN en el servidor y extrae registros en los que el solicitante es un bot o un agente automatizado. Como los datos proceden del nivel de CDN, LLM Optimizer captura solicitudes de bots que no activan ninguna etiqueta de JavaScript. Las herramientas estándar de análisis web omiten este tráfico por completo.

El conjunto de datos utiliza el grupo de campos **Resumen de solicitudes de CDN**. Cada campo se encuentra debajo de un objeto `cdn`, por lo que los nombres de campo de las tablas siguientes toman la forma `cdn.<name>`, por ejemplo `cdn.url` y `cdn.botType`.

Cada registro describe una combinación de host, ruta URL, tipo de bot, proveedor de CDN, código de estado, referente, host reenviado y tiempo hasta el primer byte durante una hora. Cuando la misma combinación aparece más de una vez por hora, Customer Journey Analytics combina esos registros en una fila y aumenta el recuento de solicitudes. Utilice la métrica **Recuento de solicitudes de CDN** para medir el volumen. No utilice el recuento de filas.

### Dimensiones

Las siguientes dimensiones están disponibles para su uso como componentes en una vista de datos una vez que haya configurado una conexión que incluya un conjunto de datos de LLM Optimizer. La columna **Campo** muestra el campo de origen en el grupo de campos Resumen de solicitudes de CDN.

| Dimensión | Campo | Descripción |
|-----------|-------|-------------|
| URL de CDN | `cdn.url` | Dirección URL completa normalizada para la solicitud, que se utiliza como clave de unión. LLM Optimizer combina el host y la ruta solicitada en una sola dirección URL y la normaliza para que coincida con el formulario de URL completa que Customer Journey Analytics almacena para los datos web. Utilice esta dimensión para unir el conjunto de datos de búsqueda de LLM Optimizer a un conjunto de datos de evento que tenga un campo de URL completa equivalente. Incluye el host y la ruta, pero no el esquema. |
| Ruta de URL de CDN | `cdn.path` | Ruta de URL sin procesar y cadena de consulta que solicitó el agente, tal como la entregó la CDN. No incluye el esquema ni el host. Utilícelo cuando necesite la ruta solicitada exacta, en lugar de la clave de unión normalizada. |
| Host de CDN | `cdn.host` | El nombre de host que recibió la solicitud, por ejemplo, www.example.com. Este host también forma parte de la clave de unión de URL de CDN. Un conjunto de datos puede contener varios hosts cuando una organización tiene varios subdominios en la misma cuenta de CDN. |
| Tipo de bot de CDN | `cdn.botType` | Clasificación de LLM Optimizer del agente solicitante. Los valores abarcan rastreadores de búsqueda clásicos, rastreadores de índice de IA y agentes de captura en directo de IA. Consulte las [categorías de agentes de bots](#bot-agent-categories) a continuación para ver la taxonomía completa. |
| Agente de usuario de CDN | `cdn.userAgent` | La cadena del agente de usuario sin procesar del registro de CDN. Resulta útil para distinguir subtipos dentro de una clasificación de bots o para validar la clasificación asignada por LLM Optimizer. |
| Estado HTTP de CDN | `cdn.status` | El código de estado de respuesta HTTP. Indica si el bot recibió el contenido que solicitó. Consulte los [Códigos de estado](#status-codes) a continuación para obtener instrucciones de interpretación específicas para el tráfico de IA. |
| Proveedor de CDN | `cdn.cdnProvider` | Qué CDN gestionó la solicitud. Los valores son `akamai`, `byocdn-akamai`, `byocdn-fastly` y `byocdn-cloudfront`. El prefijo `byocdn-` indica la ruta de recopilación de registros, no un proveedor de CDN diferente. Un conjunto de datos puede contener varios valores cuando una organización tiene hosts detrás de diferentes configuraciones de CDN. |
| Referente de CDN | `cdn.referer` | El valor del encabezado Referente HTTP del registro de CDN. A menudo, vacío para el tráfico de bots. Cuando está presente, puede indicar qué producto o dominio de IA activó la recuperación. Por ejemplo, chat.openai.com. |
| Host reenviado de CDN | `cdn.xForwardedHost` | El valor del encabezado X-Forwarded-Host, si lo hay. Es relevante cuando la solicitud pasó a través de un proxy inverso o una capa de blindaje de CDN antes de llegar al origen. |
| Fecha de evento de CDN | Derivado de la marca de tiempo del registro | La parte de fecha de la marca de tiempo por lotes horarios de este registro. |
| Hora del evento de CDN | Derivado de la marca de tiempo del registro | La parte de hora de la marca de tiempo por lotes horarios de este registro. |

### Categorías de agentes de bots

La dimensión **Tipo de bot de CDN** organiza a los agentes en tres categorías. Cada categoría responde a una pregunta analítica diferente.

**rastreadores de búsqueda clásicos** indexan el contenido de los motores de búsqueda tradicionales. Utilice esta categoría para medir la visibilidad del contenido en los motores de búsqueda tradicionales.

| Valor de tipo de bot | Proveedor | Descripción |
|---|---|---|
| `GoogleBot` | Google | rastreador del índice de búsqueda principal de Google. También sirve Google Discover y Google News. |
| `BingBot` | Microsoft | Rastreador de índice de búsqueda de Bing. También alimenta el índice de conexión a tierra web de Microsoft Copilot. |

**rastreadores de índice de IA** rastrean contenido para crear o actualizar el corpus de formación o el índice de búsqueda de un producto de IA. Estos rastreadores están preparando la base de conocimientos de un modelo, no respondiendo a una solicitud de usuario activa. Cuando una dirección URL tiene un volumen de rastreador alto, los proveedores de IA consideran que ese contenido merece la pena indexarlo. Cuando una dirección URL tiene un volumen de rastreador bajo pero un volumen de captura en directo alto, el modelo aprovecha el conocimiento almacenado en caché en lugar de recuperar contenido nuevo.

| Valor de tipo de bot | Proveedor | Descripción |
|---|---|---|
| `GPTBot` | OpenAI | Rastreador principal de OpenAI para datos de formación de modelos y construcción de bases de conocimiento. |
| `OAI-SearchBot` | OpenAI | Rastreador de OpenAI para el producto de búsqueda web de ChatGPT. Distinto de GPTBot. Este agente crea el índice de búsqueda en tiempo real, no el cuerpo de formación. |
| `ClaudeBot` | Antrópico | Rastreador principal de Anthropic para datos de entrenamiento de modelos. |
| `Claude-SearchBot` | Antrópico | Rastreador de Claude para el índice de búsqueda y recuperación de Anthropic. Distinto de ClaudeBot. |
| `PerplexityBot` | Perplejidad | Rastreador de índice de Perplejidad. La perplejidad utiliza este agente para construir el cuerpo para su generación de respuestas. |

Se producen **recuperaciones activas de IA** cuando un usuario real envía un mensaje a un asistente de IA y este recupera la página en directo antes de responder. Utilice esta categoría para medir la demanda directa del usuario que llega a través de los asistentes de IA.

| Valor de tipo de bot | Proveedor | Descripción |
|---|---|---|
| `ChatGPT-User` | OpenAI | Un usuario hizo una pregunta a ChatGPT. ChatGPT obtuvo esta URL para leerla y formar su respuesta. |
| `ChatGPT Clients` | OpenAI | La aplicación móvil ChatGPT (iOS y Android) realizando una captura en directo. La cadena user-agent incluye la versión de la aplicación y el dispositivo. |
| `Claude-User` | Antrópico | Un usuario o una aplicación que utiliza Claude recuperó en directo esta dirección URL. La cadena user-agent puede identificar el producto Claude específico, por ejemplo, el código claude. |
| `Perplexity-User` | Perplejidad | Un usuario hizo una pregunta a Perplexity. La perplejidad obtuvo esta URL para fundamentar su respuesta. |
| `Google-NotebookLM` | Google | Un usuario abrió Google NotebookLM y obtuvo este dominio. NotebookLM obtiene todas las direcciones URL accesibles dentro de un dominio de origen. |
| `Google-ai-mode` | Google | La función Información general sobre IA de Google Search recuperó esta dirección URL para incluirla en un panel de respuestas generado por IA en los resultados de búsqueda. |
| `Gemini-Deep-Research` | Google | Un usuario dirigió una sesión de investigación profunda de Gemini. Deep Research realiza muchas recuperaciones secuenciales a través de múltiples fuentes para compilar un informe de investigación. |
| `GoogleAgent-URLContext` | Google | Un usuario compartió una URL con Gemini y le hizo preguntas sobre esa página. Gemini obtuvo la URL en vivo para responder preguntas sobre ese contenido específico. |
| `Amzn-User` | Amazon | Un agente de Amazon Alexa o Amazon AI obtuvo esta URL en directo. Normalmente aparece en el contenido de referencia y documentación. |
| `MistralAI-User` | Mistral | Recuperación en directo de un consumidor de API o producto con tecnología de Mistral. |

Cuando LLM Optimizer no puede hacer coincidir un usuario-agente con un patrón reconocido, asigna el valor `Unknown`. Puede usar la dimensión **Agente de usuario de CDN** para identificar qué agente realizó esas solicitudes.

### Códigos de estado

Los códigos de estado HTTP de este conjunto de datos indican si el agente de IA recibió el contenido que solicitó.

| Estado | Nombre | Interpretación |
|--------|------|----------------|
| 200 | Aceptar | El bot recibió la respuesta completa. El contenido estaba disponible para que lo utilizara la API. |
| 304 | Sin modificar | El bot confirmó que el contenido no ha cambiado y utilizó su versión en caché. El contenido estaba disponible. |
| 301 | Movido permanentemente | El bot se redirigió a una nueva dirección URL. Cada redirección añade un recorrido de ida y vuelta adicional. Un volumen 301 elevado en las direcciones URL rastreadas con frecuencia significa que la redirección debe resolverse en el nivel de CDN. |
| 302 | Encontrado (redirección temporal) | La misma pena de latencia que el 301. A diferencia de 301, no indica un movimiento permanente, por lo que los bots seguirán golpeando la URL original. |
| 403 | Prohibido | La CDN o el origen bloquearon el bot. Esto puede ser intencional, por ejemplo, a través de reglas de robots.txt o políticas de WAF, o no intencional, por ejemplo, a través de límites de tasa demasiado amplios. Cuando las recuperaciones de IA están bloqueadas, ese contenido no puede aparecer en las respuestas de IA. |
| 404 | No encontrado | La dirección URL no existe. El alto volumen 404 de los tipos de agentes de IA indica que el índice de IA contiene direcciones URL antiguas. Utilice el estado 410 para indicar a los rastreadores que eliminen una URL de su índice de forma permanente. |
| 429 | Demasiadas solicitudes | La tasa de CDN limita el bot. Los errores 429 persistentes en los tipos de agentes de captura en directo significan que los usuarios que hagan preguntas a los asistentes de IA sobre su contenido recibirán respuestas incompletas o que falten. |
| 504 | Se ha agotado el tiempo de espera de la puerta de enlace | La CDN dejó de esperar a que respondiera el origen. El contenido no llegó a la API. Cuando se agota el tiempo de espera de una página, la API no puede acceder a su contenido y no puede incluirlo en una respuesta. El alto volumen de 504 en los tipos de agentes de captura en vivo es un riesgo directo de visibilidad de IA. |

### Métricas

Las siguientes métricas están disponibles para su uso como componentes en una vista de datos una vez que haya configurado una conexión que incluya un conjunto de datos de LLM Optimizer. La columna **Campo** muestra el campo de origen en el grupo de campos Resumen de solicitudes de CDN.

| Métrica | Campo | Descripción |
|--------|-------|-------------|
| Recuento de solicitudes de CDN | `cdn.requests` | Recuento total de solicitudes de CDN, sumadas desde el campo de solicitudes en todas las filas. Utilice siempre esta métrica para medir el volumen. No utilice el recuento de filas. |
| Recuento de errores de CDN | `cdn.status`, `cdn.requests` | El recuento de solicitudes que devolvieron un código de estado HTTP 4xx o 5xx. |
| Tasa de errores de CDN | Derivado del recuento de errores de CDN | El recuento de errores como porcentaje del total de solicitudes. |
| Tiempo promedio de CDN a primer byte | `cdn.timeToFirstByte` | El tiempo promedio en milisegundos desde que la CDN recibió una solicitud hasta el primer byte de la respuesta. Las respuestas en caché de CDN suelen ser inferiores a 50 ms. Las respuestas proporcionadas desde el origen suelen ser de 300 ms a 700 ms. Los agentes de captura de IA suelen mostrar valores mucho más altos, que corresponden a respuestas de origen agotadas o muy lentas. Vale la pena investigar los valores promedio altos de los tipos de agentes de captura activa como un riesgo de visibilidad de IA. |

### Límites de conjuntos de datos

Este conjunto de datos captura únicamente el tráfico de bots de los registros de acceso de CDN. No contiene lo siguiente:

* **Sesiones de usuario, conversiones o datos de participación.** Un usuario que hace clic desde una respuesta de IA ejecuta JavaScript en su página, por lo que la visita se encuentra en los datos web existentes, no en este conjunto de datos. Puede introducir ambos conjuntos de datos en Customer Journey Analytics y compararlos para la misma URL y host.
* **Cualquier identificador de persona, como ECID.** No puede realizar una unión de nivel de persona desde este conjunto de datos. La unión funciona en los niveles de URL y host.
* **Granularidad de tiempo por debajo del segundo.** La marca de tiempo es por hora. No puede desglosar el tráfico en una hora en minutos o segundos.
* **Contenido de página o HTML procesado.** Este conjunto de datos registra el hecho de la recuperación y su resultado, no lo que la IA lee de la página.
* **Datos de conversión.** Este conjunto de datos no indica si una respuesta de IA llevó a una persona a visitar el sitio o convertirse. Contiene datos de resumen de CDN agregados, no datos de evento basados en personas, por lo que no vincula ninguna solicitud a una persona o sesión individual.

## Integración saliente

Por determinar.


<!-- 

# LLM Optimizer integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/en/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. LLM Optimizer provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl and reference brand content. 

>[!PREREQUISITES]
>
>You must have an LLM Optimizer paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of LLM Optimizer data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and LLM Optimizer in two ways:

* **Inbound integration**: Use LLM Optimizer data in Customer Journey Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web, mobile, and other types of data. For example, to address the following use cases:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Correlate LLM activity with downstream business outcomes (revenue, conversions, engagement).
  
* **Outbound integration**: Use Customer Journey Analytics performance data inside LLM Optimizer so AI visibility can be optimized for real business outcomes. For example, to address the following use cases:

  * Evaluate how each LLM agent correlates with revenue, conversions, and engagement.
  * Identify which LLM agents are associated with stronger downstream performance. Which LLM agents are associated with higher engagement or conversion rates.


## Inbound integration

To ingest LLM Optimizer data into Customer Journey Analytics, use the LLM Optimizer datasets available in Experience Platform. The ingestion method:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Schema class.
* Buckets data by URL/host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The LLM Optimizer dataset contains aggregated data that does not contain any PII, such as user identifiers, prompts, or responses.
>

You use the LLM Optimizer dataset in a connection. Because the dataset is a summary dataset, you can use the dataset as a lookup dataset and potentially join to an event dataset on a full-URL key.

LLM Optimizer provides this key for you in the **CDN URL** dimension. The key combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. This join-key field facilitates the join. The outcome depends on your Customer Journey Analytics implementation and whether your event dataset has a page URL field that matches the URL representation LLM Optimizer provides. When both sides resolve to the same full URL, the LLM Optimizer record matches the corresponding page in your web data.

### About the dataset

LLM Optimizer reads CDN access logs on the server side and extracts records where the requesting party is a bot or automated agent. Because the data comes from the CDN layer, LLM Optimizer captures requests from bots that do not execute any JavaScript tag. Standard web analytics tools miss this traffic entirely.

Each record describes one combination of host, URL path, bot type, CDN provider, status code, referrer, forwarded host, and time to first byte for one hour. When the same combination appears multiple times hourly, Customer Journey Analytics combines those records into one row and increases the request count. Use the **CDN Request Count** metric to measure volume. Do not use row count.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Dimension | Description |
|-----------|-------------|
| CDN URL | The normalized full URL for the request, intended as the join key. LLM Optimizer combines the host and the requested path into a single URL and normalizes it to match the full-URL form that Customer Journey Analytics stores for web data. Use this dimension to join the LLM Optimizer lookup dataset to an event dataset that has an equivalent full-URL field. It includes the host and path, but not the scheme. |
| CDN URL Path | The raw URL path and query string that the agent requested, as delivered by the CDN. Does not include the scheme or host. Use this when you need the exact requested path rather than the normalized join key. |
| CDN Host | The hostname that received the request, for example, www.example.com. This host is also part of the CDN URL join key. A dataset can contain multiple hosts when an organization has multiple subdomains on the same CDN account. |
| CDN Bot Type | LLM Optimizer's classification of the requesting agent. Values cover classic search crawlers, AI index crawlers, and AI live-fetch agents. See the [Bot agent categories](#bot-agent-categories) below for the full taxonomy. |
| CDN User Agent | The raw user-agent string from the CDN log. Useful for distinguishing sub-types within a bot classification, or for validating the classification assigned by LLM Optimizer. |
| CDN HTTP Status | The HTTP response status code. Indicates whether the bot received the content it requested. See the [Status codes](#status-codes) below for interpretation guidance specific to AI traffic. |
| CDN Provider | Which CDN handled the request. Values are `akamai`, `byocdn-akamai`, `byocdn-fastly`, and b`yocdn-cloudfront`. The `byocdn-` prefix indicates the log collection pathway, not a different CDN vendor. A dataset can contain multiple values when an organization has hosts behind different CDN configurations. |
| CDN Referrer | The HTTP Referer header value from the CDN log. Often empty for bot traffic. When present, it can indicate which AI product or domain triggered the fetch. For example, chat.openai.com. |
| CDN Forwarded Host | The X-Forwarded-Host header value, if present. Relevant when the request passed through a reverse proxy or CDN shield layer before reaching the origin. |
| CDN Event Date | The date part of the hourly batch timestamp for this record. |
| CDN Event Hour | The hour part of the hourly batch timestamp for this record. |

### Bot agent categories

The **CDN Bot Type** dimension organizes agents into three categories. Each category answers a different analytical question.

**Classic search crawlers** index content for traditional search engines. Use this category to measure how visible your content is to traditional search engines.

| Bot type value | Vendor | Description |
|---|---|---|
| `GoogleBot` | Google | Google's main search index crawler. Also serves Google Discover and Google News. |
| `BingBot` | Microsoft | Bing's search index crawler. Also feeds Microsoft Copilot's web grounding index. |

**AI index crawlers** crawl content to build or update an AI product's training corpus or search index. These crawlers are preparing a model's knowledge base, not responding to a live user request. When a URL has high crawler volume, AI vendors consider that content worth indexing. When a URL has low crawler volume but high live-fetch volume, the model draws from cached knowledge rather than fetching fresh content.

| Bot type value | Vendor | Description |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI's primary crawler for model training data and knowledge base construction. |
| `OAI-SearchBot` | OpenAI | OpenAI's crawler for ChatGPT's web search product. Distinct from GPTBot. This agent builds the real-time search index, not the training corpus. |
| `ClaudeBot` | Anthropic | Anthropic's primary crawler for model training data. |
| `Claude-SearchBot` | Anthropic | Anthropic's crawler for Claude's search and retrieval index. Distinct from ClaudeBot. |
| `PerplexityBot` | Perplexity | Perplexity's index crawler. Perplexity uses this agent to build the corpus for its answer generation. |

**AI live fetches** occur when a real user submits a prompt to an AI assistant and the assistant fetches the page live before responding. Use this category to measure direct user demand arriving through AI assistants.

| Bot type value | Vendor | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | A user asked ChatGPT a question. ChatGPT fetched this URL to read it and form its answer. |
| `ChatGPT Clients` | OpenAI | The ChatGPT mobile app (iOS and Android) doing a live fetch. The user-agent string includes the app version and device. |
| `Claude-User` | Anthropic | A user or application using Claude live-fetched this URL. The user-agent string may identify the specific Claude product, e.g., claude-code. |
| `Perplexity-User` | Perplexity | A user asked Perplexity a question. Perplexity fetched this URL to ground its answer. |
| `Google-NotebookLM` | Google | A user opened Google NotebookLM and sourced this domain. NotebookLM fetches every reachable URL within a sourced domain. |
| `Google-ai-mode` | Google | Google Search's AI Overviews feature fetched this URL to include it in an AI-generated answer panel in search results. |
| `Gemini-Deep-Research` | Google | A user ran a Gemini Deep Research session. Deep Research makes many sequential fetches across multiple sources to compile a research report. |
| `GoogleAgent-URLContext` | Google | A user shared a URL with Gemini and asked questions about that page. Gemini fetched the URL live to answer questions about that specific content. |
| `Amzn-User` | Amazon | An Amazon Alexa or Amazon AI agent live-fetched this URL. Typically appears on reference and documentation content. |
| `MistralAI-User` | Mistral | A live fetch from a Mistral-powered product or API consumer. |

When LLM Optimizer cannot match a user-agent to a recognized pattern, it assigns the value `Unknown`. You can use the **CDN User Agent** dimension to identify what agent made those requests.

### Status codes

HTTP status codes in this dataset indicate whether the AI agent received the content it requested.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | The bot received the full response. The content was available for the AI to use. |
| 304 | Not Modified | The bot confirmed the content has not changed and used its cached version. The content was available. |
| 301 | Moved Permanently | The bot was redirected to a new URL. Each redirect adds an extra round-trip. High 301 volume on frequently crawled URLs means the redirect should be resolved at the CDN level. |
| 302 | Found (Temporary Redirect) | Same latency penalty as 301. Unlike 301, it does not signal a permanent move, so bots will keep hitting the original URL. |
| 403 | Forbidden | The CDN or origin blocked the bot. This can be intentional, e.g., through robots.txt rules or WAF policy, or unintentional, e.g., through overly broad rate limits. When AI fetches are blocked, that content cannot appear in AI answers. |
| 404 | Not Found | The URL does not exist. High 404 volume on AI agent types indicates the AI's index contains stale URLs. Use the 410 status to tell crawlers to remove a URL from their index permanently. |
| 429 | Too Many Requests | The CDN rate-limited the bot. Sustained 429 errors on live-fetch agent types mean that users asking AI assistants questions about your content will receive incomplete or missing responses. |
| 504 | Gateway Timeout | The CDN stopped waiting for the origin to respond. The content did not reach the AI. When a page times out, the AI cannot access its content and cannot include it in an answer. High 504 volume on live-fetch agent types is a direct AI visibility risk. |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Metric | Description |
|--------|-------------|
| CDN Request Count | The total count of CDN requests, summed from the requests field across all rows. Always use this metric to measure volume. Do not use row count. |
| CDN Error Count | The count of requests that returned a 4xx or 5xx HTTP status code. |
| CDN Error Rate | The error count as a percentage of total requests. |
| CDN Avg Time to First Byte | The average time in milliseconds from when the CDN received a request to the first byte of the response. CDN-cached responses are typically under 50ms. Responses served from the origin are typically 300ms to 700ms. AI live-fetch agents often show much higher values, which correspond to timed-out or very slow origin responses. High average values on live-fetch agent types are worth investigating as an AI visibility risk. |

### Dataset boundaries

This dataset captures only bot traffic from CDN access logs. It does not contain the following:

* **Human sessions, conversions, or engagement data.** Human sessions are in your existing web analytics dataset. To correlate AI demand with human outcomes, join the two datasets in CJA at the URL and host level.
* **Any person identifier such as ECID.** You cannot make a person-level join from this dataset. The join works at the URL and host level.
* **Sub-second time granularity.** The timestamp is hourly. You cannot break down traffic within an hour into minutes or seconds.
* **Page content or rendered HTML.** This dataset records the fact of the fetch and its outcome, not what the AI read from the page.
* **Conversion data.** Whether an AI answer led a user to visit the site or convert is not in this dataset. That analysis requires joining to human session data in CJA.

## Outbound integration

To be determined.

-->