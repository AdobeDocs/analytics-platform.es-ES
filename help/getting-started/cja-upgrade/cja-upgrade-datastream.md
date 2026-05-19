---
title: Crear un esquema para Customer Journey Analytics
description: Más información sobre la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
autotag-review: '2026-05-19T08:13:03.106Z'
TQID: 'https://experienceleague.adobe.com/vzavQGq0OyhXTpSkqe3nnXQEW0Nax9RXt4SwTRwa4UU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 221
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
