---
description: La segmentación de una métrica individual le permite realizar comparaciones de métricas dentro del mismo informe.
title: Métricas segmentadas
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 96%

---

# Métricas filtradas

En el Generador de métricas calculadas, puede aplicar filtros dentro de su definición de métrica. Esto es útil si desea derivar nuevas métricas para usarlas en el análisis. Tenga en cuenta que las definiciones de filtros se pueden actualizar a través del Generador de filtros. Si se realizan cambios, el filtro se actualizará automáticamente en cualquier lugar donde se aplique, incluso si forma parte de una definición de métrica calculada.

![](assets/german-visitors.png)

## Creación de una métrica filtrada {#create}

Digamos que desea comparar distintos aspectos de los filtros de “Visitantes alemanes” para aquellos de un filtro en “Visitantes internacionales”. Puede crear métricas que le proporcionarán información como:

* ¿De qué forma se compara el contenido de navegación ente los dos grupos? Otro ejemplo sería: ¿De qué forma se compara la tasa de conversión entre los dos filtros?
* Como porcentaje del total de personas, ¿cuántas personas alemanas navegan por determinadas páginas en comparación con las personas internacionales?
* ¿Cuáles son las principales diferencias en términos de a qué contenido se accede desde estos filtros diferentes?

1. Si no tiene ningún filtro comparable, cree un segmento ad hoc en el creador de métricas calculadas que se llame “Visitantes alemanes”, en el que la opción “Países” sea “Alemania”. Arrastre la dimensión de países al lienzo de definición y seleccione que el valor sea Alemania:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >También puede llevar a cabo esta acción en el [Generador de filtros](/help/components/filters/create-filters.md), pero hemos simplificado el flujo de trabajo al establecer que las dimensiones estén disponibles en el creador de métricas calculadas. La opción “ad hoc” implica que el segmento no esté visible en la lista **[!UICONTROL Filtros]** del carril de la izquierda. Sin embargo, puede hacerlo público si pasa el ratón por el icono “i”, que se sitúa junto a ella, y hace clic en **[!UICONTROL Hacer público]**.

1. Si no tiene ningún filtro comparable, cree un segmento que se llame “Visitantes internacionales” en el que “Países” no sea igual a “Alemania”.
1. Cree y guarde una métrica llamada “Visitantes alemanes” arrastrando el filtro de Alemania al lienzo Definición y la métrica de Visitantes únicos dentro de este:

   ![](assets/german-visitors.png)

1. Repita el paso 3 con el segmento de Visitantes internacionales y la métrica de Visitantes únicos para crear una métrica de Visitantes internacionales.
1. En Analysis Workspace, arrastre la dimensión **[!UICONTROL Página]** a una tabla de forma libre y, luego, las dos métricas calculadas nuevas en paralelo en la parte superior:

   ![](assets/workspace-pages.png)

A continuación, se muestra un vídeo introductorio:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Porcentaje del total de métricas {#percent-total}

Puede llevar el ejemplo anterior un paso más allá comparando el filtro con una población total. Para ello, cree dos métricas: “% de visitantes alemanes totales” y “% de visitantes internacionales totales”.

1. Coloque el filtro de Visitantes alemanes (o internacionales) en el lienzo.
1. Coloque otro segmento de Visitantes alemanes (o internacionales) a continuación. Sin embargo, en esta ocasión, haga clic en el icono de configuración (el engranaje) para seleccionar “Total” como Tipo de métrica. El formato debe ser “Porcentaje”. El operador debe ser “dividido por”. Al final, tendrá esta definición de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica a su proyecto:

   ![](assets/cm_percent_total.png)
