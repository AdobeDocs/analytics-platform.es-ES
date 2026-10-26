---
description: Utilice la visualización de temas de tendencias para explorar estos temas en las conversaciones.
title: Temas de tendencia
feature: Visualizations
role: User
hide: true
source-git-commit: 85311bf19368560ef54a3361edf2e7c13590929c
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 8%
---
# Temas de tendencia {#trending-topics}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Temas de tendencia"
>abstract="Cree una visualización que muestre un desglose jerárquico detallado habilitado de los temas de tendencia con ocurrencias y porcentajes para ayudarle a identificar temas significativos en las conversaciones."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Temas de tendencia"
>abstract="Analice los temas de tendencia en función de la métrica de clasificación seleccionada. Seleccione los temas para profundizar hasta cinco niveles. Busque temas específicos y compare temas con otros intervalos de fechas."

La visualización ![Fuente](/help/assets/icons/Feed.svg) **[!UICONTROL Temas de tendencia]** le permite explorar y analizar los temas de tendencia como parte de Perspectivas de la conversación.

Puede buscar temas específicos y comparar el número y el porcentaje de cada tema en cada nivel con otros rangos de datos.

## Crear y configurar {#trendimg-topics-create-and-configure}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel"
>title="Uso de modelos de atribución no predeterminados"
>abstract="Habilite un modelo de atribución no predeterminado para esta métrica."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel_disabled"
>title="Uso de modelos de atribución no predeterminados"
>abstract="Los modelos de atribución no predeterminados no están disponibles para esta métrica."

Para crear y configurar una visualización de **[!UICONTROL temas de tendencia]**:

1. Agregar una visualización de ![Fuente](/help/assets/icons/Feed.svg) **[!UICONTROL Temas de tendencia]**. Consulte [Añadir una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. En la configuración de visualización **[!UICONTROL Temas de tendencia]**:

   1. Seleccione una **[!UICONTROL métrica de clasificación]**. Por ejemplo: **[!UICONTROL conversaciones]**.
   1. De forma opcional, si desea usar un modelo [attribution](/help/analysis-workspace/attribution/models.md) no predeterminado en la métrica, seleccione **[!UICONTROL Usar modelo de atribución no predeterminado]** y seleccione **[!UICONTROL Modelo]**, **[!UICONTROL Contenedor]** y **[!UICONTROL Ventana retrospectiva]**.
1. Seleccione **[!UICONTROL Build]** para generar la visualización. Seleccione **[!UICONTROL Restablecer]** para restablecer los valores predeterminados de configuración.

Para reconfigurar la visualización de los temas de tendencia, seleccione ![Editar](/help/assets/icons/Edit.svg) junto a **[!UICONTROL Métrica de clasificación: _métrica de clasificación_ | Niveles de subtema: _x_]**.

## Utiliza

Para utilizar la visualización:

![Usar la visualización de temas de tendencia](assets/trending-topics.png)

* Pase el ratón sobre un tema para ver una ventana emergente con más detalles. ➊

* Para ver los temas secundarios de tendencia de un tema en un nivel inferior, seleccione un tema en un nivel específico. Si no hay temas disponibles en un subnivel, verá ![DataRemove](/help/assets/icons/DataRemove.svg) **[!UICONTROL No se encontraron subtemas para _topic > subtopic > ...]**.

* Use ![Buscar](/help/assets/icons/Search.svg) **[!UICONTROL _Buscar temas_]** para buscar temas rápidamente. ➋

* Para comparar temas con otro intervalo de fechas, seleccione un intervalo de fechas de **[!UICONTROL Comparar con]**. ➌

  Para utilizar un intervalo de fechas personalizado:

  * Seleccione **[!UICONTROL Intervalo de fechas personalizado]** en el menú desplegable y en el cuadro de diálogo **[!UICONTROL Nuevo intervalo de fechas]** defina y guarde un intervalo de fechas personalizado.
  * Seleccione ese intervalo de fechas personalizado.

* Para mostrar un gráfico de líneas para la selección actual de temas, suelte una visualización [Line](/help/analysis-workspace/visualizations/line.md) en la visualización **[!UICONTROL Trending topics]**. La visualización **[!UICONTROL Line]** se vincula automáticamente a la visualización **[!UICONTROL Trending topics]** y muestra una línea para el tema seleccionado.

  ![Visualización de línea de tema de tendencia](assets/trending-topics-line-viz.png)

## Configuración

Están disponibles las siguientes [configuraciones de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) específicas.

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Mostrar valor real]** | Muestra el valor real de un tema. |
| **[!UICONTROL Porcentaje de visualización]** | Muestra el porcentaje de un tema. |
