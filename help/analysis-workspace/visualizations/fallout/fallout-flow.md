---
description: Aprenda a utilizar la visualización de abandonos en Analysis Workspace.
title: Información general de visitas en orden previsto
feature: Visualizations
exl-id: c4338821-64ac-4345-828a-15af18a95ea6
role: User
autotag-review: '2026-05-19T08:41:54.033Z'
TQID: 'https://experienceleague.adobe.com/sitlejANJcDN2u-baGg2iz2SaOyZJe8jbyXjgBbasss'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 389
ht-degree: 80%

---

# Resumen de visita en orden previsto {#fallout-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_fallout_button"
>title="Visita en orden previsto"
>abstract="Crea una visualización para ver cómo se accede de forma correcta a los puntos de comprobación deseados."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización de abandonos en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Vea [Visitas en el orden previsto](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow) para la_ ![versión de AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de este artículo._

>[!ENDSHADEBOX]

Una visualización ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Visita en orden previsto]** muestra dónde los visitantes se fueron (abandonaron) y continuaron (fracasaron) en una secuencia de páginas predefinidas.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Crear una visualización de visitas en orden previsto](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]


Las visualizaciones de visitas en el orden previsto le permiten:

* Realizar comparaciones paralelas de dos segmentos distintos en el mismo informe.
* Arrastrar y soltar (y reorganizar) pasos de canal (puntos de contacto).
* Mezclar y combinar valores de distintas dimensiones y métricas
* Crear un informe de visitas en el orden previsto multidimensional
* Identificar a qué lugar van los clientes inmediatamente tras la visita en el orden previsto

Las visitas en el orden previsto muestran la conversión y las tasas de visitas en el orden previsto entre cada paso o punto de contacto en una secuencia.

Por ejemplo, se puede hacer un seguimiento de los puntos de la visita en el orden previsto durante un proceso de compra. Solo tiene que seleccionar un punto de contacto inicial y un punto de contacto de conclusión, y añadir puntos de contacto intermedios para crear una ruta de navegación del sitio web. Pero también puede hacer visitas en el orden previsto multidimensional.

## Elija entre las visualizaciones Visita en el orden previsto, Flujo y Lienzo de recorridos

La visualización de visitas en el orden previsto tiene similitudes con la [visualización de flujo](/help/analysis-workspace/visualizations/c-flow/flow.md) y la [visualización de lienzo de recorridos](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).

### Conocer las diferencias

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Cuándo se utiliza la visita en el orden previsto

Las visualizaciones de visitas en el orden previsto y [lienzo de recorridos](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) son útiles para analizar:

* Las tasas de conversión a través de procesos específicos en el sitio (tales como un proceso de registro o de compra).
* Flujos de tráfico generales, con un ámbito más amplio: de las personas que visitaron la página de inicio, este flujo muestra cuántas realizaron una búsqueda. Y cuántas de ellas finalmente miraron un artículo específico.
* Correlaciones entre los eventos del sitio. Las correlaciones muestran el porcentaje de personas que leyeron la política de privacidad y procedieron a realizar la compra de un producto.

Las visualizaciones de visitas en el orden previsto son las más adecuadas para:

* Realizar un análisis de las visitas en el orden previsto que incluya recorridos con una secuencia predefinida de páginas y un único punto de entrada y ruta. (Utilice el lienzo de recorridos para recorridos con varios puntos de entrada y rutas).

* Los recorridos en los que necesite realizar comparaciones paralelas de dos segmentos distintos en el mismo informe.

Use [la tabla anterior](#understand-the-differences) para conocer las diferencias entre las visualizaciones de lienzo de recorridos, visitas en el orden previsto y flujo.

>[!MORELIKETHIS]
>
>[Configurar una visualización de abandonos](configuring-fallout.md)



