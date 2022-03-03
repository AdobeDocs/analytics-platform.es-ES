---
title: Introducción a Customer Journey Analytics
description: Comprenda los requisitos previos y el flujo de trabajo necesarios para implementar Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: a0b282feed28c24565c5f7cc87c7fefab3e00057
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
| **Paso 1: Si va a migrar de Adobe Analytics a CJA, consulte la guía de migración.** | [Guía de migración de Adobe Analytics a Customer Journey Analytics](/help/getting-started/aa-to-cja.md) |
| **Paso 2: introducir sus datos en Adobe Experience Platform** | Este paso, realizado en Adobe Experience Platform, incluye varios subpasos:<ul><li>**Paso 2a: Preparar el esquema de datos**: uso del modelo de datos de [Adobe Experience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) para estandarizar los datos de experiencia del cliente y [definir esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en) para la administración de experiencias del cliente.</li><li>**Paso 2b: Crear un conjunto de datos basado en el esquema**: Los datos de Platform constan de conjuntos de datos, como conjuntos de datos de correo electrónico, de CRM, de POS, de Adobe Analytics, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede [crear un conjunto de datos en Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html%3Flang%3Dnl).</li><li>**Paso 2c: Ingesta de datos en el Experience Platform**: Aquí tiene varias opciones. Consulte la [casos de uso de ingesta de datos](/help/use-cases/data-ingestion.md) para obtener más información. |
| **Paso 2: crear conexiones entre conjuntos de datos de Platform y Customer Journey Analytics** | Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform el Espacio de trabajo. Para informar sobre conjuntos de datos de Experience Platform, primero debe establecer una conexión entre conjuntos de datos en Experience Platform y Espacio de trabajo.<br>Consulte [Crear una conexión](/help/connections/create-connection.md). |
| **Paso 3: crear vistas de datos** | Una vista de datos es una vista “filtrada” de los datos. Puede crear distintas vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Puede crear varias vistas de datos para un único conjunto de datos.<br>Consulte [Crear una vista de datos](/help/data-views/create-dataview.md). |
| **Paso 4: informar sobre los datos de canales cruzados el Espacio de trabajo** | Después de crear conexiones y vistas de datos, analice los datos que ha introducido con la potencia y flexibilidad de Analysis Workspace.<br>Consulte [Realizar análisis básicos](/help/analysis-workspace/perform-basic-analysis.md) y [Realizar análisis avanzados](/help/analysis-workspace/perform-adv-analysis.md). |
