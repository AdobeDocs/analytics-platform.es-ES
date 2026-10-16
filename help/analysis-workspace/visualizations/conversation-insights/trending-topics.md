---
description: Utilice la visualización de temas de tendencias para explorar estos temas en las conversaciones.
title: Temas de tendencia
feature: Visualizations
role: User
hide: true
source-git-commit: 137dba69c8827f3b67d5656760d7715437c58b73
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%
---

# Temas de tendencia

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Temas de tendencia"
>abstract="Cree una visualización que muestre un desglose jerárquico detallado habilitado de los temas de tendencia con ocurrencias y porcentajes para ayudarle a identificar temas importantes en las conversaciones."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Temas de tendencia"
>abstract="Analice los temas de tendencia en función de la métrica de clasificación seleccionada. Seleccione los temas para profundizar hasta cinco niveles. Busque temas específicos y compare temas con otros intervalos de fechas."

La visualización ![Fuente](/help/assets/icons/Feed.svg) **[!UICONTROL Temas de tendencia]** le permite explorar y analizar los temas de tendencia como parte de Perspectivas de la conversación.

Puede buscar temas específicos y comparar el número y el porcentaje de cada tema en cada nivel con otros rangos de datos.

## Crear y configurar

Para crear y configurar una visualización de temas de tendencia:

1. Agregar una visualización de ![Fuente](/help/assets/icons/Feed.svg) **[!UICONTROL Temas de tendencia]**. Consulte [Añadir una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. En la configuración de visualización **[!UICONTROL Temas de tendencia]**:

   1. Seleccione una **[!UICONTROL métrica de clasificación]**. Por ejemplo: **[!UICONTROL conversaciones]**.
   1. De forma opcional, seleccione **[!UICONTROL Establecer atribución]** y seleccione **[!UICONTROL Modelo]**, **[!UICONTROL Contenedor]** y **[!UICONTROL Ventana retrospectiva]**.
   1. Seleccione un nivel para **[!UICONTROL Limitar niveles de subtema]**. El valor predeterminado es **[!UICONTROL Nivel 5]**.

      >[!NOTE]
      >
      >El **[!UICONTROL límite del nivel de subtema]** define el número máximo de niveles para explorar en profundidad los temas de la visualización. Si no hay más temas disponibles en un nivel dentro de ese número máximo definido, se mostrará ![Datos no disponibles](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL No se encontraron temas]**.

1. Seleccione **[!UICONTROL Build]** para generar la visualización. Seleccione **[!UICONTROL Restablecer]** para restablecer los valores predeterminados de configuración.

Para reconfigurar la visualización de los temas de tendencia, seleccione ![Editar](/help/assets/icons/Edit.svg) junto a **[!UICONTROL Métrica de clasificación: _métrica de clasificación_ | Niveles de subtema: _x_]**.

## Utiliza

Para utilizar la visualización:

* Para explorar en profundidad y ver los temas secundarios de tendencia de un tema en un nivel inferior, seleccione un tema en un nivel específico.

* Para comparar temas con otro intervalo de fechas, seleccione un intervalo de fechas en Comparar con. Para utilizar un intervalo de fechas personalizado:
  * Seleccione Intervalo de fechas personalizado en el menú desplegable y, en el cuadro de diálogo Nuevo intervalo de fechas, defina y guarde un intervalo de fechas personalizado.
  * Seleccione ese intervalo de fechas personalizado.

* Para mostrar un gráfico de líneas para la selección actual de temas, suelte una visualización [Line](/help/analysis-workspace/visualizations/line.md) en la visualización **[!UICONTROL Trending topics]**. La visualización **[!UICONTROL Line]** se vincula automáticamente a la visualización **[!UICONTROL Trending topics]**.

## Configuración

Están disponibles las siguientes [configuraciones de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) específicas.

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Mostrar valor real]** | Muestra el valor real de un tema. |
| **[!UICONTROL Porcentaje de visualización]** | Muestra el porcentaje de un tema. |



