---
title: Información general sobre Content Analytics
description: Obtenga información acerca del valor y la terminología de Content Analytics y conozca cómo funciona Content Analytics.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
TQID: https://experienceleague.adobe.com/x5FpRmZ-Wv6pPxYBEAyDzRqUSUpmwHFwbi55FwVKT5A
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c4147b6e-073b-4d3c-9ab1-d60f2f4434efid: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 905
ht-degree: 55%

---


# Información general sobre Content Analytics

Content Analytics ayuda a los especialistas en marketing a comprender cómo afecta el contenido a los indicadores de rendimiento clave que ha definido una empresa. Además de los datos de comportamiento, Content Analytics recopila datos sobre cómo se consume el contenido y cómo afectan las unidades de contenido. Por ejemplo, ¿responden mejor los clientes a un tono de voz específico, a una gama de colores específica o a temas específicos? Esta información, junto con los flujos de trabajo de creación de informes diseñados específicamente y las plantillas, puede ayudarle a realizar un análisis aún mejor y a obtener conocimientos más profundos sobre los datos de recorrido del cliente en Customer Journey Analytics.

Content Analytics utiliza un **servicio de caracterización** basado en la IA y el aprendizaje automático para descomponer el contenido en componentes y atributos. Al crear un perfil de metadatos estructurado en todo el contenido, puede analizar qué contenido y qué atributos de ese contenido impulsan los resultados empresariales.

Además de la creación de este perfil de metadatos estructurado, Content Analytics proporciona un **servicio de identidad** que identifica recursos y experiencias mediante un único identificador. El servicio de identidad puede reconocer cuándo aparece exactamente el mismo recurso en más de un lugar. Cuando esto suceda, las dos instancias de recursos se tratarán como el mismo recurso, lo que permitirá una vista más holística del uso y el consumo de contenido.

## Valor

Content Analytics proporciona valor en un nivel creciente:

1. **Uso** de contenido: con Content Analytics obtiene información sobre qué recursos reciben impresiones y dónde reciben los recursos. Estas perspectivas le ayudan a ver si los recursos se infrautilizan o se utilizan en exceso en las propiedades web y móviles.
1. **Participaciones** del contenido: Content Analytics puede proporcionar información sobre la participación, como la tasa promedio de clics entre recursos con determinados atributos. Esta información le ayuda a determinar si tipos específicos de experiencias siguen siendo eficaces.
1. Recorridos de contenido: Además, cuando se combina con todos los demás datos disponibles en Experience Platform, puede obtener perspectivas adicionales sobre sus recorridos de contenido; por ejemplo, si el contenido específico conduce a conversiones, además de la participación. Por ejemplo, si un contenido específico genera conversiones, además de la participación. Y con ese conocimiento puede determinar el retorno de la inversión de los tipos de contenido.
1. **Personalización** del contenido: en última instancia, Content Analytics le permite actuar en función de sus informaciones y utilizar estas informaciones para determinar cómo gastar dinero en contenido. Por ejemplo, ¿debo enviar tipos de contenido específicos a públicos específicos? ¿Qué contenido me ofrece oportunidades de alta personalización?

## Terminología

Content Analytics utiliza los siguientes términos clave:

![Recursos y experiencias](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Experiencia**: Una experiencia es texto en una página web que se puede reproducir usando la URL que el usuario inicial usó para visitar la página web. O la combinación de texto, recursos y clics para realizar acciones en una aplicación móvil. Cada experiencia obtiene un identificador único.
* **Recurso**: este es un fragmento de contenido individual y único, como una imagen. Cada recurso también obtiene un identificador único y un ID perceptual. Un ID perceptual es un identificador que se comparte con recursos que son visualmente idénticos. Los ID perceptuales ayudan a deduplicar recursos que pueden tener una URL de recurso diferente y, por lo tanto, un ID de recurso diferente, pero que son perceptualmente idénticos.
* **Atributo**: un atributo es un elemento de metadatos descriptivo asociado a una experiencia o recurso. Algunos ejemplos de un atributo son: estilo de fotografía, legibilidad, estrategia de persuasión, color de los objetos, color de fondo.

## Funcionamiento

Content Analytics usa datos de vistas de imágenes móviles y web de conjuntos de datos de eventos de Experience Platform para [recopilar datos de eventos de contenido](config/datacollection.md). Estos eventos de experiencia de contenido requieren que los datos se recopilen con Experience Platform Edge Network (Web SDK, Mobile SDK, API de servidor). Los datos de comportamiento se pueden recopilar con Web SDK, Mobile SDK o el conector de Source de Analytics.

![Content Analytics: funcionamiento](assets/aca-overview-new.gif)

1. Cuando un usuario visita un sitio o una aplicación [configurados para Content Analytics](config/configuration.md), Experience Platform Web o Mobile SDK registra impresiones e interacciones con el contenido.
1. El servicio de identidad y características procesa estas interacciones. Ese proceso consiste en un servicio de recuperación que vuelve a visitar las versiones públicas de las direcciones URL configuradas que definen las interacciones. Para todas estas direcciones URL recuperadas, el servicio de identidad identifica de forma exclusiva las experiencias y los recursos. Además, el servicio de personalización aplica servicios de IA/ML para descubrir experiencias, metadatos y atributos de recursos.
1. Los resultados de estos servicios ([componentes, atributos e identidades](/help/content-analytics/report/components.md)) se utilizan para actualizar los conjuntos de datos específicos y pertinentes de Content Analytics en Experience Platform.
1. Puede usar los datos de Content Analytics, junto con los datos de comportamiento y otros datos de búsqueda, en una configuración de Customer Journey Analytics ([Conexión](/help/connections/overview.md), [Vista de datos](/help/data-views/data-views.md) y [Workspace](/help/analysis-workspace/home.md)). Esa configuración proporciona la base para la información única a nivel de macro sobre el contenido. <br/>Puede comenzar rápidamente sus informes y análisis de Content Analytics usando la [plantilla de Content Analytics](/help/content-analytics/report/report.md#template).


>[!NOTE]
>
>Content Analytics aprovecha los servicios de IA/ML que pueden producir resultados inexactos o engañosos. Por lo tanto, utilice su criterio para revisar y validar los resultados generados por AI/ML.
>
>Puede usar la ficha **[!UICONTROL Comentarios]**, disponible en ![InfoOutline](/help/assets/icons/InfoOutline.svg) en la interfaz principal, para proporcionar comentarios sobre los resultados generados por inteligencia artificial o aprendizaje automático.
>

>[!NOTE]
>
>Si tiene licencia para el complemento Escudo de seguridad y privacidad, tenga en cuenta que el etiquetado DULE o las claves gestionadas por el cliente no cubren las experiencias y los recursos sujetos a Content Analytics. Además, Content Analytics no es un servicio compatible con HIPAA.
>

>[!IMPORTANT]
>
>Content Analytics solo admite la funcionalidad en inglés.
>


>[!MORELIKETHIS]
>
>Informes de [Content Analytics](report/report.md)
>[Configuración de Content Analytics](config/configuration.md)
>[Cálculo de salidas hacia otro sitio y tasa de salidas hacia otro sitio en Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/calculating-bounces-bounce-rate-in-adobe-customer-journey-analytics-options-and-implications-12722)
>

