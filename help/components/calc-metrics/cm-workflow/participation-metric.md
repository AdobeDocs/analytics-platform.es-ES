---
description: Gracias al Creador de métricas calculadas, todo el mundo puede crear una métrica de participación.
title: Métrica de participación
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---

# Generar una métrica de participación

Este artículo explica cómo crear una métrica de participación. Una métrica de participación muestra cómo los valores individuales de una dimensión (como Vistas de página, Canal de marketing) contribuyen a las sesiones que contienen una métrica específica (por ejemplo, Pedidos) o participan en ellas.

Este tipo de información podría ser útil para cualquier propietario de contenido.

>[!NOTE]
>
>Los administradores también pueden crear métricas con otros modelos de atribución, como Participación, como parte de una [vista de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=es). Consulte [Configuración del componente de atribución](../../../data-views/component-settings/attribution.md) para obtener más información.<br/>El ejemplo siguiente muestra cómo cualquier usuario con acceso al creador de métricas calculadas en Workspace puede crear una métrica de participación.


1. Comience a crear una métrica, tal como se describe en [Generar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. En el Creador de métricas calculadas, asigne un nombre a la métrica `Participation` o similar.
1. Arrastre una métrica que contenga un evento de éxito, por ejemplo [!DNL Orders], al lienzo [!UICONTROL Definición].
1. Seleccione ![engranaje](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) para la métrica.
1. En la ventana emergente que aparece, seleccione **[!UICONTROL Usar un modelo de atribución no predeterminado]** para definir el [modelo de atribución](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de ese evento en **[!UICONTROL Participación]** y seleccione **[!UICONTROL Sesión]** para la [!UICONTROL ventana retrospectiva]. Seleccione **[!UICONTROL Aplicar]** para confirmar.

   En el cuadro Definición, la métrica seleccionada se actualiza adjuntando **(Partición|Sesión)** a su nombre.

   ![Ventana emergente del modelo de atribución de columna que muestra la participación seleccionada como modelo y la sesión seleccionada para la ventana retrospectiva.](assets/participation-setup.png)



1. Seleccione [!UICONTROL **Guardar**] para guardar la métrica.
1. Utilice la métrica calculada en el informe. Por ejemplo, use la métrica [!DNL Orders (Session Participation)] calculada (como se define en el paso 5) en un informe para mostrar qué nivel de cliente contribuyó a sesiones que contenían un pedido o participó en ellas.

   ![Tabla de forma libre que muestra el nivel de cliente y los pedidos.](assets/participation-pages-customer-tier.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización, tal como se describe en [Compartir métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
