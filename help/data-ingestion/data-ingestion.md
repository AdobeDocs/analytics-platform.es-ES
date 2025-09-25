---
title: Información general sobre la ingesta de datos
description: Comprender las distintas formas de ingerir datos en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: ec56bc657961b2e4e8318ab14cd676288398462f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 85%

---

# Información general sobre la ingesta de datos

Tiene varias opciones de ingesta de datos en Customer Journey Analytics. En algunas de ellas se presupone que desea mover los datos tradicionales de Adobe Analytics, en otras se presupone que utiliza datos ingeridos en Adobe Experience Platform.

>[!IMPORTANT]
>
>En todos los casos, los datos que desee _utilizar_ en Customer Journey Analytics, en realidad _se ingieren_ en Adobe Experience Platform.


La arquitectura de Customer Journey Analytics de alto nivel se muestra aquí:

![Arquitectura de Customer Journey Analytics](/help/getting-started/assets/cja-overview.svg)

Esta arquitectura ilustra cómo el Recorrido de cliente de Analytics le permite:

* Combine varios conjuntos de datos ![Data](/help/assets/icons/Data.svg) en una [conexión](/help/connections/overview.md).
* Defina y configure las dimensiones ![Dimensiones](/help/assets/icons/Dimensions.svg) y las métricas ![Evento](/help/assets/icons/Event.svg) en una [vista de datos](/help/data-views/data-views.md), según los campos disponibles de los conjuntos de datos que definió en su conexión.
* Generar informes ![ViewTable](/help/assets/icons/ViewTable.svg) y visualizaciones (como la línea ![Line](/help/assets/icons/GraphTrend.svg) y el área ![Area](/help/assets/icons/GraphAreaStacked.svg)) en [proyectos](/help/analysis-workspace/home.md) en función de las dimensiones y métricas de las vistas de datos.

Los conjuntos de datos de la arquitectura pueden proceder de varias fuentes:

* datos por lotes,

* datos de streaming,

* datos de una implementación actual de Adobe Analytics,

* datos del seguimiento de su sitio web o aplicación móvil mediante el SDK móvil o web de Adobe Experience Platform,

* datos de seguimiento de una aplicación de escritorio, un juego de consola, descodificador o dispositivo IoT mediante la API de servidor de Adobe Experience Platform Edge Network o

* datos procedentes de un proveedor de datos de terceros para el que Adobe proporciona un conector de origen.

Y puede tener muchos de estos conjuntos de datos.

Esta sección de la documentación proporciona guías de inicio rápido para varios escenarios.

## Priorización y latencia de la ingesta

Ahora puede introducir los datos de evento en Customer Journey Analytics en un plazo de 90 minutos (SLT), independientemente de si los datos tienen 24 horas, 48 horas o 7 días de antigüedad.

Tenga en cuenta que esta posibilidad difiere según el paquete de SKU que haya adquirido su compañía:

* Ingesta de prioridades básica: datos de 24 horas de antigüedad dentro de un procesamiento SLT de 90 minutos (disponible para **CJA Foundation** y **CJA Select**)

* Ingesta de prioridades intermedia: datos de 72 horas de antigüedad dentro de un procesamiento SLT de 90 minutos (disponible para **CJA Prime**)

* Ingesta de prioridades avanzada: datos de una semana de antigüedad dentro de un procesamiento SLT de 90 minutos (disponible para **CJA Ultimate**)

## Ingesta y uso de datos de Adobe Analytics tradicional

Ya tiene Adobe Analytics implementado y desea ingerir estos datos en Adobe Experience Platform y utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos de Adobe Analytics tradicional](./analytics.md) para obtener más información.


## Ingesta y uso de datos mediante Edge Network

### Uso del SDK web de Adobe Experience Platform

Quiere analizar su sitio web con la tecnología de Adobe, migrando potencialmente desde otra solución o iniciando el seguimiento del comportamiento de su visitante. Quiere seguir las prácticas recomendadas de Adobe para la implementación, que consisten en utilizar los SDK de Adobe Experience Platform y Edge Network, para ingerir los datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante el SDK web de Adobe Experience Platform](./aepwebsdk.md) para obtener más información.

### Uso del SDK móvil de Adobe Experience Platform

Quiere analizar su aplicación móvil con la tecnología de Adobe, migrando potencialmente desde otra solución o iniciando el seguimiento del comportamiento de su visitante en la aplicación desde cero. Quiere seguir las prácticas recomendadas de Adobe para la implementación, que consisten en utilizar los SDK de Adobe Experience Platform y Edge Network, para ingerir los datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante el SDK móvil de Adobe Experience Platform](./aepmobilesdk.md) para obtener más información.

### Uso de la API del servidor de Adobe Experience Platform Edge Network

Quiere analizar la aplicación de escritorio o un juego tal como en una consola de juegos, el uso de una aplicación de streaming de vídeo en un descodificador o su dispositivo IoT con tecnología Adobe. Migrando posiblemente desde otra solución o inicio del seguimiento del comportamiento de un visitante en estos dispositivos desde cero. Quiere seguir las prácticas recomendadas de Adobe para la implementación, que consisten en utilizar las API del servidor Adobe Experience Platform Edge Network y Edge Network, para la ingesta de datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante la API del servidor de Adobe Experience Platform Edge Network](./serverapi.md) para obtener más información.

## Ingesta y uso de datos por lotes

Tiene disponibles datos relevantes por lotes que proporcionan detalles que pueden ayudarle a comprender mejor el comportamiento del cliente y analizar las interacciones con él. Algunos ejemplos de estos datos por lotes son archivos sin formato CSV, JSON o Parquet de un sistema CRM, una aplicación de lealtad u otra solución para la cual Adobe no proporciona actualmente un conector de origen. La ingesta de estos datos por lotes en Adobe Experience Platform le permite utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos por lotes](./batch.md) para obtener más información.

## Ingesta y uso de datos de streaming

Tiene una fuente de datos relevante, como un sistema CRM, un sistema ERP o cualquier otro origen que proporcione detalles que puedan ayudarle a comprender mejor el comportamiento del cliente y analizar las interacciones con él. La fuente de datos puede comunicarse a través de HTTP o de la infraestructura de streaming en la nube pública, pero para ella, Adobe no proporciona actualmente un conector de origen. La ingesta de estos datos de streaming en Adobe Experience Platform en tiempo real permite utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos de streaming](./streaming.md) para obtener más información.

## Ingesta y uso de datos mediante conectores de origen

Tiene datos disponibles de un origen compatible con un conector de origen. Los conectores de origen son ajustes configurables que le permiten ingerir datos desde la aplicación Adobe, de origen y de terceros en Adobe Experience Platform. Consulte [Información general sobre los conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es) para obtener información general sobre los conectores de origen disponibles. Con el conector de origen puede ingerir fácilmente datos del origen en Adobe Experience Platform y, a continuación, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante conectores de origen](./sources.md) para obtener más información.

## Ingesta y uso de datos ad hoc

Tiene datos ad hoc disponibles que solo requieren un único conjunto de datos en Experience Platform y no requieren la configuración de un esquema Experience Data Model (XDM). Este escenario se denomina esquema ad hoc. Los esquemas ad hoc se utilizan en varios flujos de trabajo de ingesta de datos para Experience Platform, incluida la ingesta de archivos CSV y la creación de determinados tipos de conexiones de origen.

Ver [Ingesta y uso de datos ad hoc](./adhoc.md)

>[!MORELIKETHIS]
>
>Blog: [Análisis detallado del procesamiento y la ingesta de datos en Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091?profile.language=es)

