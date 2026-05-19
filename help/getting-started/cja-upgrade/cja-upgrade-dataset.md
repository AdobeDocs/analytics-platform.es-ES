---
title: Crear un esquema para Customer Journey Analytics
description: Más información sobre la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
autotag-review: '2026-05-19T08:12:18.647Z'
TQID: 'https://experienceleague.adobe.com/ti9UiQzAa9wBCCH-44dmUxTzojuh5ZHu9YJ9HNC8OHI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 100%

---

# Creación de un conjunto de datos para utilizarlo con Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Creación de un conjunto de datos en Adobe Experience Platform"
>abstract="Un conjunto de datos es una ubicación en la que residen los datos recopilados. Cree esta ubicación en Adobe Experience Platform.<br><br>Crear un conjunto de datos con un esquema en mente solo lleva unos minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un conjunto de datos es la construcción que almacena y administra los datos que se recopilan en Adobe Experience Platform.

Para crear un conjunto de datos:

1. En la interfaz de usuario de Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Conjuntos de datos]** en [!UICONTROL ADMINISTRACIÓN DE DATOS].

1. Seleccione **[!UICONTROL Crear conjunto de datos]**.

   ![Crear conjunto de datos](assets/create-dataset.png)

1. Seleccione **[!UICONTROL Crear conjunto de datos a partir de esquema]**.

   ![Crear conjunto de datos a partir de esquema](assets/create-dataset-from-schema.png)

1. Seleccione el esquema creado anteriormente y, después, **[!UICONTROL Siguiente]**.

1. Asigne un nombre al conjunto de datos y (opcionalmente) proporcione una descripción.

   ![Nombre del conjunto de datos](assets/name-your-datatest.png)

1. Seleccione **[!UICONTROL Finalizar]**.

1. Seleccione el conmutador **[!UICONTROL Perfil]**.

   Se le pedirá que habilite el conjunto de datos para el perfil. Una vez habilitado, el conjunto de datos enriquece los perfiles de clientes en tiempo real con sus datos ingeridos.

   >[!IMPORTANT]
   >
   >    Solo puede habilitar un conjunto de datos para un perfil cuando el esquema, al que se adhiere el conjunto de datos, también esté habilitado para el perfil.

   ![Habilitar esquema para perfil](assets/aepwebsdk-dataset-profile.png)

   Consulte [Guía de la interfaz de usuario de conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es) para obtener más información sobre cómo ver, previsualizar, crear o eliminar un conjunto de datos. También puede aprender a habilitar un conjunto de datos para el perfil del cliente en tiempo real.

{{upgrade-final-step}}
