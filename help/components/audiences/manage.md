---
title: Descubra cómo administrar públicos en Customer Journey Analytics
description: Descubra cómo administrar audiencias en Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 76%

---

# Administrar públicos

Los públicos se pueden administrar en Customer Journey Analytics mediante **[!UICONTROL Componentes]** > **[!UICONTROL Públicos]**.

## Comprender las tareas de gestión de audiencia

La administración de públicos creados anteriormente le permite:

* **Programar o desprogramar** actualizaciones automáticas de audiencias. La caducidad máxima de la programación es de 1 año.
* **Renovar una programación de actualización de audiencia** cuando esté a punto de caducar. Las audiencias que caducan se tratan de manera similar a los informes programados que caducan: el administrador recibe un correo electrónico un mes antes de que la programación caduque.
* Consultar el **intervalo de actualización** y la **última vez que se actualizó un público**
* Obtener información sobre **cuánto tiempo se tardó en producir un público** de Customer Journey Analytics. Y la cantidad de tiempo que tardó el público en aparecer en Real-Time Customer Platform con fines de activación.
* Compruebe si **Real-Time Customer Platform** está usando los públicos de Customer Journey Analytics activamente. O, idealmente, cualquier aplicación de Experience Platform que consuma los públicos creados por Customer Journey Analytics.

Si cuenta con acceso a [Vista de públicos](/help/technotes/access-control.md#user-level-access), podrá ver los públicos. Si cuenta con acceso para [Crear audiencia](/help/technotes/access-control.md#user-level-access), puede editar y eliminar audiencias.

## Ver audiencias en la lista Audiencias

La ➊ Lista de audiencias muestra las audiencias existentes.

![Audience Manager](assets/audiences-manager.png)

Para ver la lista Audiencia:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Audiencias]**.

1. (Opcional) Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar qué columnas mostrar.

1. (Opcional) Busque una audiencia con ![Search](/help/assets/icons/Search.svg).

   Las siguientes columnas están disponibles con información sobre cada audiencia:

   | Columna | Descripción |
   | --- | --- |
   | ![SeleccionarCuadro](/help/assets/icons/SelectBox.svg) | Cuando se seleccionan uno o varios públicos, aparece una barra de acciones azul en la parte inferior de la interfaz de Públicos. Consulte la sección [Acciones](#actions) para obtener más información. |
   | **[!UICONTROL Título y descripción]** | El título y la descripción que introdujo al crear el público. |
   | **[!UICONTROL Vista de datos]** | La vista de datos en la que se creó esta audiencia. |
   | **[!UICONTROL Tamaño de la audiencia]** | El número total de personas en esta audiencia. |
   | **[!UICONTROL Propietario]** | El propietario del público: la persona que lo creó. |
   | **[!UICONTROL Frecuencia de actualización]** | El intervalo de actualización configurado al crear el público. |
   | **[!UICONTROL Etiquetas]** | Las etiquetas aplicadas a esta audiencia. |
   | **[!UICONTROL Estado de publicación]** | Puede aparecer ![EstadoVerde](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Listo]**, ![EstadoGris](/help/assets/icons/StatusGray.svg) **[!UICONTROL En curso]** o ![EstadoRojo](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
   | **[!UICONTROL Última actualización]** | La marca de tiempo de la última vez que se actualizó el público. |
   | **[!UICONTROL Última modificación]** | La marca de tiempo de la última vez que se editó o modificó el público. |

## Editar audiencias

Puede editar la configuración de una audiencia en cualquier momento. Cuando edita una audiencia (ya sea una audiencia única o recurrente), se requiere volver a publicar.

Para crear un público:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Audiencias]**.

   Se muestra la página Audiencias.

1. Seleccione el título de la audiencia que desea editar.

   Se muestra el cuadro de diálogo **[!UICONTROL Editar audiencia]**.

1. Puede actualizar cualquiera de los campos disponibles para la audiencia. Para obtener información sobre los campos que puede actualizar, consulte [Generador de audiencias](/help/components/audiences/publish.md#audience-builder) en el artículo [Crear y publicar audiencias](/help/components/audiences/publish.md).

1. Seleccione **[!UICONTROL Volver a publicar]**.

## Acciones

Las siguientes son acciones comunes en el administrador de proyectos programados. Puede seleccionar acciones en el menú contextual:

| Icono | Acción | Descripción |
|:---:|---|---|
| ![Etiquetas](/help/assets/icons/Labels.svg) | **[!UICONTROL Etiqueta]** | Etiquetar las audiencias seleccionadas. En el cuadro de diálogo **[!UICONTROL Actualizar etiquetas: *nombre de audiencia *]**, seleccione etiquetas en el menú desplegable o escriba una o más etiquetas nuevas. Seleccione&#x200B;**[!UICONTROL Guardar &#x200B;]**&#x200B;para guardar. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar las audiencias seleccionadas. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Cambiar el nombre]** | Cambiar el nombre de la audiencia seleccionada. Use el cuadro de diálogo **[!UICONTROL Cambiar nombre: *nombre de audiencia *]**&#x200B;para cambiar el nombre de la audiencia y seleccione&#x200B;**[!UICONTROL Guardar &#x200B;]**&#x200B;para guardar. |

Las siguientes acciones están disponibles en la barra de acciones azul al seleccionar uno o más proyectos programados.

| Icono | Acción | Descripción |
|:---:|---|---|
| ![Cerrar](/help/assets/icons/Close.svg) | **[!UICONTROL *x *seleccionada]** | Seleccionar para anular la selección de las audiencias seleccionadas. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar las audiencias seleccionadas. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar a CSV]** | Exportar las audiencias seleccionadas a un archivo lkanado `audiences.csv`. |

## Filtrado de la lista de audiencias

Puede filtrar la [lista de audiencias](#audiences-list) mediante el ➋ del panel de filtro. Para mostrar u ocultar el panel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

![Audience Manager](assets/audiences-manager.png)

El panel de filtro consta de las siguientes secciones.

### Vista de datos

| Vista de datos | Descripción |
|---|---|
| ![Propietarios](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | La sección **[!UICONTROL Vista de datos]** le permite filtrar las vistas de datos. <ul><li>Utilice la opción ![Buscar](/help/assets/icons/Search.svg) para buscar vistas de datos que desea usar para filtrar.</li><li>Puede seleccionar más de una vista de datos.</li></ul> |

### Propietarios

| Propietario | Descripción |
|---|---|
| ![Propietarios](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | La sección **[!UICONTROL Propietario]** le permite filtrar por propietarios. <ul><li>Utilice la opción ![Buscar](/help/assets/icons/Search.svg) para buscar los propietarios que desea usar para filtrar.</li><li>Puede seleccionar más de un propietario. </li></ul> |

## Frecuencia de actualización

| Frecuencia de actualización | Descripción |
|---|---|
| ![Frecuencia de actualización](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | La sección **[!UICONTROL Frecuencia de actualización]** le permite filtrar la frecuencia de actualización. <ul><li>Utilice la opción ![Búsqueda](/help/assets/icons/Search.svg) para buscar la frecuencia de actualización que desea usar para filtrar.</li><li>Solo se muestran como opciones disponibles las frecuencias de actualización definidas para los públicos<br/> de la [Lista de públicos](#audiences-list).</li></ul> |


### Etiquetas

| Etiquetas | Descripción |
|---|---|
| ![Etiquetas](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | La sección **[!UICONTROL Etiquetas]** le permite filtrar las etiquetas. <ul><li>Utilice la opción ![Búsqueda](/help/assets/icons/Search.svg) para buscar etiquetas que desea usar para filtrar. |
