---
description: Gracias al Creador de métricas calculadas, todo el mundo puede crear una métrica de participación.
title: Métrica de participación
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 5fbffb01c08b5f8069b2670742f7ae3836ad8357
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 42%

---

# Crear una métrica de &quot;participación&quot;

La siguiente información explica cómo crear una métrica que muestre qué páginas contribuyeron a las visitas que contenían un pedido (o participaron en ellas).

Este tipo de información podría ser útil para cualquier propietario de contenido.

>[!NOTE]
>
>Puede habilitar métricas de participación en las Herramientas de administración, pero solo para los eventos personalizados 1-100.

1. Comience a crear una métrica, tal como se describe en [Crear métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. En el Creador de métricas calculadas, asigne a la métrica el nombre &quot;Participación&quot; o algo similar
1. Arrastre el evento de éxito “Pedidos” al lienzo Definición.
1. Cambie el [modelo de atribución](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de ese evento a **[!UICONTROL Participación]** en el icono de engranajes de **[!UICONTROL Configuración]**. Seleccione **[!UICONTROL Visita]** retrospectiva. La definición debería tener un aspecto parecido al siguiente:

   ![](assets/participation.png)

1. Seleccionar [!UICONTROL **Guardar**] para guardar la métrica.
1. Utilice la métrica calculada en un informe **[!UICONTROL Páginas]**.

   ![](assets/participation-pages.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización.
