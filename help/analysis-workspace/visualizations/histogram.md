---
description: Un histograma es similar a un gráfico de barras, pero agrupa números en rangos (contenedores).
title: Histograma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: f8abf388e0cb1e2e2eb9ff69fed2c542a26dcd66
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 34%

---

# Histograma {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histograma"
>abstract="Cree una visualización de histograma para representar la distribución de datos numéricos en grupos de intervalos."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Este artículo documenta la visualización del histograma en ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)**Customer Journey Analytics**.<br/>Ver [Histograma](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/histogram) para la versión de ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)**Adobe Analytics**de este artículo.*

>[!ENDSHADEBOX]


La visualización ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]** es similar a una visualización de [!UICONTROL Barra], pero agrupa números en rangos (contenedores). Analytics automatiza la creación de contenedores de números en rangos, pero puede modificar la configuración en [Configuración avanzada](#advanced-settings).

## Utiliza

Para crear un histograma:

1. Agregue una visualización de ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]**. Consulte [Agregar una visualización a un panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Arrastre una métrica de la lista de componentes **[!UICONTROL Métricas]** o seleccione una métrica del menú desplegable [!UICONTROL *Agregar una métrica*].
1. (opcional) Seleccione **[!UICONTROL Mostrar configuración avanzada]**. Consulte [Configuración avanzada](#advanced-settings).
1. Seleccione **[!UICONTROL Generar]**.

>[!NOTE]
>
>Los histogramas únicamente admiten métricas estándar, pero no métricas calculadas.

En el ejemplo siguiente, se utiliza un histograma para agrupar las sesiones por el número de personas. El histograma muestra que la mayoría de las personas tienen entre 16 y 21 sesiones para el intervalo de fechas seleccionado.

![](assets/histogram.png)

## Configuración avanzada

Como parte de la visualización, hay disponibles ajustes específicos de histograma.

| Configuración de histograma | Descripción |
|---|---|
| **[!UICONTROL Iniciando el depósito]** | Determina por qué contenedor empieza el histograma. La opción predeterminada es “1”. Puede ajustar los números iniciales de 0 hasta el infinito (sin números negativos). |
| **[!UICONTROL Contenedores de métricas]** | Le permite aumentar/disminuir el número de rangos de datos (contenedores). El número máximo de contenedores es 50. |
| **[!UICONTROL Tamaño del contenedor de métricas]** | Le permite establecer el tamaño de cada contenedor. Por ejemplo, puede cambiar el tamaño del contenedor de 1 vista de página a 2 vistas de página. |
| **[!UICONTROL Método de recuento]** | Seleccione entre **[!UICONTROL Persona]**, **[!UICONTROL Sesión]** o **[!UICONTROL Evento]**. Por ejemplo, vistas de página por sesión o vistas de página por persona o vistas de página por evento. |

<!--Russ or Meike - Check Hit Type link above. -->

**Ejemplos**:

| Iniciando el depósito | Bloques de métricas | Tamaño del contenedor de métricas | Resultado  |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histograma, contenedor inicial 1, contenedores de métricas 5, tamaño del contenedor de métricas 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histograma, contenedor inicial 0, contenedores de métricas 3, tamaño del contenedor de métricas 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Agregar una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configuración de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menú contextual de visualización ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


## Publicación de blog

Consulte esta publicación de blog acerca de información sobre [el uso de histogramas para identificar valores de datos inesperados](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168).
