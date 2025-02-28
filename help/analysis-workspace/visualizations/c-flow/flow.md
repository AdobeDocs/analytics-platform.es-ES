---
description: Obtenga información acerca de la función Flujo que muestra las rutas del cliente en sus sitios web y aplicaciones.
title: Resumen de flujos
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 25%

---

# Flujo {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Flujo"
>abstract="Cree una visualización para ver el flujo de personas de un punto de comprobación al siguiente."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Flujo"
>abstract="Analice el flujo de visitas o visitantes de un punto de contacto al siguiente. Especifique un componente (métrica, dimensión o elemento) con el que comenzar y con el que finalizar. De forma opcional, puede definir la configuración avanzada para configurar aún más la visualización."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización de flujo en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Ver [Flujo](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) para la_ ![versión de Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de este artículo._

>[!ENDSHADEBOX]


La visualización ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]** muestra las rutas del cliente en sus sitios web y aplicaciones.

Con la visualización puede:

* Visualice el recorrido del cliente a través de su sitio web o aplicación.
* Analizar a qué lugares van los clientes antes y después de los puntos de comprobación especificados, como la entrada, una dimensión específica o la salida.
* Cree filtros designando un punto específico en una ruta elegida.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Crear una visualización de flujo](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]


## Flujos interdimensionales

Puede mostrar el [flujo entre dimensiones](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Por ejemplo, puede combinar páginas y departamentos en un diagrama. En este caso, su flujo puede ir desde la página de inicio a la página Hombres y, a continuación, al departamento Zapatos.

Cada columna puede mostrar una dimensión distinta. Arrastre una dimensión y suéltela en una zona de colocación para añadir esa dimensión al diagrama.

>[!MORELIKETHIS]
>
>[Configurar una visualización de flujo](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Elija entre las visualizaciones de flujo, visitas en el orden previsto o lienzo de Recorrido

La visualización de flujo tiene similitudes con la [visualización de visitas en el orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) y la [visualización de lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), pero con diferencias importantes.

### Comprender las diferencias

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Cuándo usar Flujo

Las visualizaciones de flujo son las más adecuadas para:

* Análisis exploratorio y ad hoc para el siguiente punto de contacto inmediato en la ruta. (Utilice lienzo de Recorrido para los recorridos con una secuencia de páginas predefinidas o los que utilicen una ruta final).

* Recorridos no lineales con varios puntos de entrada y rutas. (Utilice lienzo de Recorrido para recorridos con una secuencia de páginas predefinidas).

Use [la tabla anterior](#understand-the-differences) para comprender las diferencias entre el flujo, las visitas en el orden previsto y el lienzo de Recorrido.
