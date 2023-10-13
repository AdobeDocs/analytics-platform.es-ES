---
description: Gracias al Creador de métricas calculadas, todo el mundo puede crear una métrica de participación.
title: Métrica de participación
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d95d324350a2f8aa77032e7cac1c924d161d47ce
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 17%

---

# Generar una métrica de “participación”

En este artículo se explica cómo crear una métrica que muestre cómo los valores individuales de una dimensión seleccionada (como Vistas de página, Canal de marketing o Versión de la aplicación) contribuyeron a sesiones que contenían un pedido o participaron en ellas.

Este tipo de información podría ser útil para cualquier propietario de contenido.

>[!NOTE]
>
>Los administradores también pueden crear métricas con otros modelos de atribución, como Participación, como parte de una [vista de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=es). El ejemplo siguiente muestra cómo los puede crear cualquier usuario con acceso al creador de métricas calculadas en Workspace.

1. Comience a crear una métrica, tal como se describe en [Crear métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. En el Creador de métricas calculadas, asigne a la métrica el nombre &quot;Participación&quot; o algo similar
1. Arrastre el evento de éxito “Pedidos” al lienzo Definición.
1. Seleccionar ![Engranaje](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) para el [!DNL Orders] métricas.
1. En la ventana emergente que aparece, seleccione **[!UICONTROL Uso de un modelo de atribución no predeterminado]** para definir el [modelo de atribución](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de ese evento a **[!UICONTROL Participación]** y seleccione **[!UICONTROL Session]** para el [!UICONTROL Ventana retroactiva]. Seleccionar **[!UICONTROL Aplicar]** para confirmar.

   En el cuadro Definición, ![Evento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Pedidos** se ha actualizado a ![Evento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Pedidos (participación|sesión)**.

   ![](assets/participation-setup.png)



1. Seleccionar [!UICONTROL **Guardar**] para guardar la métrica.
1. Utilice la métrica calculada en el informe. Debajo de la métrica calculada se utiliza un informe para mostrar qué nivel de cliente contribuyó a sesiones que contenían un pedido o participó en ellas.

   ![](assets/participation-pages-customer-tier.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización, tal como se describe en [Compartir métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
