---
title: Introducción a Análisis de Viaje del Cliente
description: Introducción a Análisis de Viaje del Cliente.
translation-type: tm+mt
source-git-commit: 7ff761d9a2f2ebbe0e051e5785f12048ca2ea937
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 1%

---


# Introducción a Análisis de Viaje del Cliente

Para implementar el análisis de viajes del cliente, debe seguir este flujo de trabajo. Algunas tareas iniciales se realizan en Adobe Experience Platform y otras en Customer Journey Analytics.

## Requisitos previos

El análisis de viajes del cliente está disponible para los clientes que

* Son clientes [de Adobe Analytics Select, Prime o Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) , y
* Están aprovisionados para la plataforma [de](https://www.adobe.com/es/experience-platform.html)Adobe Experience y
* Ha adquirido la SKU de Análisis de viajes del cliente

## Flujo de trabajo

| Tarea | Detalles |
|---|---|
| **Paso 1: Obtener sus datos en Adobe Experience Platform** | Este paso, realizado en Adobe Experience Platform, incluye varios subpasos:<ul><li>**Paso 1a: Preparar el esquema** de datos: Utilice el Modelo de datos de [Adobe Experience (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) para estandarizar los datos de experiencia del cliente y [definir esquemas](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) para la gestión de la experiencia del cliente.</li><li>**Paso 1b: Cree un conjunto de datos basado en el esquema**: Los datos de la plataforma constan de conjuntos de datos, como conjuntos de datos de correo electrónico, conjuntos de datos de CRM, conjuntos de datos de POS, conjunto de datos de Adobe Analytics, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede crear un conjunto de datos [en la plataforma](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)de experiencias.</li><li>**Paso 1c: Ingestar datos en la plataforma** de experiencias: Utilice el conector de plataforma de Adobe Analytics incorporado para incorporar datos tradicionales de Adobe Analytics a la plataforma. Puede crear una conexión de origen por grupo de informes. Consulte [Creación de una conexión de origen con Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) en la documentación de Adobe Experience Platform. Una vez creada la conexión, se crea automáticamente un esquema de destinatario y un conjunto de datos para contener los datos entrantes. Además, se rellenan los datos de forma retroactiva y se ingieren hasta 13 meses de datos históricos. Cuando se complete la ingestión inicial, puede continuar con `Step 2` la creación de una conexión entre este conjunto de datos de Analytics y el análisis de viajes del cliente. O bien, puede ingerir otros tipos de datos mediante la ingesta [por](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)lotes, la[transmisión por secuencias](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)o [otros conectores](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)de origen.</li></ul> |
| **Paso 2: Creación de conexiones entre conjuntos de datos de plataforma y Análisis del viaje del cliente** | Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform en Workspace. Para informar sobre los conjuntos de datos de la plataforma de experiencia, primero debe establecer una conexión entre los conjuntos de datos de la plataforma de experiencia y del espacio de trabajo.<br>Consulte [Creación de una conexión](/help/connections/create-connection.md). |
| **Paso 3: Crear vistas de datos** | Una vista de datos es una vista &quot;filtrada&quot; de los datos. Puede crear diferentes vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Puede crear varias vistas de datos para un único conjunto de datos.<br>Consulte [Creación de una vista](/help/data-views/create-dataview.md)de datos. |
| **Paso 4: Informar sobre los datos de canales cruzados en Workspace** | Después de crear conexiones y vistas de datos, analice los datos que ha introducido con la potencia y flexibilidad de Espacio de trabajo de Análisis.<br>Consulte [Realizar análisis](/help/projects/perform-basic-analysis.md) básica y [Realizar análisis](/help/projects/perform-adv-analysis.md)avanzada. |
