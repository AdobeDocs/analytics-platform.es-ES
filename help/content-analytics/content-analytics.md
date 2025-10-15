---
title: Información general sobre Content Analytics
description: Información general sobre Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 100%

---

# Información general sobre Content Analytics

Content Analytics ayuda a los especialistas en marketing a comprender cómo afecta el contenido a los indicadores de rendimiento clave que ha definido una empresa. Además de los datos de comportamiento, Content Analytics recopila datos sobre cómo se consume el contenido y cómo este genera impacto. Por ejemplo, ¿responden mejor los clientes a un tono de voz específico, a una gama de colores específica o a temas específicos? Esta información, junto con los flujos de trabajo de creación de informes diseñados específicamente y las plantillas, puede ayudarle a realizar un análisis aún mejor y a obtener conocimientos más profundos sobre los datos de recorrido del cliente en Customer Journey Analytics.

Content Analytics utiliza un **servicio de caracterización** basado en la IA y el aprendizaje automático para descomponer el contenido en componentes y atributos. Al crear un perfil de metadatos estructurado en todo el contenido, puede analizar qué contenido y qué atributos de ese contenido generan resultados empresariales.

Además de la creación de este perfil de metadatos estructurado, Content Analytics proporciona un **servicio de identidad** que identifica recursos y experiencias mediante un único identificador. El servicio de identidad puede reconocer cuándo aparece exactamente el mismo recurso en más de un lugar. Cuando esto suceda, las dos instancias de recursos se tratarán como el mismo recurso, lo que permitirá una vista más holística del uso y el consumo de contenido.

## Valor

Content Analytics proporciona valor en un nivel creciente:

1. **Uso** de contenido: con Content Analytics obtiene información sobre qué recursos reciben impresiones y dónde reciben los recursos. Esta información le ayuda a ver si los recursos se infrautilizan o se utilizan en exceso en las propiedades web.
1. **Participaciones** del contenido: Content Analytics puede proporcionar información sobre la participación, como la tasa promedio de clics entre recursos con determinados atributos. Esta información le ayuda a determinar si tipos específicos de experiencias siguen siendo eficaces.
1. **Recorridos** del contenido: además, cuando se combinan con todos los demás datos disponibles en Experience Platform, puede obtener información adicional sobre los recorridos de su contenido. Por ejemplo, si un contenido específico genera conversiones, además de la participación. Y con ese conocimiento puede determinar el retorno de la inversión de los tipos de contenido.
1. **Personalización** del contenido: en última instancia, Content Analytics le permite actuar en función de sus informaciones y utilizar estas informaciones para determinar cómo gastar dinero en contenido. Por ejemplo, ¿debo enviar tipos de contenido específicos a públicos específicos? ¿Qué contenido me ofrece oportunidades de alta personalización?

## Terminología

Content Analytics utiliza los siguientes términos clave:

![Recursos y experiencias](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Experiencia**: una experiencia es todo el texto de una página web que se puede reproducir usando la URL usada por el usuario inicial que visitó esa página web. Cada experiencia obtiene un identificador único. Los cambios en la página que producen cambios en el HTML de la página resultan en una nueva experiencia.
* **Recurso**: este es un fragmento de contenido individual y único, como una imagen. Cada recurso también obtiene un identificador único y un ID perceptual. Un ID perceptual es un identificador que se comparte con recursos que son visualmente idénticos. Los ID perceptuales ayudan a deduplicar recursos que pueden tener una URL de recurso diferente y, por lo tanto, un ID de recurso diferente, pero que son perceptualmente idénticos.
* **Atributo**: un atributo es un elemento de metadatos descriptivo asociado a una experiencia o recurso. Algunos ejemplos de un atributo son: estilo de fotografía, legibilidad, estrategia de persuasión, color de los objetos, color de fondo.

## Funcionamiento

Content Analytics usa los datos de vista de imágenes web en conjuntos de datos de evento en Experience Platform para [recopilar datos de evento de contenido](config/datacollection.md). Y combina esa recopilación de datos de contenido con la implementación (ya existente) de recopilación de datos de comportamiento.

![Content Analytics: funcionamiento](assets/aca-overview.gif)

1. Cuando un usuario visita un sitio [configurado para Content Analytics](config/configuration.md), Experience Platform Web SDK registra las impresiones y las interacciones con el contenido.
1. El servicio de identidad y características procesa estas interacciones. Ese proceso consiste en un servicio de recuperación que vuelve a visitar las versiones públicas de las direcciones URL configuradas que definen las interacciones. Para todas estas direcciones URL recuperadas, el servicio de identidad identifica de forma exclusiva las experiencias y los recursos. Además, el servicio de personalización aplica servicios de IA/ML para descubrir experiencias, recursos, metadatos y atributos.
1. Los resultados de estos servicios ([componentes, atributos e identidades](/help/content-analytics/report/components.md)) se utilizan para actualizar los conjuntos de datos específicos y pertinentes de Content Analytics en Experience Platform.
1. Puede utilizar los datos de Content Analytics, junto con los datos de comportamiento y otros datos de consulta, en una configuración de Customer Journey Analytics ([Conexión](/help/connections/overview.md), [Vista de datos](/help/data-views/data-views.md) y [Workspace](/help/analysis-workspace/home.md)). Esa configuración proporciona la base para los conocimientos únicos a nivel de macro sobre el contenido. <br/>Puede iniciar sus informes y Content Analytics con la [plantilla de Content Analytics](/help/content-analytics/report/report.md#template).


>[!NOTE]
>
>Content Analytics aprovecha los servicios de IA/ML que pueden producir resultados inexactos o engañosos. Por lo tanto, utilice su criterio para revisar y validar los resultados generados por AI/ML.
>
>Puede usar la ficha **[!UICONTROL Comentarios]**, disponible en ![InfoOutline](/help/assets/icons/InfoOutline.svg) en la interfaz principal, para proporcionar comentarios sobre los resultados generados por inteligencia artificial o aprendizaje automático.
>

>[!NOTE]
>
>Si ha adquirido la licencia del complemento Escudo de privacidad y seguridad, tenga en cuenta que (cualquier dato generado) las experiencias y los recursos, sujetos a Content Analytics, no están cubiertos por el etiquetado DULE ni por las claves gestionadas por el cliente. Además, Content Analytics no es un servicio compatible con HIPAA.
>


>[!MORELIKETHIS]
>
>[Creación de informes de Content Analytics](report/report.md)
>>[Configurar Adobe Analytics](config/configuration.md)
>>[Cálculo de salidas hacia otro sitio y tasa de salidas hacia otro sitio en Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446?profile.language=es#M454)
>

