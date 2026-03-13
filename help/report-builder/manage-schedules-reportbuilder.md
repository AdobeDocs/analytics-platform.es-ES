---
title: Administrar Libros Programados En Report Builder
description: Obtenga información sobre cómo administrar libros programados en Report Builder.
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 0a0427d9-223e-410b-a8ef-8601390d88aa
source-git-commit: 9d5c895672e422a82ef68b0af6cd85359c9b11ea
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 5%

---

# Administrar libros de trabajo programados

Puede programar un libro para compartirlo por correo electrónico o exportarlo a un destino de nube, tal como se describe en los siguientes artículos:

* [Schedule workbooks by sharing through email](/help/report-builder/schedule-reportbuilder.md)

* [Schedule workbooks for export to cloud destinations](/help/report-builder/report-builder-export.md)

The following sections describe how to manage workbooks after they are scheduled:

## View and manage scheduled workbooks

You can view and manage all scheduled workbooks in the **[!UICONTROL Workbooks]** tab.

1. Select **[!UICONTROL Schedule]** in the Report Builder hub

1. Select the **[!UICONTROL Workbooks]** tab. You see a list of all scheduled workbooks. (También puede seleccionar la pestaña **[!UICONTROL Heredado]** para ver una lista de libros heredados que deben migrarse al nuevo Report Builder).

   ![Libro programado](assets/scheduled-workbooks.png){zoomable="yes"}

1. Realice una de las siguientes acciones:

   * Pase el ratón sobre el icono para ver el estado de un libro programado.

   * In the search field ![Search](/help/assets/icons/Search.svg), search for specific scheduled workbooks.

   * Select the column icon ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to define which columns to show.

   * Select the filter icon ![Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), then select [!UICONTROL **Show all**] to show all scheduled workbooks for a given org.

1. Select one or more workbooks.

   ![Schedule workbooks selected](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   Las opciones disponibles son las siguientes:

   | Opción | Descripción |
   |---|---|
   | ![Editar](/help/assets/icons/Edit.svg) | Editar la programación de un libro seleccionado. |
   | ![Historial](/help/assets/icons/History.svg) | Show the history of selected workbooks. |
   | ![Pause](/help/assets/icons/Pause.svg) | Pause the schedule of selected workbooks. |
   | ![Play](/help/assets/icons/Play.svg) | Resume the schedule of selected workbooks. |
   | ![Descargar](/help/assets/icons/Download.svg) | Descargue el libro seleccionado en un nuevo libro. |
   | ![Eliminar](/help/assets/icons/Delete.svg) | Eliminar la programación de los libros seleccionados. |


## Historial y estado de los libros programados

Puede ver el historial y el estado de los libros programados en la ficha **[!UICONTROL Historial]**.

1. Select **[!UICONTROL Schedule]** in the Report Builder hub.

1. Select the **[!UICONTROL History]** tab. You see a list of all scheduled workbooks.

   ![Scheduled history](assets/scheduled-workbooks-history.png){zoomable="yes"}

   Use ![Search](/help/assets/icons/Search.svg) to search for specific workbooks in the list.
Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to define which columns to show.

   The **[!UICONTROL History]** tab allows you to review the status of each scheduled task. A separate row documents the status change for each scheduled task.

   * Un ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg) indica que el libro se envió correctamente.
   * Un ![AlertRed](/help/assets/icons/AlertRed.svg) indica que se produjo un error.

También puede seleccionar ![Historial](/help/assets/icons/History.svg) para uno o más libros seleccionados en la ficha **[!UICONTROL Libros]**. Esta acción muestra la ficha **[!UICONTROL Historial]** con una lista filtrada por su selección. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar un filtro.
