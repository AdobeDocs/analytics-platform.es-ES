---
title: Información general de Content Analytics
description: Información general sobre Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 0%

---

# Información general de Content Analytics

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Content Analytics. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}

Content Analytics ayuda a los especialistas en marketing a comprender cómo afecta el contenido a los indicadores de rendimiento clave que ha definido una empresa. Además de los datos de comportamiento, Content Analytics recopila datos sobre cómo se consume el contenido y cómo afecta a las unidades de contenido. Por ejemplo, ¿responden mejor los clientes a un tono de voz específico, a un pallet de color específico o a temas específicos? Esta información, junto con plantillas y flujos de trabajo de creación de informes diseñados específicamente, puede ayudarle a realizar un análisis aún mejor y a obtener perspectivas más profundas de los datos de recorrido del cliente en Customer Journey Analytics.

Content Analytics usa una IA y un servicio de **característica** de aprendizaje automático para desglosar el contenido en componentes y atributos. Al crear un perfil de metadatos estructurado en todo el contenido, puede analizar qué contenido y qué atributos de ese contenido generan resultados empresariales.

Además de crear este perfil de metadatos estructurado, Content Analytics proporciona un **servicio de identidad** que identifica los recursos y experiencias con un solo identificador. El servicio de identidad puede reconocer cuándo aparece el mismo recurso en más de un lugar. Cuando esto sucede, las dos instancias de recursos se tratan como la misma, lo que permite una vista más holística del uso y el consumo de contenido.

## Valor

Content Analytics proporciona valor en un nivel creciente:

1. Contenido **uso**: con Content Analytics obtiene información sobre qué recursos reciben impresiones y dónde los recursos reciben impresiones. Estas perspectivas le ayudan a ver si los recursos se infrautilizan o se utilizan en exceso en las propiedades web.
1. **participaciones** de contenido: Content Analytics puede proporcionar perspectivas de participación, como la tasa promedio de clics entre recursos con determinados atributos. Estas perspectivas le ayudan a determinar si tipos específicos de experiencias siguen siendo eficaces.
1. Contenido **recorridos**: además, cuando se combinan con todos los demás datos disponibles en Experience Platform, puede obtener información adicional sobre sus recorridos de contenido. Por ejemplo, si un contenido específico genera conversiones, además de la participación. Y con ese conocimiento puedes determinar el ROI de los tipos de contenido.
1. Contenido **personalizado**: en última instancia, Content Analytics le permite actuar según sus perspectivas y utilizar estas perspectivas para determinar cómo gastar dinero en contenido. Por ejemplo, ¿debo enviar tipos de contenido específicos a audiencias específicas? ¿Qué contenido me ofrece oportunidades de alta personalización?

## Terminología

Content Analytics utiliza los siguientes términos clave:

![Assets y experiencias](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Experiencia**: Una experiencia es texto en una página web que se puede reproducir usando la URL usada por el usuario inicial que visitó esa página web. Cada experiencia obtiene un identificador único.
* **Recurso**: un recurso es un fragmento de contenido individual y único, como una imagen. Cada recurso también obtiene un identificador único.
* **Atributo**: un atributo es un elemento de metadatos descriptivo asociado a una experiencia o recurso. Algunos ejemplos de un atributo son: estilo de fotografía, legibilidad, estrategia de persuasión, color de objeto, color de fondo.

## Funcionamiento

Content Analytics utiliza datos de vista de imágenes web recopilados en conjuntos de datos de evento en Experience Platform. Estos datos se pueden recopilar mediante los distintos métodos disponibles: Experience Platform Edge Network (Web SDK, API de servidor) o conector de origen de Analytics.

![Content Analytics - Cómo funciona](assets/aca-overview.gif)


1. Cuando un usuario visita un sitio configurado para Content Analytics, Experience Platform Web SDK registra las interacciones con el contenido.
1. El servicio de ensamblador de funciones y el servicio de identidad procesan los datos visitados. Ese proceso consiste en un rastreador que vuelve a visitar las versiones públicas de las direcciones URL configuradas y aplica servicios AI/ML.
1. Los resultados de estos servicios (componentes, atributos e identidades) se utilizan para actualizar los conjuntos de datos específicos de análisis de contenido relevantes en Experience Platform.
1. Los datos de análisis de contenido, junto con los datos de comportamiento y otros conjuntos de datos de búsqueda, que utiliza en la configuración de Customer Journey Analytics (combinación de Conexión, Vista de datos y Workspace). Esa configuración proporciona la base para obtener información única a nivel de macro sobre el contenido.

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
>[Informes de Content Analytics](report/report.md)
>[Configurar Content Analytics](config/configuration.md)
>