---
description: La sincronización de visualizaciones le permite controlar qué tabla de datos o fuente de datos corresponde con una visualización.
keywords: Analysis Workspace;Sincronizar visualización con fuente de datos
title: Administración de fuentes de datos
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 27%

---

# Administración de fuentes de datos {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Bloquear selección"
>abstract="Active esta configuración para bloquear la visualización en las posiciones o en los elementos seleccionados de la fuente de datos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostrar tabla"
>abstract="Si se selecciona **[!UICONTROL Mostrar tabla]**, se generará un nuevo origen de datos para la visualización actual, independiente del origen de datos original."

<!-- markdownlint-enable MD034 -->



La sincronización de visualizaciones le permite controlar qué tabla de datos o fuente de datos corresponde con una visualización.

>[!TIP]
>
>Puede saber qué visualizaciones están relacionadas por el color de ![StatusOrange](/help/assets/icons/StatusOrange.svg) junto al título de las visualizaciones. La coincidencia de colores significa que las visualizaciones están basadas en la misma fuente de datos.
>

Puede mostrar u ocultar la fuente de datos. También puede bloquear la selección a las posiciones seleccionadas o a los elementos seleccionados. Esta configuración determina cómo cambia (o no) la visualización al introducir nuevos datos.

![Cuadro de diálogo de opciones de Data Source que muestra las opciones descritas en la siguiente sección.](assets/lock-selection.png)


| Opción | Descripción |
|--- |--- |
| **[!UICONTROL Origen de datos]** | En el menú desplegable, seleccione la fuente de datos en la que se basa la visualización. |
| **[!UICONTROL Visualizaciones vinculadas]** | Enumera todas las visualizaciones vinculadas. Se aplica a la fuente de datos (tabla de forma libre). |
| **[!UICONTROL Mostrar origen de datos]** | Permite mostrar u ocultar la fuente de datos (tabla de forma libre) que corresponde a la visualización. |
| **[!UICONTROL Bloquear selección]** | Seleccione esta opción para bloquear la visualización ![LockClosed](/help/assets/icons/LockClosed.svg) con los datos seleccionados actualmente en la tabla de datos correspondiente. Una vez activado, seleccione entre:  <ul><li>**Posiciones seleccionadas**: la visualización está bloqueada en las **posiciones** seleccionadas en la tabla de datos correspondiente. Estas posiciones se siguen visualizando, incluso si cambian los elementos específicos de estas posiciones (por ejemplo, debido a la ordenación o al filtrado). Por ejemplo, seleccione esta opción si desea mostrar los cinco nombres de campaña principales enumerados en la fuente de datos en esta visualización en todo momento. No importa qué nombres de campaña aparezcan.</li> <li>**Elementos seleccionados**: la visualización está bloqueada en **elementos** específicos seleccionados actualmente en la tabla de datos correspondiente. Estos elementos se seguirán visualizando, incluso si cambian su clasificación entre los elementos de la tabla. Por ejemplo, seleccione esta opción si desea mostrar los mismos cinco nombres de campaña específicos enumerados en la fuente de datos en esta visualización en todo momento. No importa cómo se clasifiquen esos nombres de campaña.</li></ul>Si la visualización está bloqueada a datos que ya no son visibles en la tabla de datos conectada, puede generar una nueva tabla. Seleccione **[!UICONTROL Mostrar tabla]** para generar un nuevo origen de datos para su visualización actual, independiente del origen de datos original. |
