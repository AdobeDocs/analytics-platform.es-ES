---
description: Utilice la visualización de líneas para representar conjuntos de datos de tendencias (basados en el tiempo)
title: Líneas
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: afe5b341ea1b442c23561299fbffce59dae45930
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 15%

---


# Líneas

La visualización Línea representa las métricas que utilizan una línea para mostrar cómo cambian los valores en un período de tiempo. Un gráfico de líneas solo se puede usar cuando se utiliza el tiempo como dimensión.

![Visualización de líneas](assets/line-viz.png)

>[!IMPORTANT]
>
>Algunos ajustes de visualización de línea, como [!UICONTROL Mostrar línea de tendencia], están actualmente en pruebas limitadas. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/landing/an-releases.html)

Haga clic en el icono de engranaje en la parte superior derecha de la visualización Línea para acceder a [**Configuración de visualización**](freeform-analysis-visualizations.md) disponible. La configuración se clasifica en:

* **General**:: Configuración común en los tipos de visualización
* **Eje**:: Configuración que afecta al eje x o y de la visualización de líneas
* **Superposiciones**:: Opciones para agregar contexto adicional a la serie que se muestra en la visualización de línea.

![Configuración de visualización](assets/viz-settings-modal.png)

## Cambiar la granularidad

Un menú desplegable de granularidad en la [configuración de visualización](freeform-analysis-visualizations.md) le permite cambiar una visualización de tendencias (p. ej., una línea o una barra) de diaria a semanal, mensual, etc. La granularidad también se actualiza en la tabla del origen de datos.

## Mostrar mínimo o máximo

Bajo **[!UICONTROL Configuración de visualización]** > **[!UICONTROL Superposiciones]** > **[!UICONTROL Mostrar mín./máx.]**, puede superponer una etiqueta de valor mínimo y máximo para resaltar rápidamente los picos y los valores de una métrica.

![Mostrar mín./máx.](assets/min-max-labels.png)

## Mostrar superposición de línea de tendencia

Bajo **[!UICONTROL Configuración de visualización]** > **[!UICONTROL Superposiciones]** > **[!UICONTROL Mostrar línea de tendencia]**, puede elegir agregar una línea de tendencia de regresión a la serie de líneas. Las líneas de tendencia ayudan a mostrar un patrón más claro en los datos.

![Línea de tendencia lineal](assets/show-linear-trendline.png)

Todos los modelos se ajustan con los mínimos cuadrados normales:

| Modelo | Descripción |
|---|---|
| Lineal | Crea una línea recta de mejor ajuste para conjuntos de datos lineales simples y resulta útil cuando los datos aumentan o disminuyen a una velocidad constante. Ecuación: `y = a + b * x` |
| Logarítmica | Crea una línea curva que se adapta mejor y resulta útil cuando la velocidad de cambio de los datos aumenta o disminuye rápidamente y luego se alza. Una línea de tendencia logarítmica puede utilizar valores negativos y positivos. Ecuación: `y = a + b * log(x)` |
| Exponencial | Crea una línea curva y resulta útil cuando los datos suben o disminuyen a tasas de crecimiento constantes. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: `y = a + e^(b * x)` |
| Potencia | Crea una línea curva y resulta útil para conjuntos de datos que comparan mediciones que aumentan a una velocidad específica. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: `y = a * x^b` |
| Valores cuadráticos | Busca el mejor ajuste para un conjunto de datos con forma de parábola (cóncava arriba o abajo). Ecuación: `y = a + b * x + c * x^2` |
