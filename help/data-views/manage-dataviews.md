---
title: Administrar vistas de datos
description: Obtenga información sobre cómo administrar las vistas de datos.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c5cf15ab-3eb1-4e6b-93a3-3d89694ca0ea
source-git-commit: c7cf7250f30e2f6023aa7690391aea149ba12eff
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 10%

---

# Administrar vistas de datos


Una vez que haya [creado o editado una o más vistas de datos](/help/data-views/create-dataview.md), puede administrarlas en **[!UICONTROL Vistas de datos]**.

Seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Vistas de datos]** en la barra de menú principal de Customer Journey Analytics.

La interfaz **[!UICONTROL Vistas de datos]** muestra una tabla con todas las vistas de datos disponibles.

![Interfaz de vistas de datos](/help/data-views/assets/data-views.png)

En la tabla están disponibles las siguientes columnas e iconos:

| Columna o icono | Descripción |
| --- | --- |
| **[!UICONTROL Nombre]** | El nombre de la vista de datos. |
| ![Información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Para ver información sobre la vista de datos, seleccione ![InfoOutline](/help/assets/icons/InfoOutline.svg) junto al nombre de la vista de datos.<br/>Una ventana emergente muestra detalles sobre la vista de datos. |
| ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Seleccione ![Más](/help/assets/icons/More.svg) para abrir un menú contextual. Puede seleccionar:<br/>![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para [editar](#edit-data-views) una vista de datos.<br/>![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar]** a [copiar una vista de datos](#copy-data-views).<br/>![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** para [eliminar](#delete-data-views) una vista de datos.<br/>![ArchivoCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar a CSV]** para [exportar los detalles de la vista de datos a un archivo CSV](#export-data-views-to-csv).<br/>![ProyectoAgregar](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Crear proyecto]** para [crear un nuevo proyecto de Workspace](#create-project-from-data-views) para la vista de datos.<br/>![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Habilite para Data Insights Agent]** para habilitar una vista de datos para Data Insights Agent.<br/>![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Deshabilite para Data Insights Agent]** para deshabilitar una vista de datos para Data Insights Agent. |
| **[!UICONTROL Conexión]** | Nombre de la conexión asociada con la vista de datos. |
| **[!UICONTROL Zona protegida]** | Nombre de la zona protegida asociada a la vista de datos. |
| **[!UICONTROL Propietario]** | Propietario de la vista de datos. |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | Indica si [Data Insights Agent](/help/data-analysis-ai.md) está **[!UICONTROL habilitado]** o **[!UICONTROL deshabilitado]** para la vista de datos. <br/>Seleccione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para mostrar una ventana emergente con **[!UICONTROL Estado de Data Insights Agent]** en las vistas de datos. <br/>![Uso de Data Insights Agent](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL Integraciones]** | Enumerar integraciones con otras soluciones. Por ejemplo: Análisis de audiencia de Adobe, Content Analytics, Brand Concierge, Journey Optimizer, GenStudio y Análisis de uso. |
| **[!UICONTROL Usar en CJA]** | Indique si la vista de datos se utiliza en Customer Journey Analytics. Este valor solo está **[!UICONTROL desactivado]** para las vistas de datos que se generan automáticamente como parte de la integración de Adobe Journey Optimizer. |
| **[!UICONTROL Fecha de creación]** | La marca de tiempo cuando se creó la vista de datos. |
| **[!UICONTROL Última modificación]** | La marca de tiempo cuando se modificó la vista de datos por última vez. |

Para configurar qué columnas mostrar en la tabla, seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). En el cuadro de diálogo **[!UICONTROL Personalizar tabla]**, seleccione las columnas que desea mostrar. Luego selecciona **[!UICONTROL Aplicar]**.


## Vistas de datos de búsqueda

Puede buscar rápidamente una vista de datos usando el cuadro ![Buscar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

## Filtrado de vistas de datos

Para aplicar un filtro a la lista de vistas de datos, seleccione el icono ![Filtro](/help/assets/icons/Filter.svg) y, a continuación, elija una de las siguientes opciones de filtro:

| Opción de filtro | Descripción |
|---------|----------|
| **[!UICONTROL Conexiones]** | Solo se muestran las vistas de datos asociadas con las conexiones seleccionadas. |
| **[!UICONTROL Propietario]** | Solo se muestran las vistas de datos propiedad de las personas seleccionadas. |
| **[!UICONTROL Zona protegida]** | Solo se muestran las vistas de datos disponibles en los entornos limitados que seleccione. |
| **[!UICONTROL Integraciones]** | Solo se muestran las vistas de datos con integraciones seleccionadas. |
| **[!UICONTROL Usar en CJA]** | Seleccione **[!UICONTROL Activado]** para mostrar solamente las vistas de datos que se han habilitado para usar con Customer Journey Analytics. Seleccione **[!UICONTROL Desactivado]** para mostrar solamente las vistas de datos que aún no están habilitadas para su uso con Customer Journey Analytics. |


Seleccione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar el panel de filtros.

## Crea una vista de datos

Para [crear una nueva vista de datos](/help/data-views/create-dataview.md), seleccione **[!UICONTROL Crear nueva vista de datos]**.


## Edición de vistas de datos

Si desea [editar una vista de datos](/help/data-views/create-dataview.md):

1. Seleccione ![Más](/help/assets/icons/More.svg) junto al nombre de la vista de datos.
1. Seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** en el menú contextual.

Como alternativa, puede:

1. Seleccione la fila de vista de datos.
1. Seleccionar ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** en la barra de acciones azul.


## Copia de vistas de datos

Si desea copiar una vista de datos:

1. Seleccione ![Más](/help/assets/icons/More.svg) junto al nombre de la vista de datos.
1. Seleccione ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar]** del menú contextual.

Como alternativa, puede:

1. Seleccione una o varias filas de vista de datos.
1. Seleccione ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar]** de la barra de acciones azul.

La vista de datos se copia y se agrega a la lista con **[!UICONTROL (Copiar)]** anexado al nombre.


## Eliminación de vistas de datos

Si desea eliminar una vista de datos:

1. Seleccione ![Más](/help/assets/icons/More.svg) junto al nombre de la vista de datos.
1. Seleccione ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** del menú contextual.

Como alternativa, puede:

1. Seleccione una o varias filas de vista de datos.
1. Seleccione ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** en la barra de acciones azul.

Al eliminar una o más vistas de datos, el panel **[!UICONTROL Eliminar vista de datos]** indica qué proyectos se ven afectados.

![Eliminar vista de datos](/help/data-views/assets/delete-data-view.png)


* En ➊ **[!UICONTROL Confirmación]**, se muestran las implicaciones de la eliminación de las vistas de datos.
* Seleccione **[!UICONTROL Eliminar]** para eliminar las vistas de datos de forma permanente. Seleccione **[!UICONTROL Cancelar]** para cancelar.


## Exportación de vistas de datos a CSV

Puede exportar una vista de datos a un archivo CSV.

1. Seleccione ![Más](/help/assets/icons/More.svg) junto al nombre de la vista de datos.
1. Seleccione ![ArchivoCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar a CSV]** desde el menú contextual.

Como alternativa, puede:

1. Seleccione una o varias filas de vista de datos.
1. Seleccione ![ArchivoCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar a CSV]** desde la barra de acciones azul.

Los detalles de las vistas de datos seleccionadas se exportan a un archivo CSV denominado `Data views List (x).csv` en la carpeta Descargas del explorador.


## Crear proyecto a partir de vistas de datos

Puede crear un proyecto de Workspace directamente desde la interfaz de vistas de datos.

1. Seleccione ![Más](/help/assets/icons/More.svg) junto al nombre de la vista de datos.
1. Seleccione ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Crear proyecto]** en el menú contextual.

Como alternativa, puede:

1. Seleccione una fila de la vista de datos.
1. Seleccione ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Crear proyecto]** de la barra de acciones azul.


## Habilitar o deshabilitar las vistas de datos para Data Insights Agent

Puede habilitar o deshabilitar una vista de datos para [Data Insights Agent](/help/data-analysis-ai.md).

1. Seleccione ![Más](/help/assets/icons/More.svg) junto al nombre de la vista de datos.
1. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Habilitar para Data Insights Agent]** o ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Deshabilitar para Data Insights Agent]** del menú contextual.

Como alternativa, puede:

1. Seleccione una o varias filas de vista de datos que estén deshabilitadas o habilitadas para Data Insights Agent.
1. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Habilitar para Data Insights Agent]** o ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Deshabilitar para Data Insights Agent]** de la barra de acciones azul.
