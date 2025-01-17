---
title: Crear un esquema para el Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 41965bcd5ae8252fbf2ceda0d2b633ec6dc0e9a3
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 23%

---

# Crear un flujo de datos para utilizarlo con Customer Journey Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

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
