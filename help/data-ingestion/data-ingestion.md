---
title: Información general sobre la ingesta de datos
description: Comprender las distintas formas de ingerir datos en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 70%

---

# Información general sobre la ingesta de datos

Tiene varias opciones al ingerir datos en Customer Journey Analytics. En algunas de ellas se presupone que desea mover los datos tradicionales de Adobe Analytics, en otras se presupone que utiliza datos ingeridos en Adobe Experience Platform.

>[!IMPORTANT]
>
>En todos los casos, los datos que desee _utilizar_ en Customer Journey Analytics, en realidad _se ingieren_ en Adobe Experience Platform.


Consulte la arquitectura de Customer Journey Analytics de nivel general mostrada anteriormente en [Información general](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es):

![La arquitectura del Customer Journey Analytics se describe en esta sección](./assets/cja-architecture.png)

El conjunto de datos de la arquitectura anterior puede proceder de varios orígenes:

- datos por lotes,

- datos de streaming,

- datos de una implementación actual de Adobe Analytics,

- datos de seguimiento de su sitio web/aplicación móvil mediante el SDK web/móvil de Adobe Experience Platform,

- datos de seguimiento de una aplicación de escritorio, un juego de consola, un decodificador o un dispositivo IoT mediante la API del servidor de red Adobe Experience Platform Edge, o

- datos procedentes de un proveedor de datos de terceros para el que Adobe proporciona un conector de origen.

Y puede tener muchos de estos conjuntos de datos.

Esta sección de la documentación proporciona guías de inicio rápido para varios escenarios.

## Ingesta y uso de datos de Adobe Analytics tradicional

Ya tiene Adobe Analytics implementado y desea ingerir estos datos en Adobe Experience Platform y utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos de Adobe Analytics tradicional](./analytics.md) para obtener más información.


## Ingesta y uso de datos a través de la red perimetral

### Uso del SDK web de Adobe Experience Platform

Desea analizar su sitio web con tecnología de Adobe, con la posibilidad de migrar desde otra solución o comenzar a rastrear el comportamiento de su persona. Quiere seguir las prácticas recomendadas de Adobe para la implementación, que consisten en utilizar los SDK de Adobe Experience Platform y Edge Network, para ingerir los datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante el SDK web de Adobe Experience Platform](./aepwebsdk.md) para obtener más información.

### Uso del SDK de Adobe Experience Platform Mobile

Desea analizar su aplicación móvil con tecnología de Adobe, con la posibilidad de migrar desde otra solución o empezar a rastrear el comportamiento de una persona en la aplicación desde cero. Quiere seguir las prácticas recomendadas de Adobe para la implementación, que consisten en utilizar los SDK de Adobe Experience Platform y Edge Network, para ingerir los datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante el SDK para móviles de Adobe Experience Platform](./aepmobilesdk.md) para obtener más información.

### Uso de la API del servidor de red perimetral de Adobe Experience Platform

Desea analizar la aplicación de escritorio, el juego tal como se juega en una consola de juegos, el uso de una aplicación de transmisión de vídeo en un decodificador o su dispositivo IoT con tecnología de Adobe. Posible migración desde otra solución o inicio del seguimiento del comportamiento de una persona en estos dispositivos desde cero. Desea seguir las prácticas recomendadas de Adobe para la implementación de, que utiliza las API de servidor de red perimetral de Adobe Experience Platform y la red perimetral, para la ingesta de datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante la API del servidor de red perimetral de Adobe Experience Platform](./serverapi.md) para obtener más información.

## Ingesta y uso de datos por lotes

Tiene disponibles datos relevantes por lotes que proporcionan detalles que pueden ayudarle a comprender mejor el comportamiento del cliente y analizar las interacciones con él. Algunos ejemplos de estos datos por lotes son archivos sin formato CSV, JSON o Parquet de un sistema CRM, una aplicación de fidelidad u otra solución para la cual Adobe no proporciona actualmente un conector de origen. La ingesta de estos datos por lotes en Adobe Experience Platform le permite utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos por lotes](./batch.md) para obtener más información.

## Ingesta y uso de datos de streaming

Tiene una fuente de datos relevante, como un sistema CRM, un sistema ERP o cualquier otro origen que proporcione detalles que puedan ayudarle a comprender mejor el comportamiento del cliente y analizar las interacciones con él. La fuente de datos puede comunicarse a través de HTTP o de la infraestructura de streaming en la nube pública, pero para ella, Adobe no proporciona actualmente un conector de origen. La ingesta de estos datos de streaming en Adobe Experience Platform en tiempo real permite utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos de streaming](./streaming.md) para obtener más información.

## Ingesta y uso de datos mediante conectores de origen

Tiene datos disponibles de un origen compatible con un conector de origen. Los conectores de origen son ajustes configurables que le permiten ingerir datos desde la aplicación Adobe, de origen y de terceros en Adobe Experience Platform. Consulte [Información general sobre los conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es) para obtener información general sobre los conectores de origen disponibles. Con el conector de origen puede ingerir fácilmente datos del origen en Adobe Experience Platform y, a continuación, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante conectores de origen](./sources.md) para obtener más información.
