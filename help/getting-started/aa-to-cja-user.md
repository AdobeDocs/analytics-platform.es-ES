---
title: CJA User Guide for Adobe Analytics users
description: What to consider from a user's perspective when your company moves data from Adobe Analytics to Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 64ba233212fa6bfc1d63c122e1f8dcebe6735f39
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 6%

---

# CJA User Guide for Adobe Analytics users

If your organization is starting to employ Customer Journey Analytics (CJA), you may notice some similarities and differences between traditional Analytics and CJA. This page aims to explain those differences to help acclimate your organization to the new implementation and reporting workflow. This page also provides additional resources on new concepts, and further steps to make your journey as an analyst easier and more successful.

Several features in CJA are renamed and redesigned to align with industry standards. Some updated terminology includes segments, virtual report suites, classifications, customer attributes, and container names. The limitations of eVars and props no longer exist, in favor of flexible custom dimensions and metrics.

## What hasn&#39;t changed

Much of what you are familiar with on the reporting side has not changed.

* [](/help/analysis-workspace/home.md) Workspace operates the same as it does in traditional Adobe Analytics.
* [](/help/mobile-app/home.md)
* [](/help/report-builder/report-buider-overview.md) (Before this version of Report Builder, you couldn’t use in on Mac unless you ran it on VMware.) This version doesn’t support traditional AA data request yet.

## Changes to reporting

You have access to a lot more cross-channel data to analyze. For example, you can create a workspace project that analyzes performance of multiple channels, provided these datasets are ingested by your organization and included in data views used by CJA (see &quot;Changes to data architecture&quot; below).

![](assets/cross-channel.png)

## Changes to data architecture {#architecture}

CJA gets its data from Adobe Experience Platform. Experience Platform lets you centralize and standardize customer data and content from any system or channel and applies data science and machine learning to improve the design and delivery of personalized experiences.

Customer data in the Experience Platform is stored as datasets, which consist of a schema and batches of data. Para obtener más información sobre la plataforma, consulte la [Descripción general de arquitectura de Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

[](/help/connections/create-connection.md) [](/help/data-views/data-views.md) Data views are conceptually similar to virtual report suites, and are the basis of reporting in CJA. Since Experience Platform sources all data for reporting, report suites no longer exist as a container for data.

A connection lets your Analytics Admin integrate datasets from Adobe Experience Platform into CJA, included in the following video:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe offers multiple ways to bring data in to Adobe Experience Platform, including report suite data through the Adobe Analytics Source Connector or the Web SDK. Existing implementations from multiple report suites can be combined in Experience Platform. The connections and data views that are based on these data sets can combine data that previously existed in separate report suites.

## Changes to the concept of virtual report suites {#data-views}

[](/help/data-views/create-dataview.md) These changes make general settings like timezone and session time-out intervals configurable and retroactive. Individual variable settings like attribution and expiration can also be customized on a report or data view level. These settings are non-destructive and retroactive.

Notice that the report suite selector in the top right now lets you choose from available data views:

![](assets/data-views.png)

[](/help/data-views/data-views-usecases.md)

## Changes to the concept of eVars and props

 Unlimited schema elements are available, including dimensions, metrics, and list fields. These are mapped to unlimited schema elements including dimensions, metrics and list fields in Experience Platform. All visit and attribution settings applied after processing rules in Adobe Analytics now apply at query time in Customer Journey Analytics.

With this flexibility, you may run into situations in which a single schema field can be used as both a dimensions and a metric to support different tracking needs.

## Changes to the concept of segments

Adobe has renamed the &quot;segments&quot; component to &quot;filters&quot; to better align with industry standards and provide better distinction with segments in Adobe Experience Platform.

  If you want to move existing Adobe Analytics segments to Customer Journey Analytics, see the following video:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

[!DNL Customer Journey Analytics]

In addition to the concept of segments changing, segment containers are also updated.

* **** El contenedor [!UICONTROL Persona] incluye todas las visitas y vistas de página de los visitantes en un lapso de tiempo específico.
* **** El contenedor [!UICONTROL Sesión] le permite identificar interacciones de páginas, campañas o conversiones para una sesión específica.
* **** El contenedor [!UICONTROL Persona] incluye todas las visitas y vistas de página de los visitantes en un lapso de tiempo específico.

## Changes to the concept of calculated metrics

Calculated metrics are similarly named between traditional Analytics and CJA.   If you want to move Adobe Analytics calculated metrics to Customer Journey Analytics, see the following video:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Changes to variable attribution and expiration settings

 [](/help/data-views/component-settings/persistence.md)

You can have multiple versions of the same variable in the same data view. For example, you can have one Tracking Code dimension that expires after 30 days, and another that expires at the end of a session. Both of these Tracking Code dimensions use the same source data, but use different attribution settings.

You can also have multiple data views based on the same connection. For example, you can have one data view with a session timeout of 30 minutes, and another with a session timeout of 15 minutes. Both data views appear in the upper right selector so you can seamlessly transition between them.

## Changes to the concept of classifications

&quot;Classifications&quot; are now known as &quot;Lookup datasets&quot;. Lookup datasets are used to look up values or keys found in your Event or Profile data. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento a los nombres de producto. [](/help/use-cases/b2b.md)

## Changes to the concept of customer attributes

&quot;Customer attributes&quot; are now known as &quot;Profile datasets&quot;.  For example, it allows you to upload CRM data about your customers. Puede elegir qué ID de persona desea incluir. [!DNL Experience Platform]

## Changes to how Adobe identifies visitors

CJA expands the concepts of identities beyond ECIDs to include any ID you want to use, including Customer ID, Cookie ID, Stitched ID, User ID, Tracking Code, and so on. [](/help/connections/cca/overview.md) Any user setting up a Workspace project in CJA must understand the IDs used across the datasets. See the following video that highlights the use of identities in CJA:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Changes to the concept of low-traffic dimension item

 CJA has fewer limitations to high cardinality fields. Changes to the reporting architecture allows Analysis Workspace to report on many more unique dimension items. [](../analysis-workspace/workspace-faq/long-tail.md)
