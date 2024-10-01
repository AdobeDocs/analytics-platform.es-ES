---
title: Dimensiones de alta cardinalidad
description: Explica cómo gestiona Customer Journey Analytics las dimensiones con muchos valores únicos
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 6%

---

# Dimensiones de alta cardinalidad

Al utilizar una dimensión que contiene muchos valores únicos, el informe resultante puede contener demasiados elementos de dimensión únicos para mostrar o calcular. Los resultados se truncan al eliminar los elementos de dimensión que se consideran menos importantes. Estas optimizaciones se realizan para mantener el rendimiento del proyecto y del producto.

Cuando se solicita un informe con demasiados valores únicos, Analysis Workspace muestra un indicador en el encabezado de la dimensión que indica que no se incluyen todos los elementos de dimensión. Por ejemplo, **[!UICONTROL Filas: 1-50 de más de 22.343.156]**. La palabra clave **[!UICONTROL more than]** indica que se aplicó alguna optimización al informe para devolver los elementos de dimensión más importantes.

![Tabla de forma libre en Workspace que muestra la palabra clave &quot;más que&quot; para mostrar 1-50 de más de 22.343.156](assets/high-cardinality.png)

## Determinación de los elementos de dimensión que se van a mostrar

El Customer Journey Analytics procesa los informes en el momento en que se ejecutan y distribuye el conjunto de datos combinado a varios servidores. Los datos de cada servidor de procesamiento se agrupan por ID de persona, lo que significa que un solo servidor de procesamiento contiene todos los datos de una persona determinada. Una vez que un servidor termina de procesarse, entrega su subconjunto de datos procesados a un servidor agregador. Todos los subconjuntos de datos procesados se combinan y se devuelven en forma de informe de Workspace.

Si algún servidor individual procesa datos que superan un umbral único, trunca los resultados antes de devolver el subconjunto de datos procesado. Los elementos de dimensión truncados se determinan en función de la métrica que se utiliza para ordenar.

Si la métrica de clasificación es una métrica calculada, el servidor utiliza las métricas dentro de la métrica calculada para determinar qué elementos de dimensión se truncan. Dado que las métricas calculadas pueden contener varias métricas de importancia variable, los resultados pueden ser menos precisos. Por ejemplo, al calcular &quot;Ingresos por persona&quot;, la cantidad total de ingresos y el número total de personas se devuelven y se agregan antes de realizar la división. Como resultado, cada servidor de procesamiento individual elige qué elementos quitar sin saber cómo afectan sus resultados a la ordenación general.

Aunque es posible que falten algunos elementos de dimensión individuales en los informes de alta cardinalidad, los totales de columna son precisos y no se basan en datos truncados. La función &quot;Recuento distinto&quot; de las métricas calculadas tampoco se ve afectada por los elementos de dimensión truncados.

## Prácticas recomendadas para dimensiones de alta cardinalidad

La mejor manera de dar cabida a las dimensiones de alta cardinalidad es limitar el número de elementos de dimensión que procesa un informe. Dado que todos los informes se procesan en el momento en que se solicitan, puede ajustar los parámetros del informe para obtener resultados inmediatos. El Adobe recomienda cualquiera de las siguientes optimizaciones para las dimensiones de alta cardinalidad:

* Usar un [filtro](/help/components/filters/create-filters.md). Los filtros se aplican en el momento en que cada servidor procesa un subconjunto de datos.
* Utilice una búsqueda. Los elementos de Dimension excluidos del término de búsqueda se eliminan de los resultados del informe, lo que aumenta la probabilidad de que vea los elementos de dimensión deseados.
* Utilice una dimensión del conjunto de datos de búsqueda. Las dimensiones del conjunto de datos de búsqueda combinan elementos de dimensión del conjunto de datos de evento, lo que limita el número de valores únicos devueltos.
* Use la configuración del componente [Incluir/excluir](/help/data-views/component-settings/include-exclude-values.md) en el administrador de vista de datos.
* Reduzca el intervalo de fechas de la solicitud. Si muchos valores únicos se acumulan con el tiempo, acortar el intervalo de fechas del informe de Workspace puede limitar el número de valores únicos que deben procesar los servidores.
* Considere utilizar [Exportación de tabla completa](/help/analysis-workspace/export/export-cloud.md) para devolver todas las filas de la tabla.
