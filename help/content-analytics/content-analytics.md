---
title: Resumen de análisis de contenido
description: Información general sobre el análisis de contenido
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 8c257279353112df583b46d87ea17749a75867e2
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 0%

---

# Resumen de análisis de contenido

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Análisis de contenido. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}

El análisis de contenido ayuda a los especialistas en marketing a comprender cómo afecta el contenido a los indicadores de rendimiento clave que ha definido una empresa. Además de los datos de comportamiento, Content Analytics recopila datos sobre cómo se consume el contenido y cómo afecta a las unidades de contenido. Por ejemplo, ¿responden mejor los clientes a un tono de voz específico, a un pallet de color específico o a temas específicos? Esta información, junto con plantillas y flujos de trabajo de creación de informes diseñados específicamente, puede ayudarle a realizar un análisis aún mejor y a obtener perspectivas más profundas de los datos de recorrido del cliente en Customer Journey Analytics.

El análisis de contenido usa una IA y un servicio de aprendizaje automático basado en **funciones** para desglosar el contenido en componentes y atributos. Al crear un perfil de metadatos estructurado en todo el contenido, puede analizar qué contenido y qué atributos de ese contenido generan resultados empresariales.

Además de la creación de este perfil de metadatos estructurado, Content Analytics proporciona un **servicio de identidad** que identifica los recursos y las experiencias mediante un único identificador. El servicio de identidad puede reconocer cuándo aparece exactamente el mismo recurso en más de un lugar. Cuando esto sucede, las dos instancias de recursos se tratan como la misma, lo que permite una vista más holística del uso y el consumo de contenido.

## Valor

El análisis de contenido proporciona valor en un nivel creciente:

1. Contenido **uso**: con el análisis de contenido obtiene información sobre qué recursos reciben impresiones y dónde reciben los recursos. Estas perspectivas le ayudan a ver si los recursos se infrautilizan o se utilizan en exceso en las propiedades web.
1. **participaciones** de contenido: los análisis de contenido pueden proporcionar perspectivas de participación, como la tasa promedio de clics entre recursos con determinados atributos. Estas perspectivas le ayudan a determinar si tipos específicos de experiencias siguen siendo eficaces.
1. Contenido **recorridos**: además, cuando se combinan con todos los demás datos disponibles en Experience Platform, puede obtener información adicional sobre sus recorridos de contenido. Por ejemplo, si un contenido específico genera conversiones, además de la participación. Y con ese conocimiento puedes determinar el ROI de los tipos de contenido.
1. Contenido **personalizado**: en última instancia, el análisis de contenido le permite actuar según sus perspectivas y utilizar estas perspectivas para determinar cómo gastar dinero en contenido. Por ejemplo, ¿debo enviar tipos de contenido específicos a audiencias específicas? ¿Qué contenido me ofrece oportunidades de alta personalización?

## Terminología

El análisis de contenido utiliza los siguientes términos clave:

![Assets y experiencias](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Experiencia**: Una experiencia es texto en una página web que se puede reproducir usando la URL usada por el usuario inicial que visitó esa página web. Cada experiencia obtiene un identificador único.
* **Recurso**: un recurso es un fragmento de contenido individual y único, como una imagen. Cada recurso también obtiene un identificador único.
* **Atributo**: un atributo es un elemento de metadatos descriptivo asociado a una experiencia o recurso. Algunos ejemplos de un atributo son: estilo de fotografía, legibilidad, estrategia de persuasión, color de objeto, color de fondo.

## Funcionamiento

El análisis de contenido utiliza datos de vista de imágenes web recopilados en conjuntos de datos de evento en Experience Platform. Estos datos se pueden recopilar mediante los distintos métodos disponibles: Experience Platform Edge Network (Web SDK, API de servidor) o conector de origen de Analytics.

![Análisis de contenido - Cómo funciona](assets/how-it-works.png)


1. Cuando un usuario visita un sitio, Experience Platform Web SDK, configurado para el análisis de contenido, registra las interacciones con el contenido.
1. El servicio de ensamblador de funciones y el servicio de identidad procesan los datos visitados.
1. Los resultados de estos servicios (componentes, atributos e identidades) se utilizan para actualizar los conjuntos de datos específicos de análisis de contenido relevantes en Experience Platform.
1. Los datos de análisis de contenido, junto con los datos de comportamiento y otros conjuntos de datos de búsqueda, se pueden utilizar en una configuración de Customer Journey Analytics (conexión, vista de datos y Workspace). Esa configuración proporciona la base para las perspectivas únicas a nivel de macro sobre el contenido.

>[!NOTE]
>
>El análisis de contenido aprovecha AI/ML. Los resultados (para la caracterización de experiencias y recursos) pueden ser inexactos.
>


>[!MORELIKETHIS]
>
>[Informes de análisis de contenido](report/report.md)
>[Configurar análisis de contenido](config/configuration.md)
