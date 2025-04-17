---
title: Información general sobre el análisis de contenido
description: Información general sobre el análisis de contenido
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 1acb6ee56ec3d1c5ae21bb857205a0b9cc66cea0
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 50%

---

# Información general sobre el análisis de contenido

{{release-limited-testing}}

El análisis de contenido ayuda a los especialistas en marketing a comprender cómo afecta el contenido a los indicadores de rendimiento clave que ha definido una empresa. Además de los datos de comportamiento, Content Analytics recopila datos sobre cómo se consume el contenido y cómo afecta a las unidades de contenido. Por ejemplo, ¿responden mejor los clientes a un tono de voz específico, a una paleta de colores específica o a temas específicos? Esta información, junto con los flujos de trabajo de creación de informes diseñados específicamente y las plantillas, puede ayudarle a realizar un análisis aún mejor y a obtener conocimientos más profundos sobre los datos de recorrido del cliente en Customer Journey Analytics.

El análisis de contenido utiliza un **servicio de caracterización** basado en la IA y el aprendizaje automático para descomponer el contenido en componentes y atributos. Al crear un perfil de metadatos estructurado en todo el contenido, puede analizar qué contenido y qué atributos de ese contenido generan resultados empresariales.

Además de la creación de este perfil de metadatos estructurado, el análisis de contenido proporciona un **servicio de identidad** que identifica recursos y experiencias mediante un único identificador. El servicio de identidad puede reconocer cuándo aparece exactamente el mismo recurso en más de un lugar. Cuando esto sucede, las instancias de este recurso se tratan como el mismo recurso, lo que permite una vista más holística del uso y el consumo de contenido.

## Valor

El análisis de contenido proporciona valor en un nivel creciente:

1. **Uso** de contenido: con el análisis de contenido obtiene información sobre qué recursos reciben impresiones y dónde reciben los recursos. Esta información le ayuda a ver si los recursos se infrautilizan o se utilizan en exceso en las propiedades web.
1. **Participaciones** del contenido: los análisis de contenido pueden proporcionar información sobre la participación, como la tasa promedio de clics entre recursos con determinados atributos. Esta información le ayuda a determinar si tipos específicos de experiencias siguen siendo eficaces.
1. **Recorridos** del contenido: además, cuando se combinan con todos los demás datos disponibles en Experience Platform, puede obtener información adicional sobre los recorridos de su contenido. Por ejemplo, si un contenido específico genera conversiones, además de la participación. Y con ese conocimiento puede determinar el retorno de la inversión de los tipos de contenido.
1. **Personalización** del contenido: en última instancia, el análisis de contenido le permite actuar en función de sus informaciones y utilizar estas informaciones para determinar cómo gastar dinero en contenido. Por ejemplo, ¿debo enviar tipos de contenido específicos a públicos específicos? ¿Qué contenido me ofrece oportunidades de alta personalización?

## Terminología

El análisis de contenido utiliza los siguientes términos clave:

![Recursos y experiencias](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Experiencia**: una experiencia es todo texto de una página web que se puede reproducir con la URL que usó el usuario inicial que visitó la página web. Cada experiencia obtiene un identificador único. Los cambios en la página que producen cambios en el HTML de la página resultan en una nueva experiencia.
* **Recurso**: un recurso es un fragmento de contenido individual y único, como una imagen. Cada recurso también obtiene un identificador único y un ID perceptual. Un ID perceptual es un identificador que se comparte con recursos que son visualmente idénticos. Los ID perceptuales ayudan a deduplicar recursos que pueden tener una URL de recurso diferente y, por lo tanto, un ID de recurso diferente, pero que son perceptualmente idénticos.
* **Atributo**: un atributo es un elemento de metadatos descriptivo asociado a una experiencia o recurso. Algunos ejemplos de un atributo son: estilo de fotografía, legibilidad, estrategia de persuasión, color de los objetos, color de fondo.

## Funcionamiento

El análisis de contenido utiliza datos de la vista de imágenes web recopilados en conjuntos de datos de eventos en Experience Platform. Estos datos se pueden recopilar mediante los distintos métodos disponibles: Experience Platform Edge Network (SDK web, API de servidor) o conector de origen de Analytics.

![Análisis de contenido: funcionamiento](assets/aca-overview.gif)


1. Cuando un usuario visita un sitio [configurado para Content Analytics](config/configuration.md), Experience Platform Web SDK registra las impresiones y las interacciones con el contenido.
1. El servicio de identidad y características procesa estas interacciones. Ese proceso consiste en un servicio de recuperación que vuelve a visitar las versiones públicas de las direcciones URL configuradas que definen las interacciones. Para todas estas direcciones URL recuperadas, el servicio de identidad identifica de forma exclusiva las experiencias y los recursos. Además, el servicio de personalización aplica servicios de IA/ML para descubrir experiencias, recursos, metadatos y atributos.
1. Los resultados de estos servicios ([componentes, atributos e identidades](/help/content-analytics/report/components.md)) se utilizan para actualizar los conjuntos de datos de análisis de contenido específicos relevantes en Experience Platform.
1. Los datos de análisis de contenido, junto con los datos de comportamiento y otros datos de búsqueda, se pueden usar en una configuración de Customer Journey Analytics ([Conexión](/help/connections/overview.md), [Vista de datos](/help/data-views/data-views.md) y [Workspace](/help/analysis-workspace/home.md)). Esa configuración proporciona la base para obtener información única a nivel de macro sobre el contenido. <br/>Puede iniciar sus informes y análisis de Content Analytics con la [plantilla de Content Analytics](/help/content-analytics/report/report.md#template).

>[!NOTE]
>
>Content Analytics aprovecha los servicios de IA/ML que pueden producir resultados inexactos o engañosos. Por lo tanto, utilice su criterio para revisar y validar los resultados generados por AI/ML.
>
>Puede usar la ficha **[!UICONTROL Comentarios]**, disponible en ![InfoOutline](/help/assets/icons/InfoOutline.svg) en la interfaz principal, para proporcionar comentarios sobre los resultados generados por inteligencia artificial o aprendizaje automático.
>

>[!NOTE]
>
>Si tiene licencia para el complemento Escudo de seguridad y privacidad, tenga en cuenta que (cualquier dato generado a partir de) las experiencias y los recursos, sujetos a Content Analytics, no están cubiertos por el etiquetado DULE ni por las claves gestionadas por el cliente.
>


>[!MORELIKETHIS]
>
>[Creación de informes del análisis de contenido](report/report.md)
>[Configurar Adobe Analytics](config/configuration.md)
>

