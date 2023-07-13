---
title: Elemento de dimensión Resultados truncados
description: Explica el elemento de dimensión "Resultados truncados" y por qué aparece en los informes.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: cf3c451cbefa7d6f9d5ea326c69fc2e5944881ff
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 13%

---

# Elemento de dimensión Resultados truncados

Cuando se utiliza una dimensión que contiene muchos valores únicos, un informe puede devolver un elemento de dimensión etiquetado como **[!UICONTROL Resultados truncados]**. Este elemento de dimensión significa que el informe solicitado contenía demasiados valores únicos para que se procese de forma eficaz. Como resultado, elimina los elementos que se consideran menos importantes.

## Arquitectura de procesamiento y valores únicos Customer Journey Analytics

El Customer Journey Analytics procesa los informes en el momento en que se ejecutan y distribuye el conjunto de datos combinado a varios servidores. Los datos de cada servidor de procesamiento se agrupan por ID de persona, lo que significa que un solo servidor de procesamiento contiene todos los datos de una persona determinada. Una vez que el servidor termina de procesarse, entrega su subconjunto de datos procesados a un servidor agregador. Todos los subconjuntos de datos procesados se combinan y se devuelven en forma de informe de Workspace.

Si algún servidor individual agrega un conjunto de resultados que supera un umbral de tamaño, trunca los resultados antes de enviarlos de vuelta. Esta optimización mantiene el tráfico de red y la agregación dentro de los límites para permitir una creación de informes rápida. Dado que cada servidor de procesamiento trunca los resultados solo con la vista de sus propios datos, es posible que los elementos que se muestran en Analysis Workspace tengan valores de métrica que estén ligeramente desfasados.

El servidor elige qué elementos de dimensión se descartan en función de la métrica que se utiliza para ordenar. Si la métrica de clasificación es una métrica calculada, el servidor utiliza métricas dentro de la métrica calculada para determinar qué elementos de dimensión se truncan. Dado que las métricas calculadas pueden contener varias métricas de importancia variable, los resultados pueden ser menos precisos. Por ejemplo, al calcular &quot;Ingresos por persona&quot;, la cantidad total de ingresos y el número total de personas se devuelven y se agregan antes de realizar la división. Como resultado, cada nodo elige qué elementos quitar sin saber cómo afectan sus resultados a la ordenación general.

## Diferencias entre &quot;Resultados truncados&quot; y &quot;Poco tráfico&quot;

En versiones anteriores de Adobe Analytics, se utilizaba una arquitectura de procesamiento diferente. Los datos se procesaban en el momento en que se recopilaron. Los elementos Dimension se colocaban en Bajo tráfico después de que una dimensión alcanzara 500 000 valores únicos y aplicara un filtrado más agresivo con un millón de valores únicos. El recuento &quot;Valor único&quot; se restablecía al principio de cada mes natural. Los datos procesados eran permanentes; no había forma de sacar los datos existentes de Bajo tráfico.

En Customer Journey Analytics, los elementos de dimensión solo se truncan si los resultados de un informe son demasiado grandes. Los datos procesados no son permanentes, lo que significa que puede reducir o eliminar el truncamiento modificando el informe.

## Reducción del elemento de dimensión &quot;Resultados truncados&quot;

Si desea reducir el número de eventos en el elemento de dimensión &quot;Resultados truncados&quot;, Adobe recomienda cualquiera de las siguientes opciones:

* Utilice un [Filtrar](/help/components/filters/create-filters.md). Los filtros se aplican en el momento en que cada servidor procesa un subconjunto de datos. Limitar el número de valores únicos que devuelven reduce el elemento de dimensión Resultados truncados.
* Utilice una búsqueda. Si se utiliza una búsqueda, los elementos que no coincidan con la búsqueda se eliminarán de los resultados del informe, lo que aumenta la probabilidad de que vea los elementos que desea.
* Utilice una dimensión del conjunto de datos de búsqueda. Las dimensiones del conjunto de datos de búsqueda combinan elementos de dimensión del conjunto de datos de evento, lo que limita el número de valores únicos devueltos.
