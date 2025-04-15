---
title: Obtenga información sobre cómo administrar audiencias creadas en Customer Journey Analytics
description: Descubra cómo administrar audiencias en Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 65dcbf63d9e155cb7e04bf9a550151a37b8457e6
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 18%

---

# Administrar audiencias

Audiences se puede administrar en Customer Journey Analytics mediante **[!UICONTROL Componentes]** > **[!UICONTROL Audiences]**.

## Comprender las tareas de gestión de audiencia

La administración de audiencias creadas anteriormente permite:

* **Programar o desprogramar** actualizaciones automáticas de audiencias. La caducidad máxima de la programación es de 1 año.
* **Renovar una programación de actualización de audiencia** cuando esté a punto de caducar. Las audiencias que caducan se tratan de manera similar a los informes programados que caducan: el administrador recibe un correo electrónico un mes antes de que la programación caduque.
* Ver el intervalo **de** actualización y la **última vez que se actualizó un audiencia**
* Obtener insight por la **cantidad de tiempo que se tardó en producir una audiencia** de Customer Journey Analytics. Y la cantidad de tiempo que tardó la audiencia en aparecer en Real-time Customer Platform con fines de activación.
* Compruebe si las audiencias de Customer Journey Analytics están **siendo utilizadas activamente por Real-time Customer Platform**. O (idealmente) cualquier aplicación de Experience Platform que consuma las audiencias creadas por Customer Journey Analytics.

Si no cuenta con acceso para [Vista de audiencia](/help/technotes/access-control.md#user-level-access), podrá ver las audiencias. Si cuenta con acceso para [Crear audiencia](/help/technotes/access-control.md#user-level-access), puede editar y eliminar audiencias.

## Ver audiencias en la lista Audiencias

La ➊ Lista de audiencias muestra las audiencias existentes.

![Administrador de audiencias](assets/audiences-manager.png)

Para ver la lista Audiencia:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Audiencias]**.

1. (Opcional) Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar qué columnas mostrar.

1. (Opcional) Busque una audiencia con ![Search](/help/assets/icons/Search.svg).

   Las columnas siguientes están disponibles con información sobre cada audiencia:

   | Columna | Descripción |
   | --- | --- |
   | ![SeleccionarCuadro](/help/assets/icons/SelectBox.svg) | Cuando se seleccionan una o más audiencias, aparece una barra de acciones azul en la parte inferior de la interfaz de Audiencias. Consulte [Acciones](#actions) para obtener más información. |
   | **[!UICONTROL Título y descripción]** | Título y descripción que escribió al crear el audiencia. |
   | **[!UICONTROL Vista de datos]** | La vista de datos en la que se creó esta audiencia. |
   | **[!UICONTROL Tamaño de la audiencia]** | El número total de personas en esta audiencia. |
   | **[!UICONTROL Propietario]** | El propietario de la audiencia: la persona que creó la audiencia. |
   | **[!UICONTROL Frecuencia de actualización]** | El intervalo de actualización configurado cuando se creó la audiencia. |
   | **[!UICONTROL Etiquetas]** | Las etiquetas aplicadas a esta audiencia. |
   | **[!UICONTROL Estado de publicación]** | Puede mostrar ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Listo]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL En curso]** o ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
   | **[!UICONTROL Última actualización]** | Marca de tiempo de la última actualización de la audiencia. |
   | **[!UICONTROL Última modificación]** | Marca de hora de cuándo se editó o modificó el audiencia por última vez. |

## Editar audiencias

Puede editar la configuración de una audiencia en cualquier momento. Cuando edita una audiencia (ya sea una audiencia única o recurrente), se requiere volver a publicar.

Para editar una audiencia:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Audiences]**.

   Se muestra la página Audiencias.

1. Seleccione el título de la audiencia que desea editar.

   Se muestra el cuadro de diálogo **[!UICONTROL Editar audiencia]**.

1. Puede actualizar cualquiera de los campos disponibles para la audiencia. Para obtener información sobre los campos que puede actualizar, consulte [Generador de audiencias](/help/components/audiences/publish.md#audience-builder) en el artículo [Crear y publicar audiencias](/help/components/audiences/publish.md).

1. Seleccione **[!UICONTROL Volver a publicar]**.

## Acciones

Las siguientes son acciones comunes en el administrador de proyectos programados. Puede seleccionar acciones en el menú contextual:

| Icono | Acción | Descripción |
|:---:|---|---|
| ![Etiquetas](/help/assets/icons/Labels.svg) | **[!UICONTROL Etiqueta]** | Etiquete las audiencias seleccionadas. En el cuadro de **[!UICONTROL diálogo Actualizar etiquetas: *audiencia nombre *]**, seleccione etiquetas en el menú desplegable o escriba una o más etiquetas nuevas. Seleccione**[!UICONTROL Guardar ]**para guardar. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar las audiencias seleccionadas. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Cambiar el nombre]** | Cambiar nombre el audiencia seleccionado. Utilice el **[!UICONTROL cuadro de diálogo Cambiar nombre: *audiencia nombre *]**para cambiar el nombre del audiencia y seleccionar**[!UICONTROL Guardar ]**desea guardar. |

Las siguientes acciones están disponibles en la barra de acciones azul al seleccionar uno o más proyectos programados.

| Icono | Acción | Descripción |
|:---:|---|---|
| ![Cerrar](/help/assets/icons/Close.svg) | **[!UICONTROL *x *seleccionado]** | Seleccione para anular la selección de las audiencias seleccionadas. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar las audiencias seleccionadas. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar a CSV]** | Exporte las audiencias seleccionadas a un archivo denominado `audiences.csv`. |

## Filtrado de la lista de audiencias

Puede filtrar la [lista de audiencias](#audiences-list) mediante el ➋ del panel de filtro. Para mostrar u ocultar el panel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

![Administrador de audiencias](assets/audiences-manager.png)

El panel de filtros consta de las siguientes secciones.

### Vista de datos

| Vista de datos | Descripción |
|---|---|
| ![Propietarios](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | La sección **[!UICONTROL Vista de datos]** le permite filtrar las vistas de datos. <ul><li>Usa ![Buscar](/help/assets/icons/Search.svg) para buscar las vistas de datos que desea usar para filtrar.</li><li>Puede seleccionar varias vistas de datos.</li></ul> |

### Propietarios

| Propietario | Descripción |
|---|---|
| ![Propietarios](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | La **[!UICONTROL sección Propietario]** le permite filtrar por propietarios. <ul><li>![Utilice Search](/help/assets/icons/Search.svg) para búsqueda a los propietarios que desea usar para filtrar.</li><li>Se puede seleccionar más de una propietario. </li></ul> |

## Frecuencia de actualización

| Frecuencia de actualización | Descripción |
|---|---|
| ![Frecuencia de actualización](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | La **[!UICONTROL sección Frecuencia de Actualizar]** le permite filtrar por actualización Frecuencia. <ul><li>![Utilice Search](/help/assets/icons/Search.svg) para búsqueda para actualizar los Frecuencia desea usar para filtrar.</li><li>Solo las frecuencias de actualización definidas<br/> para las audiencias en el [lista Audiences](#audiences-list) se muestran como opciones disponibles.</li></ul> |


### Etiquetas

| Etiquetas | Descripción |
|---|---|
| ![Etiquetas](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | La sección **[!UICONTROL Etiquetas]** le permite filtrar las etiquetas. <ul><li>Usa ![Buscar](/help/assets/icons/Search.svg) para buscar las etiquetas que desea usar para filtrar. |
