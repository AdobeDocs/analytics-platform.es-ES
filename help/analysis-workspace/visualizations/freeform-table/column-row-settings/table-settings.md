---
description: La configuración de filas varía en función del componente que haya arrastrado a la tabla.
title: Configuración de filas
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 94%

---

# Configuración de filas

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

La configuración de filas varía en función del componente que haya arrastrado a la tabla. Para acceder a la configuración de fila de tabla, haga clic en el icono Configuración junto a una dimensión, filtro, métrica, periodo de tiempo o desglose dentro de cada uno de estos elementos:

![](assets/row-settings.png)

| Configuración | Descripción |
|--- |--- |
| Alinear fechas | Esta es una configuración de nivel de tabla que alinea las fechas de cada columna con todos los inicios de la misma fila. La alineación de fechas está habilitada de forma predeterminada cuando se utiliza una dimensión de tiempo en las filas de la tabla y se aplican diferentes intervalos de fechas en las columnas. Por ejemplo, en una tabla diaria con octubre y septiembre aplicados en las columnas, la columna izquierda inicia con el 1 de octubre y la columna derecha inicia con el 1 de septiembre. |
| Desglose por posición | De forma predeterminada, esta configuración está deshabilitada y los desgloses se corrigen a elementos de fila estáticos. Por ejemplo, supongamos que desglosa los 3 elementos de dimensión de página principales (página principal, resultados de búsqueda, cierre de compra) por canal de marketing. Después abandona el proyecto y regresa dos semanas más tarde. Al volver a abrir el proyecto, las 3 páginas principales han cambiado, y ahora la página principal, los resultados de búsqueda y el cierre de compra son las 4 o 6 páginas principales. De forma predeterminada, los desgloses del canal de marketing seguirán apareciendo en la página principal, los resultados de búsqueda y el cierre de compra, aunque ahora se encuentren en las filas 4-6. <br> Por el contrario, **Desglose por posición** siempre desglosará los 3 elementos principales, independientemente de lo que sean. En referencia a nuestro ejemplo, cuando vuelva a abrir el proyecto, los desgloses de canal de marketing se vincularán a las 3 páginas principales de la tabla, no a la página principal, los resultados de búsqueda y el cierre de compra, que ahora están en las filas 4-6. |
| Porcentajes | **Calcular porcentajes por columna** es la configuración predeterminada; los porcentajes visibles en una columna se calculan en función del total de la columna. <br>**Calcular porcentajes por fila** obliga a la tabla improvisada a calcular los porcentajes de las celdas en la fila en lugar de en la columna, con el total general como denominador. Esto es muy útil en los porcentajes de tendencias. Esta configuración está habilitada de forma predeterminada al utilizar el icono Visualizar. |
| Totales de columna | Esta configuración solo está disponible para [filas estáticas](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Mostrar como la suma de las filas actuales** muestra una suma del lado del cliente de las filas de la tabla, lo que significa que el total *no* deduplicará las métricas como visitas o visitantes. <br> **Mostrar el total general** muestra una suma del lado del servidor, lo que significa que el total anulará el duplicado de las métricas. |
