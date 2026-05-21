---
description: Aprenda a crear una métrica calculada simple.
title: Crear Una Métrica Calculada Simple
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
TQID: https://experienceleague.adobe.com/hbiAmMoSUMm2Ggf5Vkxm484SzYETtgRRZAuaWvlS884
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 17%

---

# Crear una métrica calculada simple

La siguiente información explica cómo crear una métrica *Vistas de página por visitas* simple.

1. Comience a crear una métrica, como se describe en [Crear métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Asigne a la métrica el nombre `Page Views per Session` o algo similar.
1. Asigne a la métrica una **[!UICONTROL descripción]** fácil de usar para mostrar para qué se utiliza la métrica.
1. Seleccione el **[!UICONTROL formato]** correcto. Para este ejemplo, elija **[!UICONTROL Decimal]**.
1. Decida cuántos lugares decimales desea que muestre su informe.
1. En el menú desplegable **[!UICONTROL Mostrar tendencia ascendente como]**, seleccione ▲ **[!UICONTROL Bueno (verde)]**.
1. Agregue una **[!UICONTROL Etiqueta]** para organizar sus métricas.
1. Para esta métrica calculada, primero arrastre **[!UICONTROL Vistas de página]** desde los componentes de **[!UICONTROL Métricas]** a la sección **[!UICONTROL Definición]** del lienzo.
1. A continuación, arrastre **[!UICONTROL Sesiones]** desde los componentes de **[!UICONTROL Métricas]** y suelte la métrica debajo de **[!UICONTROL Vistas de página]** (espere hasta que aparezca la línea azul antes de soltar la métrica).
1. Seleccione el operador dividir ![Dividir](/help/assets/icons/Divide.svg). (Dividir es el operador predeterminado).
1. Puede ver una **[!UICONTROL vista previa]** de la métrica mientras la está generando.
1. **[!UICONTROL Compatibilidad del producto]** muestra si la métrica calculada es compatible en cualquier lugar de Customer Journey Analytics (excluida la experimentación).

   ![Métrica calculada simple](assets/simple-calculated-metric.png)
1. Seleccione **[!UICONTROL Guardar]**.

   Observe que la fórmula de **[!UICONTROL Resumen]** se actualiza cada vez que realice cambios en la definición de la métrica.

1. (Opcional) Para compartir, aprobar, (volver a) etiquetar, cambiar el nombre o eliminar una métrica, puede ir a [Administrador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md).

