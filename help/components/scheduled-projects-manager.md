---
description: Obtenga información sobre cómo administrar proyectos programados.
title: Proyectos programados
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 41%

---

# Proyectos programados

Los proyectos programados de Analysis Workspace se pueden administrar en Customer Journey Analytics mediante **[!UICONTROL Componentes]** > **[!UICONTROL Proyectos programados]**.

En **[!UICONTROL Proyectos programados]**, puede editar y eliminar la programación recurrente de proyectos.  La [lista de proyectos programados](#scheduled-project-list) muestra los elementos que ha creado un usuario en particular. Si la cuenta del usuario está desactivada en la aplicación, se detendrán todos los envíos programados.

![Interfaz de proyectos programados](assets/scheduled-projects.png)

## Lista de proyectos programados

La lista Proyectos programados ➊ muestra columnas para:

| Columna | Descripción |
| --- | --- |
| ![SeleccionarCuadro](/help/assets/icons/SelectBox.svg) | Cuando se seleccionan uno o más proyectos programados, aparece una barra de acciones azul en la parte inferior de la interfaz Proyectos programados. Consulte las [acciones](#actions) para obtener más información.  |
| ![Star](/help/assets/icons/Star.svg) | Seleccione para favorecer a ![Star](/help/assets/icons/Star.svg) o para anular el favor de ![StarOutline](/help/assets/icons/StarOutline.svg) en un proyecto programado. |
| **[!UICONTROL ID de programación]** | ID que se utiliza principalmente con fines de depuración. |
| **[!UICONTROL Nombre]** | Nombre de este proyecto.<br/>Seleccione ![EsquemaDeInformación](/help/assets/icons/InfoOutline.svg) para ver más detalles del proyecto programado.<br/>Seleccione ![Más](/help/assets/icons/More.svg) para abrir un menú contextual. Desde este menú puede:<ul><li>![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** un proyecto programado.</li><li>![Etiquetas](/help/assets/icons/Labels.svg) **[!UICONTROL Etiquetar]** un proyecto programado.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Apruebe]** un proyecto programado.</li><li>![ArchivoCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar CSV]**: exporte un proyecto programado a un archivo CSV.</li></ul> |
| **[!UICONTROL Propietario]** | La persona que creó el proyecto y es propietaria de él. |
| **[!UICONTROL Etiquetas]** | (opcional) El etiquetado es una buena forma de organizar los proyectos. Todos los usuarios pueden crear etiquetas y aplicar una o más a un proyecto. Sin embargo, solo verá las etiquetas de los proyectos que sean suyos o que se hayan compartido con usted. |
| **[!UICONTROL Entregado a]** | Destinatarios de este proyecto programado. |
| **[!UICONTROL Fecha de caducidad]** | Puede establecer la fecha de caducidad en un máximo de un año, independientemente de la frecuencia de programación. |
| **[!UICONTROL Frecuencia]** | La frecuencia con la que desea que este proyecto programado se envíe a uno o varios destinatarios. |
| **[!UICONTROL Hora de ejecución]** | A qué hora del día se envía este proyecto programado. |
| **[!UICONTROL Cantidad de consultas]** | Número de consultas de este proyecto. |
| **[!UICONTROL El intervalo de fecha más largo]** | Intervalo de fecha más largo definido para el proyecto programado. Este valor puede ser relevante para investigar los problemas de rendimiento. Consulte [Administrador de actividades de creación de informes](/help/reporting-activity-manager/reporting-activity-overview.md) para obtener más información. |
| **[!UICONTROL Cantidad de consultas]** | Número de consultas ejecutadas para el proyecto programado. Este valor puede ser relevante para investigar los problemas de rendimiento. Consulte [Administrador de actividades de creación de informes](/help/reporting-activity-manager/reporting-activity-overview.md) para obtener más información. |


Puede usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar qué columnas mostrar.

Busque un proyecto programado con ![Buscar](/help/assets/icons/Search.svg). También puede ver si se aplica algún filtro desde el panel Filtros. Para quitar un filtro, seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para un filtro. Para quitar todos los filtros, seleccione **[!UICONTROL Borrar todo]**.

Para editar un proyecto programado, seleccione su título. Utilice el cuadro de diálogo **[!UICONTROL Editar proyecto programado]** para actualizar los detalles de la programación. Ver [Enviar archivos a otros](../analysis-workspace/export/t-schedule-report.md) para obtener más detalles.

![Editar proyecto programado](assets/edit-scheduled-project.png)

Seleccione **[!UICONTROL Actualizar]** para actualizar la programación.




## Acciones

Las siguientes son acciones comunes en el administrador de proyectos programados. Puede seleccionar acciones en el menú contextual o en la barra de acciones azul al seleccionar uno o varios proyectos programados.

| Icono | Acción | Descripción |
|:---:|---|---|
| ![Cerrar](/help/assets/icons/Close.svg) | **[!UICONTROL *x *seleccionada]** | Seleccione para anular la selección de los proyectos programados seleccionados. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar los proyectos programados seleccionados para el proyecto; los proyectos no se eliminan. |
| ![Etiquetas](/help/assets/icons/Labels.svg) | **[!UICONTROL Etiqueta]** | Etiquete los proyectos programados seleccionados. En **[!UICONTROL Etiquetar proyectos programados]**, seleccione las etiquetas y seleccione **[!UICONTROL Guardar]** para guardar. |
| ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Aprobar]** | Apruebe los proyectos programados seleccionados. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar a CSV]** | Exportar los proyectos programados seleccionados a un archivo denominado `Export Scheduled Projects List.csv`. |


