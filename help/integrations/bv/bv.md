---
title: Integración de visibilidad de la marca
description: Integración de Brand Visibility con Customer Journey Analytics
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
source-wordcount: '844'
ht-degree: 3%
---

# Integración de Adobe Brand Visibility

[Adobe Brand Visibility](https://experienceleague.adobe.com/es/docs/brand-visibility/using/home){target="_blank"} es una aplicación generativa con prioridad de IA para la optimización de motores generativos, diseñada para ayudar a las marcas a mejorar su visibilidad, precisión e influencia en entornos de búsqueda impulsados por IA. Brand Visibility proporciona perspectivas sobre la presencia de marca en respuestas generadas por IA, ofrece recomendaciones de contenido prescriptivo y automatiza las correcciones de optimización.

La IA se ha convertido en un canal de descubrimiento principal. Los agentes del modelo de lenguaje grande (LLM), como ChatGPT, Claude, Copilot y Perplexity, rastrean el contenido de la marca.

>[!NOTE]
>
>Debe tener una oferta de pago por Visibilidad de la marca. A continuación, [configure y habilite](./configure.md) el origen de Adobe Brand Visibility en su zona protegida de Experience Platform.
>


>[!IMPORTANT]
>
>Como parte de esta integración, algunos procesos temporales de datos de Visibilidad de la marca tienen lugar en Estados Unidos. En última instancia, los datos se almacenan en la región designada, según la configuración del contrato de Customer Journey Analytics.
>


## Casos de uso

Puede beneficiarse de la integración entre Customer Journey Analytics y Brand Visibility de dos maneras:

* **Integración entrante**: utilice los datos de Visibilidad de la marca en Customer Journey Analytics para medir el tráfico impulsado por LLM (rastreadores de bots, solicitudes RAG, actividad del agente) junto con datos web, móviles y de otro tipo. Por ejemplo, puede realizar lo siguiente:

  * Mida el tráfico impulsado por LLM por fuente de agente junto con los canales tradicionales.

  * Identificar el contenido que consume mucho los LLM pero que no tiene el rendimiento suficiente en la conversión humana.

  * Detectar dónde fallan las solicitudes del agente LLM en las rutas críticas.

  * Comparar la demanda de bots LLM de una página con las conversiones e ingresos de esa página en los datos web, coincidiendo en los niveles de URL y host.

* **Integración saliente**: envíe datos de rendimiento de Customer Journey Analytics a Brand Visibility para que pueda optimizar la visibilidad de IA para las fuentes de LLM que le envían tráfico valioso, como ChatGPT o Perplexity. Por ejemplo, puede realizar lo siguiente:

  * Vea qué fuentes de LLM envían visitantes humanos que siguen convirtiendo o generando ingresos. Customer Journey Analytics mide esto a partir del tráfico web al que se hace referencia, no del conjunto de datos de bots.
  * Clasifique las fuentes de LLM según el valor descendente de los visitantes humanos que envían y, a continuación, centre su trabajo de visibilidad de la IA en las fuentes que funcionan mejor.


## Integración entrante

El tráfico LLM llega a su sitio de dos maneras. Customer Journey Analytics mide cada trayecto desde una fuente de datos diferente.

La primera forma es con una persona que lee una respuesta de IA y luego hace clic en el sitio. Esa visita ejecuta la misma JavaScript que recopila el resto de los datos web. Por lo tanto, los datos web de Customer Journey Analytics existentes incluyen la visita y el dominio de referencia que le envió el usuario, por ejemplo, chatgpt.com. Customer Journey Analytics no etiqueta estas visitas como tráfico de IA por sí solo. Para identificarlos y agruparlos, se crea un campo derivado en la conexión que coincide con los dominios de referencia de IA y, a continuación, se generan segmentos e informes sobre ese campo. Consulte [Campos derivados](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. No necesita el conjunto de datos de Visibilidad de la marca para este tráfico humano.

La segunda forma es un bot o agente que solicite sus páginas directamente. Esto incluye rastreadores que crean un índice de IA y recuperaciones en directo que se producen cuando un usuario envía un mensaje a un asistente de IA. Estas solicitudes no ejecutan ningún JavaScript, por lo que los datos web existentes no los registran. El conjunto de datos de Visibilidad de la marca captura este tráfico desde la capa de CDN. El resto de esta sección describe ese conjunto de datos.


### Incorporación del conjunto de datos

La fuente de Adobe Brand Visibility se habilita en Experience Platform. La fuente envía los datos a la zona protegida como un conjunto de datos de resumen. Para medir los datos en Customer Journey Analytics, siga dos pasos más para la configuración:

1. Cree una conexión que incluya el conjunto de datos de Brand Visibility.
2. Cree una vista de datos sobre esa conexión. La vista de datos hace que las dimensiones y métricas siguientes estén disponibles en Analysis Workspace.

El conjunto de datos:

* Utiliza [conjuntos de datos de resumen](/help/data-views/summary-data.md) basados en la clase Métricas de resumen de XDM.
* Agrupa datos por dirección URL y host, hora y características de solicitud como tipo de bot, proveedor de CDN y estado.

>[!NOTE]
>
>El conjunto de datos de Brand Visibility contiene datos agregados. No contiene ninguna PII, como un identificador de usuario, indicadores o respuestas.
>

Como es un conjunto de datos de resumen, puede utilizarlo como un conjunto de datos de búsqueda y unirlo a un conjunto de datos de evento en una clave de URL completa.

Brand Visibility proporciona esta clave en la dimensión **CDN URL**. Combina el host y la ruta solicitada en una sola URL completa normalizada, de forma similar a como Customer Journey Analytics almacena los datos web. El éxito de la unión depende de su propia recopilación de datos. El conjunto de datos de evento necesita un campo de dirección URL completo equivalente o un campo que se pueda analizar y normalizar para que coincida con la dirección URL que proporciona la Visibilidad de la marca. Cuando ambos lados se resuelven en la misma dirección URL completa, el registro de Visibilidad de la marca coincide con la página correspondiente de los datos web.

Consulte para obtener más información:

* [Configuración de la integración entrante](/help/integrations/bv/configure.md)
* [Referencia de conjunto de datos](/help/integrations/bv/reference.md)

## Integración saliente

Para obtener información sobre la integración saliente, consulte [Integración de Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"} en la documentación de Adobe Brand Visibility.
