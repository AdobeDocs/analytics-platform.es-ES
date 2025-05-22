---
title: Crear un esquema para Customer Journey Analytics
description: Más información sobre la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---

# Crear una secuencia de datos para utilizarla con Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Crear una secuencia de datos en Adobe Experience Platform"
>abstract="Un conjunto de datos es una ubicación intermedia que pasa los datos a todos los servicios configurados. Cree esta ubicación en Adobe Experience Platform.<br><br>La creación inicial de una secuencia de datos en la interfaz de Platform solo lleva unos minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Una secuencia de datos representa la configuración del lado del servidor al implementar los SDK web y móvil de Adobe Experience Platform. Al recopilar datos con los SDK de Adobe Experience Platform, los datos se envían a Adobe Experience Platform Edge Network. Es la secuencia de datos la que determina a qué servicios se reenvían los datos.

En la configuración, desea configurar la secuencia de datos para enviar los datos recopilados a su conjunto de datos en Adobe Experience Platform.

>[!NOTE]
>
>Los siguientes pasos solo son necesarios para implementaciones de Adobe Analytics que utilizan AppMeasurement o la extensión de Analytics (etiquetas).
>
>Si la implementación de Adobe Analytics utiliza el SDK web o la extensión del SDK web, el conjunto de datos ya existe en el entorno de Adobe Analytics.

Para configurar la secuencia de datos, debe hacer lo siguiente:

1. En Adobe Experience Platform, seleccione **[!UICONTROL Secuencias de datos]** en [!UICONTROL RECOPILACIÓN DE DATOS] en el carril izquierdo.

1. Seleccione **[!UICONTROL Nueva secuencia de datos]**.

1. Asigne un nombre y describa su secuencia de datos. Seleccione el esquema en la lista [!UICONTROL Esquema de eventos].

   ![Nuevo conjunto de datos](assets/new-datastream.png)

1. Seleccione **[!UICONTROL Guardar]**.

{{upgrade-final-step}}
