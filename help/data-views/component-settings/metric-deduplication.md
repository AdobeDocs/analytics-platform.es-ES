---
title: Configuración del componente de anulación de deduplicación de métricas
description: Cuenta solo la primera aparición de una métrica en los informes.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:57.728Z'
TQID: 'https://experienceleague.adobe.com/bCgBjD9r0cQ3O73fEip-EQHItMHQSX-2AECydDxR9Ms'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 79%

---

# Configuración del componente de anulación de deduplicación de métricas {#metric-deduplication-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_deduplication"
>title="Anulación de duplicación métrica"
>abstract="Configure una métrica para contar solo los valores que aparezcan de forma no repetitiva."

<!-- markdownlint-enable MD034 -->


La anulación de deduplicación de métricas le permite configurar una métrica para que solo cuente los valores de forma no repetitiva.

![Anulación de duplicación métrica](../assets/metric-deduplication.png)

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Anulación de duplicación métrica] | Casilla de verificación que permite habilitar la anulación de deduplicación de métricas. Deshabilitado de forma predeterminada. |
| [!UICONTROL Ámbito de anulación de duplicación] | Permite determinar hasta dónde llega la comprobación única.<br/>**[!UICONTROL Cuenta global &#x200B;]**: solo se cuenta la primera ocurrencia de métrica en la ventana de informes.<br/>**[!UICONTROL Cuenta]**: solo se cuenta la primera ocurrencia de métrica en la ventana de informes.<br/>**[!UICONTROL Oportunidad &#x200B;]**: solo se cuenta la primera ocurrencia de métrica en la ventana de informes.<br/>**[!UICONTROL Grupo de compra]**: solo se cuenta la primera ocurrencia de métrica en la ventana de informes.<br/>**[!UICONTROL Persona &#x200B;]**: solo se cuenta la primera ocurrencia de métrica en la ventana de informes.<br>**[!UICONTROL Sesión]**: solo se cuenta la primera ocurrencia de métrica de la sesión.<br> |
| [!UICONTROL ID de anulación de duplicación] | En lugar de aplicar la anulación de deduplicación en la propia métrica, le permite aplicar la anulación de duplicación de métricas en función de una dimensión. Útil para dimensiones como ID de compra para aplicar la anulación de deduplicación. |
| [!UICONTROL Valor que mantener] | <ul><li>**Mantener primera instancia**: utilícelo en situaciones en las que la instancia inicial de la métrica sea válida. Lo más común probablemente sería una confirmación de compra. Incluso si alguien vuelve a cargar la página sin querer y obtiene otra instancia de confirmación de compra, el evento inicial es el válido.</li><li>**Mantener última instancia**: utilícelo en situaciones en las que recopilar la última instancia tenga más sentido. Ejemplo: Alguien actualiza su perfil en línea. Solo queremos contar una de estas actualizaciones por sesión. Sin embargo, pueden actualizar su perfil varias veces durante la sesión. Si conservamos la primera instancia, podría haber actividades que no se vincularan al evento. En este caso, tiene más sentido mantener la última instancia.</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>La anulación de duplicación en el ámbito de una _persona_ se evalúa mediante meses completos en tiempo UTC. Es posible que una ventana de creación de informes mensual parcial no muestre todas las instancias primera o última, si algunas ocurrieron dentro del mes completo, pero fuera de las fechas de creación de informes.
