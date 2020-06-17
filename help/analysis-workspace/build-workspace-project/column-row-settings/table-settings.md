---
description: La configuración de filas varía en función del componente que haya arrastrado a la tabla.
title: Configuración de filas
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---


# Configuración de filas

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

La configuración de filas varía en función del componente que haya arrastrado a la tabla.

También puede utilizar [acciones del botón secundario en una tabla](/help/analysis-workspace/visualizations/freeform-table.md) para administrar las filas seleccionadas.

Para obtener acceso a la configuración de fila de tabla, haga clic en el icono Configuración junto a una dimensión, segmento, métrica, periodo de tiempo o desglose dentro de cada uno de estos elementos:

![](assets/row-settings.png)

| Configuración de fila | Descripción |
|--- |--- |
| Comparaciones de fechas | Alinee fechas de cada columna para que todas empiecen en la misma fila.   Cuando alinea las fechas, por ejemplo, en una comparación mes a mes entre octubre y septiembre de 2016, la columna de la izquierda comenzará el 1 de octubre y la de la derecha, el 1 de septiembre.<br>Deshabilitado de forma predeterminada. |
| Porcentajes | Calcular porcentajes por fila obliga a la tabla improvisada a calcular los porcentajes de las celdas en la fila en lugar de en la columna. Esto es muy útil en los porcentajes de tendencias.<br>Habilitado de forma predeterminada al utilizar el icono Visualizar. |
| Totales de columna | Esta configuración solo se muestra con las [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL Mostrar la suma de las filas actuales como el total]**: muestra una suma del lado del cliente de las filas de la tabla, lo que significa que el total **no** eliminará las métricas duplicadas como visitas o visitantes.</li><li>**[!UICONTROL Mostrar total general:]** muestra una suma del lado del servidor, lo que significa que el total eliminará la duplicación de métricas como visitas o visitantes.</li></ul> |
| Desgloses | **[!UICONTROL Desglose por posición]**: puede realizar desgloses según una ubicación fija en una tabla improvisada. Por ejemplo, puede especificar que se desglosen siempre las primeras siete filas.<br>(Anteriormente, la lista de valores en el desglose estaba “bloqueada”. Esto llevaba a una situación en la que, por ejemplo, si realizaba un desglose de Fecha por Página, obtenía una lista de las 50 primeras páginas para el intervalo de fechas seleccionado. Si se guardaba ese informe y se ejecutaba un mes después, era probable que las 50 primeras páginas hubieran cambiado. No obstante, Analysis Workspace utilizaría los resultados del desglose original y devolvería las mismas páginas, pero con el mes en curso como intervalo de fechas.)<br>Para realizar desgloses basados en una ubicación fija: 1. Desglose algunas de las filas de su tabla. 2. Haga clic en el icono de Configuración (engranaje) junto a la fila que quiere en una posición fija. 3. Active la casilla junto a Desglose por posición. 4. Cambie el criterio de ordenación o el intervalo de fechas y verá que ahora los desgloses están vinculados a la posición de la fila, no a las filas en sí.<br>Deshabilitado de forma predeterminada. |