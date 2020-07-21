---
title: Valores de dimensión dinámicos vs. estáticos
description: Cómo interactuar con valores de dimensión dinámicos y estáticos en tablas.
translation-type: tm+mt
source-git-commit: 0477302df92ccab30d9f3a45cc7b22f2112a0c70
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 9%

---


# Valores de dimensión dinámicos frente a estáticos en tablas improvisadas

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

En las tablas improvisadas, las filas y columnas pueden contener varios valores de componente. Estos valores pueden ser dinámicos (cambian con el tiempo) o estáticos (no cambian con el tiempo), según la análisis que desee generar.

## Valores de dimensión dinámica

Los valores de dimensión dinámica cambian con el tiempo y dependen de la métrica por la que se ordena en la tabla improvisada. Los valores de dimensión dinámica son preferibles cuando desea analizar los elementos principales de un período de tiempo determinado.

Cuando se coloca una dimensión en una tabla improvisada, se devuelven filas dinámicas. Representan los elementos principales que corresponden a la dimensión de una métrica y un período de tiempo determinados. También puede colocar una dimensión en columnas de tabla improvisada y ésta se expande automáticamente a los 5 valores de dimensión principales.

Por ejemplo, cuando arrastra la dimensión Tipo de explorador a la tabla, los valores de dimensión Tipo de explorador principales (por ejemplo, Microsoft, Apple, Google, etc.) volver dinámicamente a las filas de tabla. Si se suelta en una columna, los 5 valores de dimensión Tipo de explorador principales devuelven dinámicamente.

Los valores de dimensión dinámica tienen la opción de filtro de fila y **no tienen** iconos de bloqueo y X.

## Valores de dimensión estáticos

Los valores de dimensión estáticos no cambian con el tiempo; son componentes fijos que siempre se devuelven en una tabla improvisada. Los valores de dimensión estáticos son preferibles cuando se desea analizar siempre el mismo elemento, ya sean campañas específicas o días específicos de la semana.

Cada vez que selecciona y suelta manualmente valores de componente específicos (dimensión, métrica, segmento, intervalo de fechas) en una tabla, el resultado es una lista estática de filas o columnas. También se pueden crear valores de dimensión estáticos si elige:

* En filas, haga clic con el botón derecho > [!UICONTROL Mostrar sólo las filas seleccionadas]
* Desde columnas, haga clic con el botón derecho > [!UICONTROL Convertir el elemento en estático]

Por ejemplo, cuando arrastra elementos específicos del tipo de navegador como Microsoft y Apple, esos dos elementos específicos siempre se arrastran a la tabla.

Los valores de dimensión estáticos **no tienen** la opción de filtro de fila. En su lugar, los iconos Bloquear y X están presentes en cada elemento. Haga clic en el icono X para eliminar ese valor de dimensión de la tabla.

## Valores de dimensión mixtos

Los valores de dimensión de diferentes dimensiones se pueden agregar a la misma tabla. En estos casos, el encabezado de fila indica &quot;Dimensiones mixtas&quot;. Estos valores de dimensión son estáticos. Por ejemplo, agregar valores de dimensión específicos de la dimensión Tipo de navegador y otros valores de dimensión de la dimensión Explorador.

## Filas totales improvisadas

Las filas dinámicas y estáticas se comportan de forma diferente en la fila total improvisada. De forma predeterminada:

* Las filas dinámicas se suman a las métricas de servidor y de duplicado, como visitas o visitantes
* Las filas estáticas se suman en el lado del cliente y **no eliminan** las métricas de duplicado.

[Obtenga más información sobre las opciones totales](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) de Workspace para filas dinámicas y estáticas.
