---
description: Aprenda a utilizar un histograma, que es similar a un gráfico de barras, pero agrupa números en rangos (contenedores).
title: Histograma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
autotag-review: '2026-05-19T08:31:33.712Z'
TQID: 'https://experienceleague.adobe.com/X9T4RpAiJ8uL0clPhyjffdl02kwd-k2Jv3O5t6iHfss'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 494
ht-degree: 77%

---

# Histograma {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histograma"
>abstract="Cree una visualización de histograma para representar la distribución de datos numéricos en grupos de intervalos."


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización del histograma en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consulte [Histograma](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/visualizations/histogram) para la_ ![versión de AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de este artículo._

>[!ENDSHADEBOX]


La visualización ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]** es similar a una visualización [!UICONTROL Barra], pero agrupa los números en rangos (intervalos). Analytics automatiza la creación de contenedores de números en rangos, pero puede modificar la configuración en [Configuración avanzada](#advanced-settings).

## Utiliza

Para crear un histograma:

1. Añada una visualización ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]**. Consulte [Añadir una visualización a un panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
1. Arrastre una métrica de la lista de componentes **[!UICONTROL Métricas]** o seleccione una métrica del menú desplegable [!UICONTROL *Agregar una métrica*].
1. (opcional) Seleccione **[!UICONTROL Mostrar configuración avanzada]** para: Consulte [Configuración avanzada](#advanced-settings).
1. Seleccione **[!UICONTROL Generar]**.

>[!NOTE]
>
>Los histogramas únicamente admiten métricas estándar, pero no métricas calculadas.

En el ejemplo siguiente, se utiliza un histograma para agrupar las sesiones en función del número de personas. El histograma muestra que la mayoría de las personas tienen entre 16 y 21 sesiones para el intervalo de fechas seleccionado.

![Histograma](assets/histogram.png)

## Configuración avanzada

Como parte de la visualización, hay una configuración específica del histograma.

| Configuración del histograma | Descripción |
|---|---|
| **[!UICONTROL Iniciando el intervalo]** | Determina por qué contenedor empieza el histograma. La opción predeterminada es “1”. Puede ajustar los números iniciales de 0 hasta el infinito (sin números negativos). |
| **[!UICONTROL Intervalos de métricas]** | Le permite aumentar/disminuir el número de rangos de datos (contenedores). El número máximo de contenedores es 50. |
| **[!UICONTROL Tamaño del intervalo de métricas]** | Le permite establecer el tamaño de cada contenedor. Por ejemplo, puede cambiar el tamaño del contenedor de 1 vista de página a 2 vistas de página. |
| **[!UICONTROL Método de recuento]** | Seleccione entre **[!UICONTROL Cuenta global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Cuenta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Grupo de compra]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Oportunidad]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Persona]**, **[!UICONTROL Sesión]**, **[!UICONTROL Evento]** u **[!UICONTROL Objeto]**. Por ejemplo, vistas de página por cuenta [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, vistas de página por sesión, o vistas de página por persona, o vistas de página por evento. Cuando seleccione **[!UICONTROL Objeto]**, seleccione el [contenedor personalizado](/help/data-views/create-dataview.md#containers-1) para el análisis de subeventos. |

<!--Russ or Meike - Check Hit Type link above. -->

**Ejemplos**:

| Iniciando el intervalo | Intervalos de métricas | Tamaño del intervalo de métricas | Resultado |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histograma, iniciando el intervalo 1, intervalos de métricas 5, tamaño de intervalo de métricas 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histograma, iniciando el intervalo 0, intervalos de métricas 3, tamaño del intervalo de métricas 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Agregar una visualización a un panelConfiguración de la visualizaciónMenú contextual de visualizaciónUso de histogramas para identificar valores de datos inesperados](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

