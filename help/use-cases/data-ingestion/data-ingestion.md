---
title: Opciones de ingesta de datos para Customer Journey Analytics
description: Comprender las distintas formas de ingerir datos en Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T11:01:56.579Z'
TQID: 'https://experienceleague.adobe.com/Uqoyk9k3hEOB90hzLtXhoYtmfX18wmXPHp-AWxgNIwU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: bfef374d-acfd-4c57-bf74-a2b36053c545id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 827
ht-degree: 86%

---

# Opciones de ingesta de datos para Customer Journey Analytics

Tiene varias opciones de ingesta de datos en Customer Journey Analytics. Algunos de ellos suponen que desea mover los datos tradicionales de Adobe Analytics, algunos de los cuales suponen que los ingiere directamente desde Adobe Experience Platform. Esta referencia proporciona pasos de alto nivel para seguir, con vínculos a información más detallada.

## Ingesta de datos de Adobe Analytics tradicional

Este flujo de trabajo utiliza el conector de origen de Analytics y varía en función de si utiliza DTM o Launch como Administrador de etiquetas.

### Mediante etiquetas en Adobe Experience Platform (anteriormente denominado [!UICONTROL Launch])

1. [Crear una capa de datos](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=es), si aún no lo ha hecho. Una capa de datos es un marco de objetos de JavaScript del sitio que contiene todos los valores de variables utilizados en la implementación. Permite un mayor control y un mantenimiento más sencillo en la implementación.
1. Usar [etiquetas de Adobe Experience Platform](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=es) para implementar código en el sitio para la recopilación de datos si aún no lo ha hecho. Esta solución de administración de etiquetas le permite implementar código de Analytics junto con otros requisitos de etiquetado. Las ofertas ofrecen integraciones con otras soluciones y productos, y le permiten implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.
1. Crear un [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) en Adobe Experience Platform. Este conector de origen ingresará los datos de Analytics en Experience Platform, en un marco de trabajo normalizado denominado [Sistema de modelo de datos de experiencia (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es). Consulte también [Uso de los datos de grupos de informes de Adobe Analytics en Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=es) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

## Ingesta de datos mediante el SDK web de Adobe Experience Platform y Edge Network

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) es una biblioteca JavaScript del lado del cliente que permite a los clientes de Adobe CX Enterprise interactuar con los distintos servicios de CX Enterprise a través de Adobe Experience Platform Edge Network.

1. [Configure la extensión Adobe Experience Platform Web SDK en tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=es) para enviar datos a CX Enterprise desde propiedades web, a través de Adobe Experience Platform Edge Network.
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=es) para crear una o varias [conexiones](/help/connections/create-connection.md) y [vistas de datos](/help/data-views/data-views.md) que informarán al sistema de informes entre canales.

## Ingesta de datos con ingesta por lotes y de streaming

Adobe Experience Platform reúne datos de varios orígenes para ayudar a los especialistas en marketing a comprender mejor el comportamiento de sus clientes. La ingesta de datos de Adobe Experience Platform representa los múltiples métodos mediante los cuales Platform ingiere datos de estos orígenes, así como la forma en que se mantienen los datos dentro del lago de datos para que los usen los servicios de Platform secundarios.

### Ingesta por lotes

1. Configure [Ingesta por lotes](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=es#batch) para permitir la ingesta de datos en Adobe Experience Platform como archivos por lotes. Los datos que se están ingiriendo pueden ser los datos de perfil de un archivo plano de un sistema CRM (como un archivo de Parquet) o los datos que se ajustan a un esquema conocido en el registro del modelo de datos de experiencia (XDM).
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=es) para crear una o varias [conexiones](/help/connections/create-connection.md) y [vistas de datos](/help/data-views/data-views.md) que informarán al sistema de informes entre canales.

### Ingesta de streaming

1. Configure la [Ingesta de streaming](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=es#streaming) para enviar datos del cliente y de dispositivos del lado del servidor a Experience Platform en tiempo real.
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=es) para crear una o varias [conexiones](/help/connections/create-connection.md) y [vistas de datos](/help/data-views/data-views.md) que informarán al sistema de informes entre canales.

## Introducción de datos de Google Analytics para analizarlos en Customer Journey Analytics

Consulte este tutorial sobre cómo [Analizar datos de Google Analytics mediante Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html) para ver los pasos detallados.

## Utilice la API de inserción masiva de datos para obtener datos en Analytics y, a continuación, realice la ingesta mediante el conector de origen de Analytics en Experience Platform

1. [Utilice la API de inserción masiva de datos](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para enviar datos de colección del lado del servidor a Adobe Analytics. Permite enviar archivos con formato CSV que contienen datos de evento.
1. [Cree un conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) para llevar estos datos de consumidor a Adobe Experience Platform.
1. Usar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=es) para crear una o varias [conexiones](/help/connections/create-connection.md) y [vistas de datos](/help/data-views/data-views.md) que informarán al sistema de informes entre canales.
