---
description: Obtenga información sobre cómo sincronizar una tabla de forma libre o una fuente de datos con la visualización correspondiente.
keywords: Analysis Workspace;Sincronizar visualización con fuente de datos
title: Administrar fuentes de datos
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 89%

---

# Administración de fuentes de datos {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Bloquear selección"
>abstract="Habilite esta configuración para bloquear la visualización en las posiciones o en los elementos seleccionados de la fuente de datos."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostrar tabla"
>abstract="Si se selecciona **[!UICONTROL Mostrar tabla]**, se generará un nuevo origen de datos para la visualización actual, independiente del origen de datos original."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostrar tabla"
>abstract="Seleccione **[!UICONTROL Mostrar tabla]** para generar una nueva fuente de datos para la visualización actual, independiente de la fuente de datos original."

La sincronización de visualizaciones le permite controlar qué tabla de forma libre o fuente de datos corresponde con una visualización.

>[!TIP]
>
>Puede saber qué visualizaciones están relacionadas por el color ![StatusOrange](/help/assets/icons/StatusOrange.svg) situado junto al título de las visualizaciones. La coincidencia de colores significa que las visualizaciones están basadas en la misma fuente de datos.
>

Puede mostrar u ocultar la fuente de datos. También puede bloquear la selección en las posiciones seleccionadas o a los elementos seleccionados. Esta configuración determina cómo cambia (o no) la visualización al introducir nuevos datos.

![Opción Fuente de datos que muestra las opciones que se describen en la siguiente sección.](assets/lock-selection.png)


| Opción | Descripción |
|--- |--- |
| **[!UICONTROL Fuente de datos]** | En el menú desplegable, seleccione la fuente de datos en la que se basa la visualización. |
| **[!UICONTROL Visualizaciones vinculadas]** | Enumera todas las visualizaciones vinculadas. Se aplica a la fuente de datos (tabla de forma libre). |
| **[!UICONTROL Mostrar fuente de datos]** | Permite mostrar u ocultar la fuente de datos (tabla de forma libre) que corresponde a la visualización. |
| **[!UICONTROL Bloquear selección]** | Seleccione esta opción para bloquear la visualización ![LockClosed](/help/assets/icons/LockClosed.svg) en los datos seleccionados actualmente en la tabla de datos correspondiente. Una vez habilitada, elija entre:  <ul><li>**Posiciones seleccionadas**: la visualización está bloqueada en las **posiciones** seleccionadas en la tabla de datos correspondiente. Estas posiciones se siguen visualizando, incluso si cambian los elementos específicos de estas posiciones (por ejemplo, debido a la ordenación o al filtrado). Por ejemplo, seleccione esta opción si desea mostrar los cinco nombres de campaña principales enumerados en la fuente de datos en esta visualización en todo momento. No importa qué nombres de campaña aparezcan.</li> <li>**Elementos seleccionados**: la visualización está bloqueada en **elementos** específicos seleccionados actualmente en la tabla de datos correspondiente. Estos elementos se seguirán visualizando, incluso si cambian su clasificación entre los elementos de la tabla. Por ejemplo, seleccione esta opción si desea mostrar los mismos cinco nombres de campaña específicos enumerados en la fuente de datos en esta visualización en todo momento. No importa cómo se clasifiquen esos nombres de campaña.</li></ul>Si la visualización está bloqueada en datos que ya no son visibles en la tabla de datos conectada, puede generar una nueva tabla. Seleccione **[!UICONTROL Mostrar tabla]**, se generará un nuevo origen de datos para la visualización actual, independiente del origen de datos original. |
