---
description: Aprenda a vincular visualizaciones a una fuente de datos de tabla de forma libre.
keywords: Analysis Workspace;Sincronizar visualización con fuente de datos
title: Administración de fuentes de datos de visualización en Analysis Workspace
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: f7d853a3b658328f952b675f838ce314b7c30fb1
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 18%
---
# Administración de fuentes de datos {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Bloquear selección"
>abstract="Habilite esta configuración para bloquear la visualización en las posiciones o en los elementos seleccionados de la fuente de datos."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostrar tabla"
>abstract="Al seleccionar **[!UICONTROL Mostrar tabla]**, se generará un nuevo origen de datos para la visualización actual, independiente del origen de datos original."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostrar tabla"
>abstract="Seleccione **[!UICONTROL Mostrar tabla]** para generar una nueva fuente de datos para la visualización actual, independiente de la fuente de datos original."

Cada visualización en Analysis Workspace se basa en una fuente de datos, normalmente una tabla de forma libre. La sincronización de visualizaciones le permite controlar qué tabla de forma libre o fuente de datos corresponde con una visualización y si la visualización permanece bloqueada a filas específicas de esa tabla.

>[!TIP]
>
>Puede saber qué visualizaciones están relacionadas por el color ![StatusOrange](/help/assets/icons/StatusOrange.svg) situado junto al título de las visualizaciones. La coincidencia de colores significa que las visualizaciones están basadas en la misma fuente de datos.
>

## Configuración de fuente de datos {#configure}

1. En Analysis Workspace, vaya a la visualización cuya fuente de datos o configuración de bloqueo desee establecer.

1. Pase el ratón sobre la visualización y luego seleccione el icono **[!UICONTROL Configuración]** ![Configuración](/help/assets/icons/Setting.svg).

1. Seleccione la ficha **[!UICONTROL Fuente de datos]**.

   ![Pestaña Fuente de datos que muestra la fuente de datos, la visualización vinculada y la configuración de selección de bloqueos.](assets/lock-selection.png)

1. Configure cualquiera de las siguientes opciones:

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Fuente de datos]** | Seleccione la fuente de datos en la que se basa la visualización. |
   | **[!UICONTROL Visualizaciones vinculadas]** | Muestra todas las visualizaciones vinculadas a la fuente de datos (tabla de forma libre). |
   | **[!UICONTROL Mostrar fuente de datos]** | Muestre u oculte la fuente de datos (tabla de forma libre) que corresponde a la visualización. |
   | **[!UICONTROL Bloquear selección]** | Bloquee la visualización en las filas seleccionadas actualmente en el origen de datos y, a continuación, seleccione **[!UICONTROL Posiciones seleccionadas]** o **[!UICONTROL Elementos seleccionados]**. Ver [Bloquear selección](#lock-selection). |

## Bloquear selección {#lock-selection}

Bloquear la selección mantiene una visualización centrada en las filas seleccionadas en su origen de datos, incluso cuando cambia la tabla. Por ejemplo, la tabla cambia al ordenarla o filtrarla, cambiar su intervalo de fechas o aplicar un segmento. Una visualización bloqueada muestra ![LockClosed](/help/assets/icons/LockClosed.svg) junto a su título.

Si los segmentos, dimensiones o métricas de la fuente de datos cambian y los datos bloqueados ya no están visibles, seleccione **[!UICONTROL Mostrar tabla]** para generar una nueva fuente de datos para la visualización, independiente de la fuente de datos original.

Cuando bloquee la selección, elija una de las siguientes opciones:

| Opción | Descripción |
| --- | --- |
| **[!UICONTROL Posiciones seleccionadas]** | Bloquea la visualización en las **posiciones** de las filas seleccionadas en el origen de datos. Estas posiciones se siguen visualizando, incluso si cambian los elementos que contienen. Por ejemplo, seleccione esta opción para mostrar siempre los cinco nombres de campaña principales en la fuente de datos, independientemente de qué campañas sean.<br><br>Si bloquea las filas de desglose y esas filas ya no están en la tabla, la visualización no se mostrará. Para volver a mostrarla, actualice la tabla (por ejemplo, su intervalo de fechas, segmentos o filtros) o actualice la selección de bloqueo. |
| **[!UICONTROL Elementos seleccionados]** | Bloquea la visualización de los **elementos** específicos seleccionados en el origen de datos. Estos elementos se siguen visualizando, incluso si cambia su clasificación en la tabla. Por ejemplo, seleccione esta opción para mostrar siempre los mismos cinco nombres de campaña, independientemente de su clasificación. |
