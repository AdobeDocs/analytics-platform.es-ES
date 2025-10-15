---
title: Configuración de la recopilación de medios de streaming para Customer Journey Analytics
description: Obtenga información sobre cómo configurar la recopilación de medios de streaming para Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 380ed5c9ee0c21ea9855a41728afec040637ce65
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 20%

---

# Configuración de la recopilación de medios de streaming para Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Configuración e implementación de Media Edge"
>abstract="Si planea utilizar la recopilación de medios de streaming con Customer Journey Analytics, debe realizar selecciones específicas en determinados pasos del proceso de actualización. Por ejemplo, debe añadir el grupo de campos Detalles de interacciones de Media Analytics al esquema, habilitar Media Analytics en la secuencia de datos y mucho más."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Al igual que en Adobe Analytics, la recopilación de medios de streaming se puede utilizar para recopilar datos de medios de streaming para utilizarlos en Customer Journey Analytics. Si utiliza la recopilación de medios de streaming con Adobe Analytics, debe incluirla en sus planes de actualización a Customer Journey Analytics.

A medida que vaya realizando los pasos para actualizar de Adobe Analytics a Customer Journey Analytics, realice las siguientes selecciones para tener en cuenta los datos de recopilación de medios de streaming:

* Al crear el esquema para Customer Journey Analytics, incluya el grupo de campos `MediaAnalytics Interaction Details`.

  Para obtener más información sobre cómo agregar este grupo de campos, consulte [Configurar el esquema en Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) en la Guía de recopilación de medios de streaming.

  Para obtener información acerca de cómo crear el esquema, vea [Crear un esquema personalizado para utilizarlo con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Al configurar la secuencia de datos para Customer Journey Analytics, habilite Media Analytics.

  Para obtener más información sobre cómo habilitar esta opción, consulte [Configuración de un conjunto de datos en Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) en la Guía de recopilación de medios de streaming.

  Para obtener información acerca de cómo crear la secuencia de datos, vea [Crear una secuencia de datos para usar con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

  >[!NOTE]
  >
  >Si la implementación de Adobe Analytics ya está utilizando Experience Platform Web SDK, este paso no es necesario.

* Al crear una vista de datos para Customer Journey Analytics, incluya los campos de esquema necesarios para la recopilación de medios de streaming.

  Asegúrese de asignar estos campos de esquema a los valores correctos en el objeto XDM.

  Para obtener más información sobre los campos obligatorios, consulte [Crear una vista de datos en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) en la Guía de recopilación de medios de streaming.

  Para obtener información sobre cómo crear la vista de datos, consulte [Crear una vista de datos en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
