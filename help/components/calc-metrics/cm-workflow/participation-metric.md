---
description: Obtenga información sobre cómo crear una métrica de participación.
title: Métrica de participación
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
TQID: https://experienceleague.adobe.com/no7rAZUl25LTEPqwRyC7vY4XcottzPGRq-DCAR5ez54
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 9%

---

# Métricas de participación

Las métricas de participación se utilizan para cuantificar la forma en que los valores individuales de una dimensión (como Vistas de página) contribuyen a las sesiones que contienen una métrica específica (como Pedidos) o participan en ellas.

>[!NOTE]
>
>Los administradores pueden crear métricas con modelos de atribución no predeterminados, como Participación, como parte de una [vista de datos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dataviews/data-views). Consulte [Configuración del componente de atribución](../../../data-views/component-settings/attribution.md) para obtener más información.

Los pasos siguientes muestran cómo cualquier usuario con [Crear permiso de métrica calculada](/help/technotes//access-control.md#user-level-access) puede crear una métrica de participación.

1. [Cree una métrica calculada](cm-workflow.md) y, en el [creador de métricas calculadas](cm-build-metrics.md), asigne un nombre a la métrica `Participation` o similar.
1. Arrastre una métrica que contenga un evento de éxito, por ejemplo [!DNL Orders], al área [!UICONTROL **[!UICONTROL Definición]**].
1. Seleccione ![engranaje](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) para la métrica.
1. En la ventana emergente que aparece, seleccione **[!UICONTROL Usar un modelo de atribución no predeterminado]** para definir el [modelo de atribución](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de ese evento en **[!UICONTROL Participación]** y seleccione **[!UICONTROL Sesión]** para el [!UICONTROL Contenedor]. Seleccione **[!UICONTROL Aplicar]** para confirmar.


   ![Ventana emergente del modelo de atribución de columna que muestra la participación seleccionada como modelo y la sesión seleccionada para la ventana retrospectiva.](assets/participation-setup.png)

   **(Partición|Sesión)** se ha agregado al nombre del componente de métrica.



1. Seleccione [!UICONTROL **Guardar**] para guardar la métrica.
1. Utilice la métrica calculada en el informe. Por ejemplo, use la métrica [!DNL Orders (Session Participation)] calculada en un informe para mostrar qué nivel de cliente contribuyó a sesiones que contenían un pedido o participó en ellas.

   ![Tabla de forma libre que muestra el nivel de cliente y los pedidos.](assets/participation-pages-customer-tier.png)
