---
title: Referencia de conjunto de datos de integración entrante de Brand Visibility
description: Obtenga información acerca de todos los detalles de los conjuntos de datos utilizados para la integración de Brand Visibility con Customer Journey Analytics
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e3958dfbad19f5fdd78b2755817d21afad8f8e84
workflow-type: tm+mt
source-wordcount: '1894'
ht-degree: 2%
---

# Referencia de conjunto de datos

[Adobe Brand Visibility](https://experienceleague.adobe.com/es/docs/brand-visibility/using/home){target="_blank"} es una aplicación generativa con prioridad de IA para la optimización de motores generativos, diseñada para ayudar a las marcas a mejorar su visibilidad, precisión e influencia en entornos de búsqueda impulsados por IA. Brand Visibility proporciona perspectivas sobre la presencia de marca en respuestas generadas por IA, ofrece recomendaciones de contenido prescriptivo y automatiza las correcciones de optimización.

La IA se ha convertido en un canal de descubrimiento principal. Los agentes del modelo de lenguaje grande (LLM), como ChatGPT, Claude, Copilot y Perplexity, rastrean el contenido de la marca.

>[!PREREQUISITES]
>
>Debe tener una oferta de pago por Visibilidad de la marca. A continuación, [configure y habilite](./configure.md) el origen de Adobe Brand Visibility en su zona protegida de Experience Platform.
>


>[!IMPORTANT]
>
>Como parte de esta integración, algunos procesos temporales de datos de Visibilidad de la marca tienen lugar en Estados Unidos. En última instancia, los datos se almacenan en la región designada, según la configuración del contrato de Customer Journey Analytics.


## Acerca del conjunto de datos

Consulte [Información general](./bv.md) para obtener más información sobre los casos de uso de la integración de entrada y salida de la Visibilidad de la marca con Customer Journey Analytics.

La visibilidad de la marca de lee los registros de acceso de CDN en el servidor y extrae registros en los que la parte solicitante es un bot o un agente automatizado. Como los datos proceden del nivel de CDN, Brand Visibility captura solicitudes de bots que no activan ninguna etiqueta de JavaScript. Las herramientas estándar de análisis web omiten este tráfico por completo.

El conjunto de datos utiliza el grupo de campos **Resumen de solicitudes de CDN**. Cada campo se encuentra debajo de un objeto `cdn`, por lo que los nombres de campo de las tablas siguientes tienen el formato <code>cdn._name_</code>, por ejemplo `cdn.url` y `cdn.botType`.

Cada registro describe una combinación de host, ruta URL, tipo de bot, proveedor de CDN, código de estado, referente, host reenviado y tiempo hasta el primer byte durante una hora. Cuando la misma combinación aparece más de una vez por hora, Customer Journey Analytics combina esos registros en una fila y aumenta el recuento de solicitudes. Utilice la métrica **Recuento de solicitudes de CDN** para medir el volumen. No utilice el recuento de filas.

## Dimensiones

Las siguientes dimensiones están disponibles para su uso como componentes en una vista de datos una vez que haya configurado una conexión que incluya un conjunto de datos de Brand Visibility. La columna **Campo** muestra el campo de origen en el grupo de campos Resumen de solicitudes de CDN.

| Dimensión | Campo | Descripción |
|-----------|-------|-------------|
| URL de CDN | `cdn.url` | Dirección URL completa normalizada para la solicitud, que se utiliza como clave de unión. La visibilidad de la marca combina el host y la ruta solicitada en una sola dirección URL y la normaliza para que coincida con el formulario de URL completa que Customer Journey Analytics almacena para los datos web. Utilice esta dimensión para unir el conjunto de datos de búsqueda de Visibilidad de la marca a un conjunto de datos de evento que tenga un campo de URL completa equivalente. Incluye el host y la ruta, pero no el esquema. |
| Ruta de URL de CDN | `cdn.path` | Ruta de URL sin procesar y cadena de consulta que solicitó el agente, tal como la entregó la CDN. No incluye el esquema ni el host. Utilícelo cuando necesite la ruta solicitada exacta, en lugar de la clave de unión normalizada. |
| Host de CDN | `cdn.host` | El nombre de host que recibió la solicitud, por ejemplo, www.example.com. Este host también forma parte de la clave de unión de URL de CDN. Un conjunto de datos puede contener varios hosts cuando una organización tiene varios subdominios en la misma cuenta de CDN. |
| Tipo de bot de CDN | `cdn.botType` | La clasificación de la visibilidad de la marca del agente solicitante. Los valores abarcan rastreadores de búsqueda clásicos, rastreadores de índice de IA y agentes de captura en directo de IA. Consulte las [categorías de agentes de bots](#bot-agent-categories) a continuación para ver la taxonomía completa. |
| Agente de usuario de CDN | `cdn.userAgent` | La cadena del agente de usuario sin procesar del registro de CDN. Útil para distinguir subtipos dentro de una clasificación de bots o para validar la clasificación asignada por Visibilidad de la marca. |
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

Cuando la Visibilidad de la marca no puede coincidir con un usuario-agente para un patrón reconocido, asigna el valor `Unknown`. Puede usar la dimensión **Agente de usuario de CDN** para identificar qué agente realizó esas solicitudes.

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

## Métricas

Las siguientes métricas están disponibles para su uso como componentes en una vista de datos una vez que haya configurado una conexión que incluya un conjunto de datos de Brand Visibility. La columna **Campo** muestra el campo de origen en el grupo de campos Resumen de solicitudes de CDN.

| Métrica | Campo | Descripción |
|--------|-------|-------------|
| Recuento de solicitudes de CDN | `cdn.requests` | Recuento total de solicitudes de CDN, sumadas desde el campo de solicitudes en todas las filas. Utilice siempre esta métrica para medir el volumen. No utilice el recuento de filas. |
| Recuento de errores de CDN | `cdn.status`, `cdn.requests` | El recuento de solicitudes que devolvieron un código de estado HTTP 4xx o 5xx. |
| Tasa de errores de CDN | Derivado del recuento de errores de CDN | El recuento de errores como porcentaje del total de solicitudes. |
| Tiempo promedio de CDN a primer byte | `cdn.timeToFirstByte` | El tiempo promedio en milisegundos desde que la CDN recibió una solicitud hasta el primer byte de la respuesta. Las respuestas en caché de CDN suelen ser inferiores a 50 ms. Las respuestas proporcionadas desde el origen suelen ser de 300 ms a 700 ms. Los agentes de captura de IA suelen mostrar valores mucho más altos, que corresponden a respuestas de origen agotadas o muy lentas. Vale la pena investigar los valores promedio altos de los tipos de agentes de captura activa como un riesgo de visibilidad de IA. |

## Límites

Este conjunto de datos captura únicamente el tráfico de bots de los registros de acceso de CDN. No contiene lo siguiente:

* **Sesiones de usuario, conversiones o datos de participación.** Un usuario que hace clic desde una respuesta de IA ejecuta JavaScript en su página, por lo que la visita se encuentra en los datos web existentes, no en este conjunto de datos. Puede introducir ambos conjuntos de datos en Customer Journey Analytics y compararlos para la misma URL y host.
* **Cualquier identificador de persona, como ECID.** No se puede realizar una unión de nivel de persona desde este conjunto de datos. La unión funciona en los niveles de URL y host.
* **Granularidad de tiempo por debajo del segundo.** La marca de tiempo es por hora. No puede desglosar el tráfico en una hora en minutos o segundos.
* **Contenido de página o HTML procesado.** Este conjunto de datos registra el hecho de la recuperación y su resultado, no lo que la IA lee de la página.
* **Datos de conversión.** Este conjunto de datos no indica si una respuesta de IA llevó a una persona a visitar el sitio o convertirse. Contiene datos de resumen de CDN agregados, no datos de evento basados en personas, por lo que no vincula ninguna solicitud a una persona o sesión individual.
