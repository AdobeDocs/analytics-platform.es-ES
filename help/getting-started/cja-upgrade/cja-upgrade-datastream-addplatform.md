---
title: Crear un esquema para Customer Journey Analytics
description: Más información sobre la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 100%

---

# Añadir Platform como servicio a la secuencia de datos {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Añadir Adobe Experience Platform como servicio a la secuencia de datos"
>abstract="Una secuencia de datos necesita uno o varios servicios a los que enviar los datos. Configure Adobe Experience Platform como servicio en el conjunto de datos.<br><br>Añadir servicios a una secuencia de datos es un proceso sencillo que solo lleva unos minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Debe existir una secuencia de datos antes de completar los pasos de esta sección. El momento y el modo en que se creó la secuencia de datos dependen de la implementación de Adobe Analytics, de la siguiente manera:

* Si la implementación de Adobe Analytics utiliza el SDK web o la extensión del SDK web, significa que la secuencia de datos estaba disponible para el entorno de Adobe Analytics antes del proceso de actualización.

* En el caso de otras implementaciones de Adobe Analytics, crear un conjunto de datos forma parte del proceso de actualización, tal como se describe en [Crear una secuencia de datos para usar con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Con la secuencia de datos disponible, debe añadir Platform como servicio:

1. En la interfaz de usuario de Adobe Experience Platform, seleccione **[!UICONTROL Secuencias de datos]** desde [!UICONTROL RECOPILACIÓN DE DATOS] en el carril izquierdo.

1. Seleccione la secuencia de datos configurada anteriormente. <!--true?-->

1. Seleccione **[!UICONTROL Agregar servicio]**.

1. En la pantalla [!UICONTROL Agregar servicio], debe hacer lo siguiente:

   1. Seleccione **[!UICONTROL Adobe Experience Platform]** en la lista [!UICONTROL Servicio].

   1. Asegúrese de que **[!UICONTROL Habilitado]** esté seleccionado.

   1. Seleccione su conjunto de datos en la lista [!UICONTROL Conjunto de datos de evento].

      ![Servicio AEP de secuencia de datos](./assets/datastream-aep-service.png)

   1. Deje los demás ajustes y seleccione **[!UICONTROL Guardar]** para guardar la secuencia de datos.

   La secuencia de datos ya está configurada para reenviar los datos recopilados de su sitio web a su conjunto de datos en Adobe Experience Platform.

   Consulte la [Información general sobre secuencias de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=es) para obtener más información sobre cómo configurar una secuencia de datos y cómo gestionar datos confidenciales.

{{upgrade-final-step}}
