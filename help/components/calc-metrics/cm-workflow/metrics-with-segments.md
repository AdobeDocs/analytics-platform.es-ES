---
description: El filtrado en métricas individuales le permite realizar comparaciones de métricas dentro del mismo informe.
title: Métricas filtradas
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 59%

---

# Métricas filtradas

En el Generador de métricas calculadas, puede aplicar filtros dentro de su definición de métrica. Esto es útil si desea derivar nuevas métricas para usarlas en el análisis. Tenga en cuenta que las definiciones de filtros se pueden actualizar a través del Generador de filtros. Si se realizan cambios, el filtro se actualizará automáticamente en cualquier lugar donde se aplique, incluso si forma parte de una definición de métrica calculada.

![](assets/german-visitors.png)

## Creación de una métrica filtrada {#create}

Digamos que desea comparar distintos aspectos de los filtros de “Visitantes alemanes” para aquellos de un filtro en “Visitantes internacionales”. Puede crear métricas que le proporcionarán información como:

* ¿De qué forma se compara el contenido de navegación ente los dos grupos? Otro ejemplo sería: ¿De qué forma se compara la tasa de conversión entre los dos filtros?
* Como porcentaje del total de personas, ¿cuántas personas alemanas navegan por determinadas páginas en comparación con las personas internacionales?
* ¿Cuáles son las principales diferencias en términos de a qué contenido se accede desde estos filtros diferentes?

Cree y guarde una métrica llamada &quot;Visitantes alemanes&quot; y una métrica llamada &quot;Visitantes internacionales&quot;:

1. Cree un filtro ad hoc en el Creador de métricas calculadas llamado &quot;Visitantes alemanes&quot;, donde &quot;Países&quot; es igual a &quot;Alemania&quot;. Arrastre la dimensión Países al lienzo Definición y seleccione [!UICONTROL **Alemania**] como valor:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >También puede hacer esto en la [Generador de filtros](/help/components/filters/create-filters.md), pero hemos simplificado el flujo de trabajo al establecer que las dimensiones estén disponibles en el Creador de métricas calculadas. &quot;Ad hoc&quot; significa que el filtro no es visible en la variable **[!UICONTROL Filtros]** en el carril izquierdo. Sin embargo, puede hacerlo público si pasa el ratón por el icono “i”, que se sitúa junto a ella, y hace clic en **[!UICONTROL Hacer público]**.

1. Arrastre el filtro de Alemania al lienzo Definición y arrastre la métrica Visitantes únicos dentro de este:

   ![](assets/german-visitors.png)

1. Seleccionar [!UICONTROL **Guardar**] para guardar la métrica calculada.

1. Cree un filtro ad hoc en el Creador de métricas calculadas llamado &quot;Visitantes internacionales&quot;, donde &quot;Países&quot; no es igual a &quot;Alemania&quot;.

   Arrastre la dimensión Países al lienzo Definición y seleccione [!UICONTROL **Alemania**] como valor, luego seleccione [!UICONTROL **no es igual a**] como operador.

1. Arrastre la métrica Visitantes únicos dentro.

1. Seleccionar [!UICONTROL **Guardar**] para guardar la métrica calculada.

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
