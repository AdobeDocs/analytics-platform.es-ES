---
title: Creación de un esquema para Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 48%

---

# Creación de una secuencia de datos para utilizarla con Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Creación de una secuencia de datos en Adobe Experience Platform."
>abstract="Una secuencia de datos es una ubicación intermedia que pasa los datos a todos los servicios configurados. Cree esta ubicación en Adobe Experience Platform.<br><br>La creación inicial de una secuencia de datos en la interfaz de Platform solo lleva unos minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Una secuencia de datos representa la configuración del lado del servidor al implementar los SDK web y móvil de Adobe Experience Platform. Al recopilar datos con los SDK de Adobe Experience Platform, los datos se envían a Adobe Experience Platform Edge Network. Es la secuencia de datos la que determina a qué servicios se reenvían los datos.

En la configuración, debe configurar el conjunto de datos para enviar los datos recopilados a su conjunto de datos en Adobe Experience Platform.

>[!NOTE]
>
>Los siguientes pasos solo son necesarios para implementaciones de Adobe Analytics que utilizan AppMeasurement o la extensión de Analytics (etiquetas).
>
>Si la implementación de Adobe Analytics utiliza Web SDK o la extensión Web SDK, el conjunto de datos ya existe en el entorno de Adobe Analytics.

Para configurar la secuencia de datos, debe hacer lo siguiente:

1. En Adobe Experience Platform, seleccione **[!UICONTROL Datastreams]** de [!UICONTROL RECOPILACIÓN DE DATOS] en el carril izquierdo.

1. Seleccione **[!UICONTROL Nueva secuencia de datos]**.

1. Asigne un nombre y describa su secuencia de datos. Seleccione el esquema en la lista [!UICONTROL Esquema de eventos].

   ![Nuevo conjunto de datos](assets/new-datastream.png)

1. Seleccione **[!UICONTROL Guardar]**.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).
