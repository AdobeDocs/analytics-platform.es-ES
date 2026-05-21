---
title: Elementos De Dimension Dinámicos Y Estáticos
description: Aprenda a utilizar elementos de dimensión dinámicos frente a estáticos en tablas de forma libre en Analysis Workspace.
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
TQID: https://experienceleague.adobe.com/q9X-MNr4r3Xrs16gAgH6-F3yrRDJP73xfXdd8BcFg84
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 77%

---

# Elementos de dimensión dinámicos y estáticos

En las tablas improvisadas, las filas y columnas pueden contener varios valores de componente. Estos valores pueden ser dinámicos (cambian con el tiempo) o estáticos (no cambian con el tiempo), según el análisis que desee generar.

## Elementos de dimensión dinámicos

Los elementos de dimensión dinámicos cambian con el tiempo y dependen de la métrica por la que se ordena en la tabla de forma libre. Se prefieren los elementos de dimensión dinámicos cuando desea analizar los elementos principales de un período de tiempo determinado.

Cuando se coloca una dimensión en una tabla de forma libre, se devuelven filas dinámicas. Las filas dinámicas representan los elementos principales que corresponden a la dimensión de una métrica y un período de tiempo determinados. También puede colocar una dimensión en columnas de tabla de forma libre y esta se expande automáticamente a los 5 elementos de dimensión principales.

Por ejemplo, cuando arrastra la dimensión Tipo de explorador a la tabla, los elementos de dimensión Tipo de explorador principales (por ejemplo, Microsoft, Apple, Google, etc.) volver dinámicamente a las filas de la tabla. Si se sueltan en una columna, los 5 elementos de dimensión Tipo de explorador principales se devuelven de forma dinámica.

Los elementos de dimensión dinámicos tienen la opción de filtro de fila ![Filter](/help/assets/icons/Filter.svg) y ![Close](/help/assets/icons/Close.svg), y **not** tienen un bloqueo ![LockClosed](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> Al hacer clic en ![Cerrar](/help/assets/icons/Close.svg) junto a un elemento de dimensión dinámica, se aplica automáticamente un filtro. Para obtener más información sobre cómo aplicar filtros a las tablas, consulte [Filtrar y ordenar tablas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Una tabla de forma libre que resalta el icono de filtro.](assets/dynamic-items.png)

## Elementos de dimensión estáticos

Los elementos de dimensión estáticos no cambian con el tiempo; son componentes fijos que siempre se devuelven en una tabla de forma libre. Se prefieren los elementos de dimensión estáticos cuando se desea analizar siempre el mismo elemento, ya sean campañas específicas o días específicos de la semana.

Cada vez que selecciona y suelta manualmente valores de componente específicos (dimensión, métrica, segmento, intervalo de fechas) en una tabla, el resultado es una lista estática de filas o columnas.

Por ejemplo, cuando arrastra elementos específicos de Tipo de explorador como Microsoft y Apple, esos dos elementos específicos siempre se arrastran a la tabla.

También se pueden crear elementos de dimensión estáticos si elige seleccionar **[!UICONTROL Mostrar solo las filas seleccionadas]** en el menú contextual para las filas seleccionadas.

Los elementos de dimensión estáticos **no** tienen la opción de filtro de fila. En su lugar, aparecen un ![BloqueoCerrado](/help/assets/icons/LockClosed.svg) y un ![Cerrar](/help/assets/icons/Close.svg) en cada elemento. Seleccione ![Cerrar](/help/assets/icons/Close.svg) para eliminar ese elemento de dimensión de la tabla.

![Una tabla de forma libre que muestra el tipo de explorador y la fila de Microsoft con un icono de candado. Nota: este elemento de dimensión es estático y no cambiará con el tiempo.](assets/static-items.png)

## Elementos de dimensión mixtos

Los elementos de dimensión de diferentes dimensiones se pueden agregar a la misma tabla. En estos casos, el encabezado de fila indica **[!UICONTROL Dimensiones mixtas]**. Estos elementos de dimensión son estáticos. Por ejemplo, si añade elementos de dimensión específicos desde la dimensión Grupo del explorador y otros elementos de dimensión desde la dimensión Nombre del explorador.

![Una tabla de forma libre que resalta la columna Dimensiones mixtas.](assets/mixed-dimensions.png)

## Filas totales improvisadas

Las filas dinámicas y estáticas se comportan de forma diferente en la fila total improvisada. De forma predeterminada:

* Las filas dinámicas se suman a las métricas del lado del servidor y a las duplicadas, como sesiones o personas.
* Las filas estáticas se suman al lado del cliente y **no** eliminan las métricas duplicadas. Para calcular el total de filas del lado del servidor, cambie la configuración fila a **Mostrar total general**. [Más información](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)
