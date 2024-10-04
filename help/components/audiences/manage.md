---
title: Obtenga información sobre cómo administrar las audiencias creadas en Customer Journey Analytics
description: Descubra cómo administrar audiencias en Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 20%

---

# Administrar audiencias

Las audiencias se pueden administrar en Customer Journey Analytics mediante **[!UICONTROL Componentes]** > **[!UICONTROL Audiencias]**.

La administración de audiencias creadas anteriormente le permite:

* **Programar o desprogramar** actualizaciones automáticas de audiencias. La caducidad máxima de la programación es de 1 año.
* **Renovar una programación de actualización de audiencia** cuando esté a punto de caducar. Las audiencias que caducan se tratan de manera similar a los informes programados que caducan: el administrador recibe un correo electrónico un mes antes de que la programación caduque.
* Ver el **intervalo de actualización** y la **última vez que se actualizó una audiencia**
* Obtenga información sobre **cuánto tiempo se tardó en producir una audiencia** del Customer Journey Analytics. Y la cantidad de tiempo que tardó la audiencia en aparecer en Real-time Customer Platform con fines de activación.
* Vea si las audiencias de Customer Journey Analytics están **siendo utilizadas activamente por Real-time Customer Platform**. O (idealmente) cualquier aplicación de Experience Platform que consuma las audiencias creadas por Customer Journey Analytics.

Si no cuenta con acceso para [Vista de audiencia](/help/technotes/access-control.md#user-level-access), podrá ver las audiencias. Si cuenta con acceso para [Crear audiencia](/help/technotes/access-control.md#user-level-access), puede editar y eliminar audiencias. La [lista de audiencias](#audiences-list) muestra las audiencias.

## Lista de audiencias

La ➊ de lista Audiencias muestra columnas para:

| Columna | Descripción |
| --- | --- |
| ![SeleccionarCuadro](/help/assets/icons/SelectBox.svg) | Cuando se seleccionan una o más audiencias, aparece una barra de acciones azul en la parte inferior de la interfaz de Audiencias. Consulte [Acciones](#actions) para obtener más información. |
| **[!UICONTROL Título y descripción]** | El título y la descripción que introdujo al crear la audiencia. |
| **[!UICONTROL Vista de datos]** | La vista de datos en la que se creó esta audiencia. |
| **[!UICONTROL Tamaño de la audiencia]** | El número total de personas en esta audiencia. |
| **[!UICONTROL Propietario]** | El propietario de la audiencia: la persona que creó la audiencia. |
| **[!UICONTROL Frecuencia de actualización]** | El intervalo de actualización configurado cuando se creó la audiencia. |
| **[!UICONTROL Etiquetas]** | Las etiquetas aplicadas a esta audiencia. |
| **[!UICONTROL Estado de publicación]** | Puede mostrar ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Listo]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL En curso]** o ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
| **[!UICONTROL Última actualización]** | Marca de tiempo de la última actualización de la audiencia. |
| **[!UICONTROL Última modificación]** | Marca de tiempo de la última modificación o edición de la audiencia. |

Puede usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar qué columnas mostrar. Busque una audiencia con ![Search](/help/assets/icons/Search.svg).

Para editar una audiencia:

1. Seleccione el título de la audiencia. Utilice el cuadro de diálogo **[!UICONTROL Editar proyecto de audiencia]** para actualizar la audiencia. Consulte [Generador de audiencias](publish.md#audience-builder) para obtener más información.

1. Seleccione **[!UICONTROL Volver a publicar]** para volver a publicar la audiencia.


## Acciones

Las siguientes son acciones comunes en el administrador de proyectos programados. Puede seleccionar acciones en el menú contextual:

| Icono | Acción | Descripción |
|:---:|---|---|
| ![Etiquetas](/help/assets/icons/Labels.svg) | **[!UICONTROL Etiqueta]** | Etiquete las audiencias seleccionadas. En el cuadro de diálogo **[!UICONTROL Actualizar etiquetas: *nombre de audiencia *]**, seleccione etiquetas en el menú desplegable o escriba una o más etiquetas nuevas. Seleccione**[!UICONTROL Guardar ]**para guardar. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar las audiencias seleccionadas. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Cambiar el nombre]** | Cambie el nombre de la audiencia seleccionada. Use el cuadro de diálogo **[!UICONTROL Cambiar nombre: *nombre de audiencia *]**para cambiar el nombre de la audiencia y seleccione**[!UICONTROL Guardar ]**para guardar. |

Las siguientes acciones están disponibles en la barra de acciones azul al seleccionar uno o más proyectos programados.

| Icono | Acción | Descripción |
|:---:|---|---|
| ![Cerrar](/help/assets/icons/Close.svg) | **[!UICONTROL *x *seleccionado]** | Seleccione para anular la selección de las audiencias seleccionadas. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar las audiencias seleccionadas. |
| ![ArchivoCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar a CSV]** | Exporte las audiencias seleccionadas a un archivo de nombre `audiences.csv`. |

## Filtro

Puede filtrar la [lista de audiencias](#audiences-list) mediante el ➋ del panel de filtro. Para mostrar u ocultar el panel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

El panel de filtro consta de las siguientes secciones.

### Vista de datos

| Vista de datos | Descripción |
|---|---|
| ![Propietarios](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | La sección **[!UICONTROL Vista de datos]** le permite filtrar las vistas de datos. <ul><li>Usa ![Buscar](/help/assets/icons/Search.svg) para buscar las vistas de datos que desea usar para filtrar.</li><li>Puede seleccionar varias vistas de datos.</li></ul> |

### Propietarios

| Propietario | Descripción |
|---|---|
| ![Propietarios](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | La sección **[!UICONTROL Propietario]** le permite filtrar por propietarios. <ul><li>Usa ![Buscar](/help/assets/icons/Search.svg) para buscar los propietarios que desea usar para filtrar.</li><li>Puede seleccionar más de un propietario. </li></ul> |

## Frecuencia de actualización

| Frecuencia de actualización | Descripción |
|---|---|
| ![Frecuencia de actualización](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | La sección **[!UICONTROL Frecuencia de actualización]** le permite filtrar la frecuencia de actualización. <ul><li>Usa ![Buscar](/help/assets/icons/Search.svg) para buscar la frecuencia de actualización que desea usar para filtrar.</li><li>Solo las frecuencias de actualización definidas para las audiencias <br/> de la [lista de audiencias](#audiences-list) se muestran como opciones disponibles.</li></ul> |


### Etiquetas

| Etiquetas | Descripción |
|---|---|
| ![Etiquetas](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | La sección **[!UICONTROL Etiquetas]** le permite filtrar las etiquetas. <ul><li>Usa ![Buscar](/help/assets/icons/Search.svg) para buscar las etiquetas que desea usar para filtrar. |
