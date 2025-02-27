---
title: Monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics
description: Obtenga información sobre cómo monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validación de datos en el conjunto de datos"
>abstract="Ahora que ha configurado la implementación de Web SDK, puede utilizar el administrador de actividades de conjuntos de datos para ver los lotes ingeridos y los que han dado error. Si ve lotes ingeridos principalmente, este paso ha finalizado. Si ve principalmente lotes con errores o sin lotes, compruebe la implementación de Web SDK para asegurarse de que envía correctamente los datos a Adobe.<br><br>Si todo se hizo correctamente y sin problemas, este paso se puede realizar en menos de un día. Si hay varios problemas de recopilación de datos, la resolución de estos puede tardar mucho más."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Después de configurar la implementación de Web SDK, debe comprobar los estados de los lotes individuales para comprobar que se están introduciendo datos en el conjunto de datos.

1. En la interfaz de usuario de Experience Platform, seleccione **[!UICONTROL Supervisión]** en el panel de navegación izquierdo.

   Se muestra el panel Monitorización. Este panel le permite ver los estados de los datos de entrada procedentes de la ingesta por lotes o de la transmisión.

   <!-- insert screenshot -->

1. Seleccione **[!UICONTROL Lote de extremo a extremo]** para ver una lista de lotes.

   Si no se muestran lotes, compruebe la implementación de Web SDK para asegurarse de que envía correctamente los datos a Adobe.

   <!-- insert screenshot -->

1. Seleccione el ID de lote para un conjunto de datos determinado y, a continuación, valide que **[!UICONTROL Éxito]** se muestra en el campo **[!UICONTROL Estado]**.

   Si se muestra **[!UICONTROL Error]** en el campo **[!UICONTROL Estado]**, compruebe la implementación de Web SDK para asegurarse de que envía correctamente los datos a Adobe.

   Repita este paso para verificar el estado de cada lote.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).