## Filtrar

Puede filtrar los proyectos programados [Lista de proyectos programados](#scheduled-project-list) mediante el panel de filtro ➌. Para mostrar u ocultar el panel de filtro, utilice ![Filtro](/help/assets/icons/Filter.svg).

El panel de filtro consta de las siguientes secciones.

### Etiquetas

| Etiquetas | Descripción |
|---|---|
| ![Etiquetas](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | La sección **[!UICONTROL Etiquetas]** le permite filtrar las etiquetas. <ul><li>Utilice ![Búsqueda](/help/assets/icons/Search.svg) **[!UICONTROL Búsqueda de etiquetas]** para buscar las etiquetas que desea utilizar para filtrar.</li><li>Puede seleccionar más de una etiqueta. Las etiquetas disponibles dependen de las selecciones realizadas en otras secciones del panel de filtro.</li><li>Los números indican lo siguiente:<ul><li>7︎⃣: número de proyectos programados asociados con la etiqueta específica.</li></ul></li></ul> |


### Propietarios

| Propietario | Descripción |
|---|---|
| ![Propietarios](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | La sección **[!UICONTROL Propietario]** le permite filtrar por los propietarios. <ul><li>Utilice ![Búsqueda](/help/assets/icons/Search.svg) *Búsqueda de propietarios* para buscar los propietarios que desea usar para filtrar.</li><li>Puede seleccionar más de un propietario. Los propietarios disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>4︎⃣: número de proyectos programados asociados con el propietario específico.</li></ul></li></ul> |


### Otros filtros

| Otros filtros | Descripción |
|---|---|
| ![Otros filtros](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | La sección **[!UICONTROL Otros filtros]** le permite filtrar otros filtros predefinidos.<ul><li>Puede seleccionar una o varias de las siguientes opciones:<ul><li> **[!UICONTROL Caducado]**: filtro en proyectos programados caducados.</li><li>**[!UICONTROL Error]**: filtro en proyectos programados para los que la programación ha fallado.</li></ul>Lo que puede seleccionar depende de la función y los permisos.</li><li>Puede seleccionar más de un otro filtro. Los otros filtros disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>4︎⃣: número de proyectos programados asociados con el otro filtro específico.</li></ul></li></ul> |
