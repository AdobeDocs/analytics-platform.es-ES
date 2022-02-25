---
title: Introducción a Customer Journey Analytics
description: Comprenda los requisitos previos y el flujo de trabajo necesarios para implementar Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 04ceeb9e9a048a224ea957ad42bc54cbd4b3f249
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 89%

---

# Introducción a Customer Journey Analytics

Para implementar Customer Journey Analytics, debe seguir este flujo de trabajo. Algunas tareas iniciales se realizan en Adobe Experience Platform y otras, en Customer Journey Analytics.

## Requisitos previos

Customer Journey Analytics está disponible para los clientes que

* son clientes de Adobe Analytics [Select, Prime o Ultimate](https://www.adobe.com/es/analytics/compare-adobe-analytics-packages.html), y
* se proporcionan para [Adobe Experience Platform](https://www.adobe.com/es/experience-platform.html) y
* ha adquirido la SKU de Customer Journey Analytics.

## Flujo de trabajo

| Tarea | Detalles |
| --- | --- |
| **Paso 1: introducir sus datos en Adobe Experience Platform** | Este paso, realizado en Adobe Experience Platform, incluye varios subpasos:<ul><li>**Paso 1a: Preparar el esquema de datos**: uso del modelo de datos de [Adobe Experience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) para estandarizar los datos de experiencia del cliente y [definir esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en) para la administración de experiencias del cliente.</li><li>**Paso 1b: Crear un conjunto de datos basado en el esquema**: Los datos de Platform constan de conjuntos de datos, como conjuntos de datos de correo electrónico, de CRM, de POS, de Adobe Analytics, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede [crear un conjunto de datos en Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html%3Flang%3Dnl).</li><li>**Paso 1c: Ingestar datos en Experience Platform**: Uso del conector de Adobe Analytics Platform integrado para incorporar datos tradicionales de Adobe Analytics a Platform. Puede crear una conexión de origen por grupo de informes. Consulte [Crear una conexión de origen con Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) en la documentación de Adobe Experience Platform. Una vez creada la conexión, se crea automáticamente un esquema de destinatario y un conjunto de datos para contener los datos entrantes. Además, se rellenan los datos de forma retroactiva y se introducen hasta 13 meses de datos históricos. Cuando se complete la introducción inicial, puede continuar con `Step 2` para crear una conexión entre este conjunto de datos de Analytics y Customer Journey Analytics. O bien, puede ingerir otros tipos de datos mediante la ingesta [por lotes](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en), la [transmisión por secuencias](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en) u [otros conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en).</li></ul> |
| **Paso 2: crear conexiones entre conjuntos de datos de Platform y Customer Journey Analytics** | Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform el Espacio de trabajo. Para informar sobre conjuntos de datos de Experience Platform, primero debe establecer una conexión entre conjuntos de datos en Experience Platform y Espacio de trabajo.<br>Consulte [Crear una conexión](/help/connections/create-connection.md). |
| **Paso 3: crear vistas de datos** | Una vista de datos es una vista “filtrada” de los datos. Puede crear distintas vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Puede crear varias vistas de datos para un único conjunto de datos.<br>Consulte [Crear una vista de datos](/help/data-views/create-dataview.md). |
| **Paso 4: informar sobre los datos de canales cruzados el Espacio de trabajo** | Después de crear conexiones y vistas de datos, analice los datos que ha introducido con la potencia y flexibilidad de Analysis Workspace.<br>Consulte [Realizar análisis básicos](/help/analysis-workspace/perform-basic-analysis.md) y [Realizar análisis avanzados](/help/analysis-workspace/perform-adv-analysis.md). |
