---
title: Información general sobre la incorporación de datos
description: Comprender las distintas formas de ingerir datos en el Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
source-git-commit: 3331f41590509ef38cb67802335414ca3de5ff94
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 3%

---

# Información general sobre la incorporación de datos

Tiene varias opciones al ingerir datos en el Customer Journey Analytics. Algunos de ellos suponen que desea mover los datos tradicionales de Adobe Analytics, algunos de los cuales suponen que utiliza datos incorporados en Adobe Experience Platform.

>[!IMPORTANT]
>
>En todos los casos, los datos que desee _use_ en Customer Journey Analytics es _ingested_ en Adobe Experience Platform.


Consulte la arquitectura de Customer Journey Analytics de alto nivel que se muestra anteriormente en [Información general](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es):

![Customer Journey Analytics](./assets/cja-architecture.png)

El conjunto de datos de la arquitectura anterior puede proceder de varias fuentes:

- datos por lotes,

- flujo continuo de datos,

- datos de una implementación actual de Adobe Analytics,

- datos del seguimiento de su sitio web o aplicación móvil mediante el SDK web/móvil de Adobe Experience Platform, o

- datos procedentes de un proveedor de datos de terceros para el que Adobe proporciona un conector de origen.

Y puede tener muchos de estos conjuntos de datos.

Esta sección de la documentación proporciona guías de inicio rápidas para varios escenarios.

## Ingesta y uso de datos de Adobe Analytics tradicional

Ya tiene Adobe Analytics implementado y desea ingerir estos datos en Adobe Experience Platform y utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos de Adobe Analytics tradicional](./analytics.md) para obtener más información.

## Ingesta y uso de datos mediante el SDK web de Adobe Experience Platform y la red perimetral

Desea analizar su sitio web con tecnología de Adobe, migrando potencialmente de otra solución o iniciando el seguimiento del comportamiento de su visitante. Desea seguir las prácticas recomendadas de Adobe para la implementación, que utiliza los SDK de Adobe Experience Platform y la red perimetral, para introducir los datos. A continuación, puede utilizar, combinar y analizar los datos introducidos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante el SDK web de Adobe Experience Platform y la red perimetral](./aepwebsdk.md) para obtener más información.

## Ingesta y uso de datos por lotes

Tiene disponibles datos relevantes de lote que proporcionan detalles que pueden ayudarle a comprender mejor el comportamiento del cliente y analizar las interacciones con él. Algunos ejemplos de estos datos por lotes son archivos planos en formato CSV, JSON o Parquet de un sistema CRM, una aplicación de fidelidad u otra solución para los que el Adobe no proporciona actualmente un conector de origen. La ingesta de estos datos por lotes en Adobe Experience Platform le permite utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos por lotes](./batch.md) para obtener más información.

## Ingesta y uso de datos de flujo continuo

Tiene una fuente de datos relevante, como un sistema CRM, un sistema ERP o cualquier otra fuente que proporcione detalles que puedan ayudarle a comprender mejor el comportamiento del cliente y analizar las interacciones con él. Esa fuente de datos puede comunicarse a través de HTTP o de la infraestructura de flujo en la nube pública, pero para la que el Adobe no proporciona actualmente un conector de origen. La ingesta de estos datos de flujo continuo en Adobe Experience Platform en tiempo real permite utilizarlos, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos de flujo continuo](./streaming.md) para obtener más información.

## Ingesta y uso de datos mediante conectores de origen

Tiene datos disponibles de un origen compatible con un conector de origen. Los conectores de origen son configuraciones configurables que le permiten introducir datos de la aplicación de Adobe, de origen y de terceros en Adobe Experience Platform. Consulte [Información general sobre conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es) para obtener información general sobre los conectores de origen disponibles. Con el conector de origen puede introducir fácilmente datos del origen en Adobe Experience Platform y, a continuación, combinarlos y analizarlos con datos de otros canales y fuentes de datos en Customer Journey Analytics.

Consulte [Ingesta y uso de datos mediante conectores de origen](./sources.md) para obtener más información.
