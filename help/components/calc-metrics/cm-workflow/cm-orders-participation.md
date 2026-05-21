---
description: Explica cómo crear una métrica que muestre qué canales de marketing ayudan a controlar las órdenes.
title: Crear Una Métrica Calculada Más Compleja
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 3%

---

# Crear una métrica calculada más compleja

Este artículo explica un ejemplo más complejo de una métrica calculada. Estas métricas calculadas muestran qué canales de marketing ayudan a dirigir las solicitudes. Este tipo de métrica calculada se puede adaptar a cualquier dimensión o evento de éxito.

1. Comience a crear una métrica calculada, tal como se describe en [Crear métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

1. En el Creador de métricas calculadas, asigne un nombre a la métrica `Assisted Online Orders` o similar.

1. Seleccione la métrica **[!UICONTROL Pedidos en línea]** de los componentes **[!UICONTROL Métricas]** y arrastre la métrica al área **[!UICONTROL Definición]**.

   1. Seleccione ![Setting](/help/assets/icons/Setting.svg) para la métrica.
   1. Haga clic en **[!UICONTROL Utilizar modelo de atribución no predeterminado]**.
   1. Ajuste el modelo de atribución en el **[!UICONTROL modelo de atribución de columna]**.
      1. Seleccione **[!UICONTROL Personalizado]** para **[!UICONTROL Modelo]**. Establece **[!UICONTROL Starter]** en `0`, **[!UICONTROL Player]** en `100` y **[!UICONTROL Closer]** en `0`.
      1. Seleccionar **[!UICONTROL Visitante]** para **[!UICONTROL Contenedor]**.
      1. Seleccione **[!UICONTROL 30 días]** para **[!UICONTROL ventana retrospectiva]**.

      1. Seleccione **[!UICONTROL Aplicar]**.

      ![Modelo de atribución de columna](assets/complex-calculated-metric.png)

1. Seleccione **[!UICONTROL Guardar]** para guardar la métrica calculada.

Para utilizar la métrica calculada:

1. En Analysis Workspace, cree una tabla de forma libre con la dimensión **[!UICONTROL Canal de marketing]**, **[!UICONTROL Pedidos en línea]** y la nueva métrica **[!UICONTROL Pedidos en línea asistidos]**.

   ![Pedidos en línea asistidos por canal de mercadotecnia](assets/marketing-channel-assists.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización, tal como se describe en [Compartir métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md).

Esta es una manera fácil de saber qué canales de marketing ayudaron a tramitar las solicitudes. Como alternativa, en una tabla de forma libre, puede seleccionar cualquier métrica y, en el menú contextual, ajustar el modelo de atribución directamente desde la tabla.
