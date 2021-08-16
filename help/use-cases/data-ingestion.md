---
title: Opciones de ingesta de datos para Customer Journey Analytics
description: Comprender las distintas formas de ingerir datos en Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
source-git-commit: 15312a57f0f122d22d0575f2008d547bcb8ab2ed
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 98%

---

# Opciones de ingesta de datos para Customer Journey Analytics

Tiene varias opciones de ingesta de datos en Customer Journey Analytics. Algunos de ellos suponen que desea mover los datos tradicionales de Adobe Analytics, algunos de los cuales suponen que los ingiere directamente desde Adobe Experience Platform. Esta referencia proporciona pasos de alto nivel para seguir, con vínculos a información más detallada.

## Ingesta de datos de Adobe Analytics tradicional

Este flujo de trabajo utiliza el conector de datos de Adobe Analytics y varía en función de si utiliza DTM o Launch como Administrador de etiquetas.

### A través de la Dynamic Tag Management (DTM)

1. [Crear una capa de datos](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=es), si aún no lo ha hecho. Una capa de datos es un marco de objetos de JavaScript del sitio que contiene todos los valores de variables utilizados en la implementación. Permite un mayor control y un mantenimiento más sencillo en la implementación.
1. Usar [DTM](https://experienceleague.adobe.com/docs/analytics/implementation/other/dtm/dtm-implementation-overview.html) para implementar el código en el sitio para la recopilación de datos si aún no lo ha hecho. Dynamic Tag Management proporciona una única capa de datos que transmite datos de múltiples fuentes.
1. Crear un [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) en Adobe Experience Platform. Este conector de origen ingresará los datos de Analytics en Experience Platform, en un marco de trabajo normalizado denominado [Sistema de modelo de datos de experiencia (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es).
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=es) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

### A través de Launch

1. [Crear una capa de datos](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html), si aún no lo ha hecho. Una capa de datos es un marco de objetos de JavaScript del sitio que contiene todos los valores de variables utilizados en la implementación. Permite un mayor control y un mantenimiento más sencillo en la implementación.
1. Usar [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=es) para implementar código en el sitio para la recopilación de datos si aún no lo ha hecho. Launch es una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Launch ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio..
1. Crear un [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) en Adobe Experience Platform. Este conector de origen ingresará los datos de Analytics en Experience Platform, en un marco de trabajo normalizado denominado [Sistema de modelo de datos de experiencia (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html).
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

## Ingesta de datos mediante el SDK web de Adobe Experience Platform y la red Edge

[SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) es una biblioteca JavaScript del lado del cliente que permite a los clientes de Adobe Experience Cloud interactuar con los distintos servicios de Experience Cloud a través de Adobe Experience Platform Edge Network.

1. [Configure la extensión web SDK de AEP en Launch](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=en) para enviar datos a Adobe Experience Cloud desde propiedades web, a través de Adobe Experience Platform Edge Network.
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

## Ingesta de datos con ingesta por lotes y de la transmisión

Adobe Experience Platform reúne datos de varias fuentes para ayudar a los especialistas en marketing a comprender mejor el comportamiento de sus clientes. La ingesta de datos de Adobe Experience Platform representa los múltiples métodos mediante los cuales Platform ingiere datos de estas fuentes, así como la forma en que se mantienen los datos dentro del lago de datos para que los usen los servicios de Platform secundarios.

### Ingesta por lotes

1. Configure [Ingesta por lotes](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=es#batch) para permitir la ingesta de datos en Adobe Experience Platform como archivos por lotes. Los datos que se están ingiriendo pueden ser los datos de perfil de un archivo plano de un sistema CRM (como un archivo de Parquet) o los datos que se ajustan a un esquema conocido en el registro del modelo de datos de experiencia (XDM).
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

### Ingesta de la transmisión

1. Configure la [Ingesta de la transmisión](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=es#streaming) para enviar datos del cliente y de dispositivos del lado del servidor a Experience Platform en tiempo real.
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

## Introducción de datos de Google Analytics para analizarlos en Customer Journey Analytics

Consulte este tutorial sobre cómo [Analizar datos de Google Analytics mediante Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=es#objectives) para ver los pasos detallados.

## Utilice la API de inserción masiva de datos para obtener datos en Analytics y, a continuación, realice la ingesta mediante el conector de origen de Adobe en Experience Platform

1. [Utilice la API de inserción masiva de datos](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para enviar datos de colección del lado del servidor a Adobe Analytics. Permite enviar archivos con formato CSV que contienen datos de evento.
1. [Cree un conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) para llevar estos datos de consumidor a Adobe Experience Platform.
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.
