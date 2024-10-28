---
title: Crear un esquema para el Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 35%

---

# Crear un flujo de datos para utilizarlo con Customer Journey Analytics

>[!NOTE]
>
>Esta documentación se debe usar después de completar el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Siga los pasos de esta página solo después de completar todos los pasos anteriores generados dinámicamente para su organización.
>
>Después de completar los pasos de esta página, continúe siguiendo los pasos de actualización que se generaron dinámicamente para su organización desde el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Una secuencia de datos representa la configuración del lado del servidor al implementar los SDK web y móvil de Adobe Experience Platform. Al recopilar datos con los SDK de Adobe Experience Platform, los datos se envían a Adobe Experience Platform Edge Network. Es la secuencia de datos la que determina a qué servicios se reenvían los datos.

En la configuración, quiere que los datos recopilados del sitio web se envíen a su conjunto de datos en Adobe Experience Platform.

Para configurar la secuencia de datos, debe hacer lo siguiente:

1. En Adobe Experience Platform, seleccione **[!UICONTROL Datastreams]** de [!UICONTROL RECOPILACIÓN DE DATOS] en el carril izquierdo.

1. Seleccione **[!UICONTROL Nueva secuencia de datos]**.

1. Asigne un nombre y describa su secuencia de datos. Seleccione el esquema en la lista [!UICONTROL Esquema de eventos].

   ![Nuevo conjunto de datos](assets/new-datastream.png)

1. Seleccione **[!UICONTROL Guardar]**.

1. Continúe siguiendo los pasos de actualización generados dinámicamente para su organización desde el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

