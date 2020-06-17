---
title: Introducción a Customer Journey Analytics
description: Introducción a Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 16bca45f2576d3feef8129d558fad6f236852cb9
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 71%

---


# Introducción a Customer Journey Analytics

Para implementar Customer Journey Analytics, debe seguir este flujo de trabajo. Algunas tareas iniciales se realizan en Adobe Experience Platform y otras, en Customer Journey Analytics.

## Requisitos previos

Customer Journey Analytics está disponible para los clientes que

* son clientes de Adobe Analytics [Select, Prime o Ultimate](https://www.adobe.com/es/analytics/compare-adobe-analytics-packages.html), y
* Se proporcionan para [Adobe Experience Platform](https://www.adobe.com/es/experience-platform.html) y
* Ha adquirido la SKU de Customer Journey Analytics.

## Flujo de trabajo

| Tarea | Detalles |
|---|---|
| **Paso 1: introducir sus datos en Adobe Experience Platform** | Este paso, realizado en Adobe Experience Platform, incluye varios subpasos:<ul><li>**Paso 1a: Preparar el esquema** de datos: Utilice el Modelo de datos de [Adobe Experience (XDM)](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/home.translate.html) para estandarizar los datos de experiencia del cliente y [definir esquemas](https://docs.adobe.com/content/help/es-ES/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) para la gestión de la experiencia del cliente.</li><li>**Paso 1b: Cree un conjunto de datos basado en el esquema**: Los datos de Platform constan de conjuntos de datos, como conjuntos de datos de correo electrónico, conjuntos de datos de CRM, conjuntos de datos de POS, conjuntos de datos de Analytics de Adobe, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede crear un conjunto de datos [en Experience Platform](https://docs.adobe.com/content/help/es-ES/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).</li><li>**Paso 1c: Ingestar datos en el Experience Platform**: Utilice el conector de Platform de Adobe Analytics incorporado para incorporar datos tradicionales de Adobe Analytics a Platform. Puede crear una conexión de origen por grupo de informes. Consulte [Crear una conexión de origen con Adobe Analytics](https://docs.adobe.com/content/help/es-ES/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) en la documentación de Adobe Experience Platform. Una vez creada la conexión, se crea automáticamente un esquema de destinatario y un conjunto de datos para contener los datos entrantes. Además, se rellenan los datos de forma retroactiva y se introducen hasta 13 meses de datos históricos. Cuando se complete la introducción inicial, puede continuar con `Step 2` para crear una conexión entre este conjunto de datos de Analytics y Customer Journey Analytics. O bien, puede ingerir otros tipos de datos mediante la ingesta [por](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)lotes, la[transmisión por secuencias](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)o [otros conectores](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)de origen.</li></ul> |
| **Paso 2: crear conexiones entre conjuntos de datos de Platform y Customer Journey Analytics** | Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform en Workspace. Para informar sobre los conjuntos de datos de Experience Platform, primero debe establecer una conexión entre los conjuntos de datos en Experience Platform y Workspace.<br>Consulte [Crear una conexión](/help/connections/create-connection.md). |
| **Paso 3: crear vistas de datos** | Una vista de datos es una vista &quot;filtrada&quot; de los datos. Puede crear distintas vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Puede crear varias vistas de datos para un único conjunto de datos.<br>Consulte [Crear una vista de datos](/help/data-views/create-dataview.md). |
| **Paso 4: informar sobre los datos de canales cruzados en Workspace** | Después de crear conexiones y vistas de datos, analice los datos que ha introducido con la potencia y flexibilidad de Analysis Workspace.<br>Consulte [Realizar análisis básicos](/help/analysis-workspace/perform-basic-analysis.md) y [Realizar análisis avanzados](/help/analysis-workspace/perform-adv-analysis.md). |
