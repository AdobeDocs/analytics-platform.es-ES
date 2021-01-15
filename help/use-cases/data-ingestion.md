---
title: Opciones de ingesta de datos para Customer Journey Analytics
description: Comprender las distintas formas de ingerir datos en Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 8a3a868ff4e2fbbcdf83ff7769382c6a92f78ec2
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 63%

---


# Opciones de ingesta de datos para Customer Journey Analytics

Tiene varias opciones de ingesta de datos en Customer Journey Analytics. Algunos de ellos suponen que desea mover los datos tradicionales de Adobe Analytics, algunos de los cuales suponen que los ingiere directamente desde Adobe Experience Platform. Esta referencia proporciona pasos de alto nivel para seguir, con vínculos a información más detallada.

## Ingesta de datos de Adobe Analytics tradicional

Este flujo de trabajo utiliza el conector de datos de Adobe Analytics y varía en función de si utiliza DTM o Launch como Administrador de etiquetas.

### A través de la Dynamic Tag Management (DTM)

1. [Crear una capa de datos](https://docs.adobe.com/content/help/es-ES/analytics/implementation/prepare/data-layer.html), si aún no lo ha hecho. Una capa de datos es un marco de objetos de JavaScript del sitio que contiene todos los valores de variables utilizados en la implementación. Permite un mayor control y un mantenimiento más sencillo en la implementación.
1. Usar [DTM](https://docs.adobe.com/content/help/es-ES/analytics/implementation/other/dtm/dtm-implementation-overview.html) para implementar el código en el sitio para la recopilación de datos si aún no lo ha hecho. Dynamic Tag Management proporciona una única capa de datos que transmite datos de múltiples fuentes.
1. Crear un [Conector de origen de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) en Adobe Experience Platform. Este conector de origen ingresará los datos de Analytics en Experience Platform, en un marco de trabajo normalizado denominado [Sistema de modelo de datos de experiencia (XDM)](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/home.html).
1. Usar [Customer Journey Analytics](https://docs.adobe.com/content/help/es-ES/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

### A través de Launch

1. [Crear una capa de datos](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), si aún no lo ha hecho. Una capa de datos es un marco de objetos de JavaScript del sitio que contiene todos los valores de variables utilizados en la implementación. Permite un mayor control y un mantenimiento más sencillo en la implementación.
1. Usar [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/es-ES/analytics/implementation/launch/overview.html) para implementar código en el sitio para la recopilación de datos si aún no lo ha hecho. Launch es una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Launch ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio..
1. Crear un [Conector de origen de Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) en Adobe Experience Platform. Este conector de origen ingresará los datos de Analytics en Experience Platform, en un marco de trabajo normalizado denominado [Sistema de modelo de datos de experiencia (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Usar [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

## Ingesta de datos mediante el SDK web de Adobe Experience Platform y la red Edge

[Adobe Experience Platform Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) SDKes una biblioteca JavaScript del lado del cliente que permite a los clientes de Adobe Experience Cloud interactuar con los distintos servicios del Experience Cloud a través de Adobe Experience Platform Edge Network.

1. [Configure la extensión AEP Web SDK en ](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) Launchpara enviar datos a Adobe Experience Cloud desde propiedades web, a través de Adobe Experience Platform Edge Network.
1. Usar [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

## Ingesta de datos con ingestión por lotes y transmisión de la ingestión

Adobe Experience Platform reúne los datos de varias fuentes para ayudar a los especialistas en marketing a comprender mejor el comportamiento de sus clientes. La ingestión de datos de Adobe Experience Platform representa los múltiples métodos mediante los cuales la plataforma ingesta datos de estas fuentes, así como la forma en que se mantienen los datos dentro del lago de datos para su uso por los servicios de plataforma descendente.

### Ingesta por lotes

1. Configure [Ingesta por lotes](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch) para permitir la ingesta de datos en Adobe Experience Platform como archivos por lotes. Los datos que se están ingeriendo pueden ser los datos de perfil de un archivo plano en un sistema CRM (como un archivo de parqué) o los datos que se ajustan a un esquema conocido en el registro del Modelo de datos de experiencia (XDM).
1. Usar [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

### Transmisión por flujo continuo

1. Configure [la inserción de flujo](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming) para enviar datos desde dispositivos cliente y servidor al Experience Platform en tiempo real.
1. Usar [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

## Introducir datos de Google Analytics para analizarlos en Customer Journey Analytics

Consulte este tutorial sobre cómo [Analizar datos de Google Analytics mediante Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives) para obtener pasos detallados.

## Utilice la API de inserción masiva de datos para obtener datos en Analytics y, a continuación, ingrese mediante el conector de origen de Adobe en Experience Platform

1. [Utilice la ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) API de inserción masiva de datos para enviar datos de recopilación de servidor a Adobe Analytics. Permite enviar archivos con formato CSV que contengan datos de evento.
1. [Cree un ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) conector de origen de Adobe Analytics para llevar estos datos de consumidor a Adobe Experience Platform.
1. Usar [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.