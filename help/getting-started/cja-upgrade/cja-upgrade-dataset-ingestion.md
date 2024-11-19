---
title: Monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics
description: Obtenga información sobre cómo monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a5425eccff643cd45fd630172b0113e646b2a9cc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Monitorizar la ingesta de conjuntos de datos al actualizar a Customer Journey Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Después de configurar la implementación del SDK web, debe comprobar los estados de los lotes individuales para comprobar que se están introduciendo datos en el conjunto de datos.

1. En la interfaz de usuario del Experience Platform, seleccione **[!UICONTROL Supervisión]** en el panel de navegación izquierdo.

   Se muestra el panel Monitorización. Este panel le permite ver los estados de los datos de entrada procedentes de la ingesta por lotes o de la transmisión.

   <!-- insert screenshot -->

1. Seleccione **[!UICONTROL Lote de extremo a extremo]** para ver una lista de lotes.

   Si no se muestran lotes, compruebe la implementación del SDK web para asegurarse de que envía correctamente los datos al Adobe.

   <!-- insert screenshot -->

1. Seleccione el ID de lote para un conjunto de datos determinado y, a continuación, valide que **[!UICONTROL Éxito]** se muestra en el campo **[!UICONTROL Estado]**.

   Si se muestra **[!UICONTROL Error]** en el campo **[!UICONTROL Estado]**, compruebe la implementación del SDK web para asegurarse de que envía correctamente los datos al Adobe.

   Repita este paso para verificar el estado de cada lote.




