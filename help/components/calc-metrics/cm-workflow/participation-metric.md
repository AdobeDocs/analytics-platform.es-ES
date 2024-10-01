---
description: Con el Creador de métricas calculadas, cualquier persona puede crear una métrica de participación.
title: Métrica de participación
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Métricas de participación

Las métricas de participación se utilizan para cuantificar la forma en que los valores individuales de una dimensión (como Vistas de página) contribuyen a las sesiones que contienen una métrica específica (como Pedidos) o participan en ellas.

>[!NOTE]
>
>Los administradores pueden crear métricas con modelos de atribución no predeterminados, como Participación, como parte de una [vista de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views). Consulte [Configuración del componente de atribución](../../../data-views/component-settings/attribution.md) para obtener más información.

Los pasos siguientes muestran cómo cualquier usuario con [Crear permiso de métrica calculada](/help/technotes//access-control.md#user-level-access) puede crear una métrica de participación.

1. [Cree una métrica calculada](cm-workflow.md) y, en el [creador de métricas calculadas](cm-build-metrics.md), asigne un nombre a la métrica `Participation` o similar.
1. Arrastre una métrica que contenga un evento de éxito, por ejemplo [!DNL Orders], al área [!UICONTROL **[!UICONTROL Definición]**].
1. Seleccione ![engranaje](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) para la métrica.
1. En la ventana emergente que aparece, seleccione **[!UICONTROL Usar un modelo de atribución no predeterminado]** para definir el [modelo de atribución](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de ese evento en **[!UICONTROL Participación]** y seleccione **[!UICONTROL Sesión]** para la [!UICONTROL ventana retrospectiva]. Seleccione **[!UICONTROL Aplicar]** para confirmar.


   ![Ventana emergente del modelo de atribución de columna que muestra la participación seleccionada como modelo y la sesión seleccionada para la ventana retrospectiva.](assets/participation-setup.png)

   **(Partición|Sesión)** se ha agregado al nombre del componente de métrica.



1. Seleccione [!UICONTROL **Guardar**] para guardar la métrica.
1. Utilice la métrica calculada en el informe. Por ejemplo, use la métrica [!DNL Orders (Session Participation)] calculada en un informe para mostrar qué nivel de cliente contribuyó a sesiones que contenían un pedido o participó en ellas.

   ![Tabla de forma libre que muestra el nivel de cliente y los pedidos.](assets/participation-pages-customer-tier.png)
