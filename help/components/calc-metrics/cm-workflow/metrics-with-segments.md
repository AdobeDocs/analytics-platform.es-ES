---
description: 'La segmentación de una métrica individual le permite realizar comparaciones de métricas dentro del mismo informe. '
title: Métricas segmentadas
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 0865c318c1390f2ad6d9864915254a7b8f68030f
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 45%

---

# Métricas filtradas

En el Creador de métricas calculadas, puede aplicar filtros dentro de su definición de métrica. Esto es útil si desea derivar nuevas métricas para usarlas en el análisis. Tenga en cuenta que las definiciones de filtros se pueden actualizar a través del Generador de filtros. Si se realizan cambios, el filtro se actualizará automáticamente en cualquier lugar donde se aplique, incluso si forma parte de una definición de métrica calculada.

![](assets/german-visitors.png)

## Crear una métrica filtrada {#create}

Supongamos que desea comparar diferentes aspectos de un filtro &quot;Visitantes alemanes&quot; con los de un filtro &quot;Visitantes internacionales&quot;. Puede crear métricas que le proporcionarán información como:

* ¿De qué forma se compara el contenido de navegación ente los dos grupos? (Otro ejemplo sería: ¿Cómo se compara la tasa de conversión entre los dos filtros?)
* Como un porcentaje de visitantes totales, ¿cuántos visitantes alemanes navegan por ciertas páginas en comparación con los visitantes internacionales?
* ¿Cuáles son las principales diferencias en términos de a qué contenido se accede mediante estos filtros diferentes?

1. Si no tiene un filtro comparable, cree un segmento ad hoc directamente en el Creador de métricas calculadas llamado &quot;Visitantes alemanes&quot;, donde &quot;Países&quot; es igual a &quot;Alemania&quot;. Arrastre la dimensión de países al lienzo de definición y seleccione que el valor sea Alemania:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >También puede hacerlo en la [Generador de filtros](/help/components/filters/create-filters.md), pero hemos simplificado el flujo de trabajo al establecer que las dimensiones estén disponibles en el Creador de métricas calculadas. &quot;Ad Hoc&quot; significa que el segmento no es visible en la variable **[!UICONTROL Filtros]** en el carril izquierdo. Sin embargo, puede hacerlo público si pasa el ratón por el icono “i”, que se sitúa junto a ella, y hace clic en **[!UICONTROL Hacer público]**.

1. Si no tiene un filtro comparable, cree un filtro llamado &quot;Visitantes internacionales&quot; donde &quot;Países&quot; no sea igual a &quot;Alemania&quot;.
1. Cree y guarde una métrica denominada &quot;Visitantes alemanes&quot; arrastrando el filtro de Alemania al lienzo Definición y la métrica de Visitantes únicos dentro de él:

   ![](assets/german-visitors.png)

1. Repita el paso 3 con el segmento de Visitantes internacionales y la métrica de Visitantes únicos para crear una métrica de Visitantes internacionales.
1. En Analysis Workspace, arrastre la dimensión **[!UICONTROL Página]** a una tabla de formato libre y, luego, las dos métricas calculadas nuevas en paralelo en la parte superior:

   ![](assets/workspace-pages.png)

A continuación, se muestra un vídeo introductorio:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Porcentaje del total de métricas {#percent-total}

Puede llevar el ejemplo anterior un paso más allá comparando el filtro con una población total. Para ello, cree dos métricas: “% de visitantes alemanes totales” y “% de visitantes internacionales totales”.

1. Coloque el filtro Visitantes de Alemania (o internacionales) en el lienzo.
1. Coloque otro filtro de Visitantes de Alemania (o internacionales) a continuación. Sin embargo, en esta ocasión, haga clic en el icono de configuración (el engranaje) para seleccionar “Total” como Tipo de métrica. El formato debe ser “Porcentaje”. El operador debe ser “dividido por”. Al final, tendrá esta definición de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica a su proyecto:

   ![](assets/cm_percent_total.png)
