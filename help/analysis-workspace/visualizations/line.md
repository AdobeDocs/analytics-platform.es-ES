---
description: Utilizar la visualización de líneas para representar conjuntos de datos de tendencias (basados en el tiempo)
title: Líneas
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 100%

---

# Líneas

La visualización de línea representa las métricas con una línea para mostrar cómo cambian los valores con el paso del tiempo. Un gráfico de líneas solo se puede usar cuando se utiliza el tiempo como dimensión.

![Visualización de líneas](assets/line-viz.png)

Haga clic en el icono del engranaje en la parte superior derecha de la Visualización de líneas para acceder a la [**Configuración de la visualización**](freeform-analysis-visualizations.md) disponible. La configuración se clasifica en:

* **General**: Configuración común en los tipos de visualización
* **Eje**: Configuración que afecta al eje x o y de la visualización de líneas
* **Superposiciones**: Opciones para añadir contexto adicional a la serie que se muestra en la visualización de líneas.

![Configuración de visualización](assets/viz-settings-modal.png)

## Cambiar la granularidad

Un menú desplegable de granularidad en la [configuración de visualización](freeform-analysis-visualizations.md) le permite cambiar una visualización de tendencias (p. ej., una línea o una barra) de diaria a semanal, mensual, etc. La granularidad también se actualiza en la tabla del origen de datos.

## Mostrar mínimo o máximo

En **[!UICONTROL Configuración de la visualización]** > **[!UICONTROL Superposiciones]** > **[!UICONTROL Mostrar mín/máx]**, puede superponer una etiqueta de valor mínimo y máximo para resaltar rápidamente los picos y las bajas de una métrica. Nota: Los valores mínimo/máximo se derivan de los puntos de datos visibles en la visualización, no del conjunto completo de valores dentro de una dimensión.

![Mostrar mín./máx.](assets/min-max-labels.png)

## Mostrar superposición de la línea de tendencia

En **[!UICONTROL Configuración de la visualización]** > **[!UICONTROL Superposiciones]** > **[!UICONTROL Mostrar línea de tendencia]**, puede elegir añadir una línea de tendencia de regresión o promedio móvil a la serie de líneas. Las líneas de tendencia ayudan a mostrar un patrón más claro en los datos.

>[!TIP]
>
>Se recomienda aplicar las líneas de tendencia a datos que no incluyan fechas de hoy (datos parciales) o futuras, ya que estas distorsionarán la línea de tendencia. Sin embargo, si necesita incluir fechas futuras, quite ceros de los datos para evitar que se distorsione durante esos días. Para ello, vaya a la tabla de fuente de datos de la visualización, elija la columna de métrica y, a continuación, habilite **[!UICONTROL Configuración de columna]** > **[!UICONTROL Interpretar cero como sin valor]**.

![Línea de tendencia lineal](assets/show-linear-trendline.png)

Todas las líneas de tendencia del modelo de regresión se ajustan con los mínimos cuadrados normales:

| Modelo | Descripción |
| --- | --- |
| Lineal | Crea una línea recta de mejor ajuste para conjuntos de datos lineales simples y resulta útil cuando los datos aumentan o disminuyen a una velocidad constante. Ecuación: `y = a + b * x` |
| Logarítmica | Crea una línea curva que se adapta mejor y resulta útil cuando la velocidad de cambio de los datos aumenta o disminuye rápidamente y luego se nivela. Una línea de tendencia logarítmica puede utilizar valores negativos y positivos. Ecuación: `y = a + b * log(x)` |
| Exponencial | Crea una línea curva y resulta útil cuando los datos suben o bajan a tasas de crecimiento constantes. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: `y = a + e^(b * x)` |
| Power | Crea una línea curva y resulta útil para conjuntos de datos que comparan mediciones que aumentan a una velocidad específica. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: `y = a * x^b` |
| Valores cuadráticos | Busca el mejor ajuste para un conjunto de datos con forma de parábola (cóncava arriba o abajo). Ecuación: `y = a + b * x + c * x^2` |
| Promedio móvil | Crea una línea de tendencia suave basada en un conjunto de promedios. Un promedio móvil utiliza una cantidad determinada de puntos de datos (definida por su selección de periodos), los promedia y utiliza el promedio como punto en la línea. Algunos ejemplos son un promedio móvil de 7 días o un promedio móvil de 4 semanas. |
