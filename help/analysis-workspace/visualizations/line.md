---
description: Utilice la visualización de líneas para representar conjuntos de datos visualizados (basados en el tiempo).
title: Líneas
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
autotag-review: '2026-05-19T08:29:43.526Z'
TQID: 'https://experienceleague.adobe.com/ekT5diDY2vDPhjZ5I2oe-lgqjQ--Ri-bO-UljZUUmJw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 566
ht-degree: 83%

---

# Líneas {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="Líneas"
>abstract="Cree una visualización de líneas que muestre cómo cambian los valores con el paso del tiempo. Una visualización de líneas solo se puede usar cuando se utiliza el tiempo como dimensión."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización de línea en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Vea [Line](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/line) para la_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** versión de este artículo._

>[!ENDSHADEBOX]


La visualización de la **[!UICONTROL línea]**![Tendencia del gráfico](/help/assets/icons/GraphTrend.svg) representa las métricas con una línea para mostrar cómo cambian los valores con el paso del tiempo. Una visualización de líneas solo se puede usar cuando se utiliza el tiempo como dimensión.

![Visualización de líneas](assets/line-viz.png)


## Configuración

Como parte de [configuración de visualización](freeform-analysis-visualizations.md#settings), hay disponible una configuración de visualización de línea específica.

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Granularidad]** | Seleccione en la lista desplegable de granularidad para cambiar una visualización de tendencias de diaria a semanal, mensual, etc. La granularidad también se actualiza en la tabla de la fuente de datos. |
| **[!UICONTROL Mostrar mínimo]** <br/>**[!UICONTROL Mostrar máximo ]** | Puede superponer una etiqueta de valor mínimo y máximo para resaltar los valores mínimo y máximo de una métrica. Los valores mínimo/máximo se derivan de los puntos de datos visibles en la visualización, no del conjunto completo de valores dentro de una dimensión.<br/>![Una superposición con la etiqueta de valor mínimo y máximo.](assets/min-max-labels.png) |
| **[!UICONTROL Mostrar línea de tendencia]** | Puede añadir una regresión o una línea de tendencia de promedio móvil a la serie de líneas. Las líneas de tendencia ayudan a mostrar un patrón más claro en los datos. Cuando esté seleccionado, elija un modelo de la lista. Consulte [Modelos](#models) para obtener información general y detallada de los modelos disponibles.<br/>![Línea de tendencia lineal](assets/show-linear-trendline.png).<p>**SUGERENCIA:** Se recomienda aplicar las líneas de tendencia a datos que no incluyan fechas de hoy (datos parciales) o futuras. Las fechas de hoy o futuras distorsionan la línea de tendencia. Sin embargo, si necesita incluir fechas futuras, quite ceros de los datos para evitar que se distorsione durante esos días. Vaya a la tabla de fuente de datos de la visualización, elija la columna de métrica y, a continuación, habilite **[!UICONTROL Configuración de columna]** > **[!UICONTROL Interpretar cero como sin valor]**.</p> |

### Modelos

Todas las líneas de tendencia del modelo de regresión se ajustan con los mínimos cuadrados normales:

| Modelo | Descripción |
| --- | --- |
| **[!UICONTROL Lineal]** | Crea una línea recta que se adapta mejor para conjuntos de datos lineales simples y resulta útil cuando los datos aumentan o disminuyen a una velocidad constante. Ecuación: `y = a + b * x` |
| **[!UICONTROL Logarítmica]** | Crea una línea curva que se adapta mejor y resulta útil cuando la velocidad de cambio de los datos aumenta o disminuye rápidamente y luego se nivela. Una línea de tendencia logarítmica puede utilizar valores negativos y positivos. Ecuación: `y = a + b * log(x)` |
| **[!UICONTROL Exponencial]** | Crea una línea curva y resulta útil cuando los datos suben o bajan a tasas de crecimiento constantes. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: `y = a + e^(b * x)` |
| **[!UICONTROL Potencia]** | Crea una línea curva y resulta útil para conjuntos de datos que comparan mediciones que aumentan a una velocidad específica. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: `y = a * x^b` |
| **[!UICONTROL Cuadrática]** | Busca el mejor ajuste para un conjunto de datos con forma de parábola (cóncava arriba o abajo). Ecuación: `y = a + b * x + c * x^2` |
| **[!UICONTROL Promedio móvil]** | Crea una línea de tendencia suave basada en un conjunto de promedios. Un promedio móvil utiliza una cantidad determinada de puntos de datos (definida por su selección de [!UICONTROL Granularidad]), los promedia y utiliza el promedio como punto en la línea. Algunos ejemplos son un promedio móvil de siete días o un promedio móvil de cuatro semanas. |


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Line](https://experienceleague.adobe.com/es/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/visualizations/line-visualization){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

>[!MORELIKETHIS]
>
>[Agregar una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configuración de la visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menú contextual de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

