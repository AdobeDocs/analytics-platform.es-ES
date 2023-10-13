---
description: Gracias al Creador de métricas calculadas, todo el mundo puede crear una métrica de participación.
title: Métrica de participación
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 6a9cae93011447fff0f74ca4ae15178e0a1f36aa
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# Crear una métrica de participación

Este artículo explica cómo crear una métrica de participación. Una métrica de participación muestra cómo los valores individuales de una dimensión (como Vistas de página, Canal de marketing) contribuyen a las sesiones que contienen una métrica específica (por ejemplo, Pedidos) o participan en ellas.

Este tipo de información podría ser útil para cualquier propietario de contenido.

>[!NOTE]
>
>Los administradores también pueden crear métricas con otros modelos de atribución, como Participación, como parte de una [vista de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=es). El ejemplo siguiente muestra cómo los puede crear cualquier usuario con acceso al creador de métricas calculadas en Workspace.


1. Comience a crear una métrica, tal como se describe en [Crear métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. En el Creador de métricas calculadas, asigne a la métrica el nombre &quot;Participación&quot; o algo similar.
1. Arrastre una métrica que contenga un evento de éxito, por ejemplo &quot;Pedidos&quot;, al lienzo Definición.
1. Seleccionar ![Engranaje](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) para la métrica.
1. En la ventana emergente que aparece, seleccione **[!UICONTROL Uso de un modelo de atribución no predeterminado]** para definir el [modelo de atribución](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de ese evento a **[!UICONTROL Participación]** y seleccione **[!UICONTROL Session]** para el [!UICONTROL Ventana retroactiva]. Seleccionar **[!UICONTROL Aplicar]** para confirmar.

   En el cuadro Definición, la métrica seleccionada se actualiza añadiendo  **(Participación|Sesión)** a su nombre.

   ![](assets/participation-setup.png)



1. Seleccionar [!UICONTROL **Guardar**] para guardar la métrica.
1. Utilice la métrica calculada en el informe. Por ejemplo, utilice el valor calculado [!DNL Orders (Session Participation)] métrica (tal como se define en el paso 5) en un informe para mostrar qué nivel de cliente contribuyó a sesiones que contenían un pedido o participó en ellas.

   ![](assets/participation-pages-customer-tier.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización, tal como se describe en [Compartir métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
