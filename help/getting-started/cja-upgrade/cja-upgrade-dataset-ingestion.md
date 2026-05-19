---
title: Monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics
description: Obtenga información sobre cómo monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
autotag-review: '2026-05-19T08:10:42.746Z'
TQID: 'https://experienceleague.adobe.com/tAPQiUUPilyH50PlqwefoZjw14QDN9ER1D6EKsMAR9w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 100%

---

# Monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validación de datos en el conjunto de datos"
>abstract="Ahora que ha configurado la implementación, puede utilizar el administrador de actividades del conjuntos de datos para ver los lotes ingeridos y los que han dado error. Si ve lotes ingeridos principalmente, este paso ha finalizado. Si ve principalmente lotes con errores o ningún lote, compruebe la implementación para asegurarse de que está enviando correctamente los datos a Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Después de configurar la implementación del SDK web o la API, debe comprobar los estados de los lotes individuales para comprobar que se están introduciendo datos en el conjunto de datos.

1. En la interfaz de usuario de Experience Platform, seleccione **[!UICONTROL Monitorización]** en el panel de navegación izquierdo.

   Se muestra el panel de control Monitorización. Este panel de control le permite ver los estados de los datos de entrada procedentes de la ingesta por lotes o de la ingesta de streaming.

   <!-- insert screenshot -->

1. Seleccione **[!UICONTROL Lote de extremo a extremo]** para ver una lista de lotes.

   Si no se muestran lotes, compruebe la implementación para asegurarse de que envía correctamente los datos a Adobe.

   <!-- insert screenshot -->

1. Seleccione el ID de lote para un conjunto de datos determinado y, a continuación, valide que **[!UICONTROL Éxito]** se muestra en el campo **[!UICONTROL Estado]**.

   Si se muestra **[!UICONTROL Error]** en el campo **[!UICONTROL Estado]**, compruebe la implementación para asegurarse de que envía correctamente los datos a Adobe.

   Repita este paso para verificar el estado de cada lote.

{{upgrade-final-step}}

