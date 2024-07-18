---
title: Información general sobre la ingesta de datos
description: Comprender las distintas formas de ingerir datos en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: dca1cc33058ba57815c3534ab21da86d5247531a
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 65%

---

# Información general sobre la ingesta de datos

Tiene varias opciones al ingerir datos en Customer Journey Analytics. En algunas de ellas se presupone que desea mover los datos tradicionales de Adobe Analytics, en otras se presupone que utiliza datos ingeridos en Adobe Experience Platform.

>[!IMPORTANT]
>
>En todos los casos, los datos que desee _utilizar_ en Customer Journey Analytics, en realidad _se ingieren_ en Adobe Experience Platform.

Consulte la arquitectura de Customer Journey Analytics de nivel general mostrada anteriormente en [Información general](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es):

![Arquitectura de Customer Journey Analytics descrita en esta sección](./assets/cja-architecture.png)

El conjunto de datos de la arquitectura anterior puede proceder de varios orígenes:

- datos por lotes,

- datos de streaming,

- datos de una implementación actual de Adobe Analytics,

- datos de seguimiento de su sitio web/aplicación móvil mediante el SDK web/móvil de Adobe Experience Platform,

- datos de seguimiento de una aplicación de escritorio, un juego de consola, un decodificador o un dispositivo IoT mediante la API de Adobe Experience Platform Edge Network Server, o

- datos procedentes de un proveedor de datos de terceros para el que Adobe proporciona un conector de origen.

Y puede tener muchos de estos conjuntos de datos.

Esta sección de la documentación proporciona guías de inicio rápido para varios escenarios.

## Priorización y latencia de la ingesta

Puede introducir los datos de evento en Customer Journey Analytics en un plazo de 90 minutos (SLT), independientemente de si los datos tienen 24 horas, 48 horas o 7 días.

Tenga en cuenta que esta posibilidad difiere según el paquete de SKU que haya adquirido su compañía:

- Ingesta de prioridad básica: datos de 24 horas de antigüedad en un procesamiento de SLT de 90 minutos (disponibles para **CJA Foundation** y **CJA Select**)

- Ingesta de prioridad intermedia: datos de 72 horas dentro del procesamiento SLT de 90 minutos (disponible para **CJA Prime**)

- Ingesta de prioridad avanzada: datos de una semana de antigüedad en un procesamiento de SLT de 90 minutos (disponible para **CJA Ultimate**)

## Ingesta y uso de datos de Adobe Analytics tradicional

Ya tiene Adobe Analytics implementado y desea ingerir estos datos en Adobe Experience Platform y utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos de Adobe Analytics tradicional](./analytics.md) para obtener más información.


## Ingesta y uso de datos mediante el Edge Network

### Uso del SDK web de Adobe Experience Platform

Desea analizar su sitio web con tecnología de Adobe, con la posibilidad de migrar desde otra solución o comenzar a rastrear el comportamiento de su persona. Quiere seguir las prácticas recomendadas de Adobe para la implementación, que consisten en utilizar los SDK de Adobe Experience Platform y Edge Network, para ingerir los datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante el SDK web de Adobe Experience Platform](./aepwebsdk.md) para obtener más información.

### Uso del SDK de Adobe Experience Platform Mobile

Desea analizar su aplicación móvil con tecnología de Adobe, con la posibilidad de migrar desde otra solución o empezar a rastrear el comportamiento de una persona en la aplicación desde cero. Quiere seguir las prácticas recomendadas de Adobe para la implementación, que consisten en utilizar los SDK de Adobe Experience Platform y Edge Network, para ingerir los datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante el SDK para móviles de Adobe Experience Platform](./aepmobilesdk.md) para obtener más información.

### Uso de la API de Adobe Experience Platform Edge Network Server

Desea analizar la aplicación de escritorio, el juego tal como se juega en una consola de juegos, el uso de una aplicación de transmisión de vídeo en un decodificador o su dispositivo IoT con tecnología de Adobe. Posible migración desde otra solución o inicio del seguimiento del comportamiento de una persona en estos dispositivos desde cero. Desea seguir las prácticas recomendadas de Adobe para la implementación de, que utiliza las API y el Edge Network de Adobe Experience Platform Edge Network Server, para la ingesta de datos. A continuación, puede utilizar, combinar y analizar los datos ingeridos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante la API de Adobe Experience Platform Edge Network Server](./serverapi.md) para obtener más información.

## Ingesta y uso de datos por lotes

Tiene disponibles datos relevantes por lotes que proporcionan detalles que pueden ayudarle a comprender mejor el comportamiento del cliente y analizar las interacciones con él. Algunos ejemplos de estos datos por lotes son archivos sin formato CSV, JSON o Parquet de un sistema CRM, una aplicación de fidelidad u otra solución para la cual Adobe no proporciona actualmente un conector de origen. La ingesta de estos datos por lotes en Adobe Experience Platform le permite utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos por lotes](./batch.md) para obtener más información.

## Ingesta y uso de datos de streaming

Tiene una fuente de datos relevante, como un sistema CRM, un sistema ERP o cualquier otro origen que proporcione detalles que puedan ayudarle a comprender mejor el comportamiento del cliente y analizar las interacciones con él. La fuente de datos puede comunicarse a través de HTTP o de la infraestructura de streaming en la nube pública, pero para ella, Adobe no proporciona actualmente un conector de origen. La ingesta de estos datos de streaming en Adobe Experience Platform en tiempo real permite utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos de streaming](./streaming.md) para obtener más información.

## Ingesta y uso de datos mediante conectores de origen

Tiene datos disponibles de un origen compatible con un conector de origen. Los conectores de origen son ajustes configurables que le permiten ingerir datos desde la aplicación Adobe, de origen y de terceros en Adobe Experience Platform. Consulte [Información general sobre los conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es) para obtener información general sobre los conectores de origen disponibles. Con el conector de origen puede ingerir fácilmente datos del origen en Adobe Experience Platform y, a continuación, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante conectores de origen](./sources.md) para obtener más información.
