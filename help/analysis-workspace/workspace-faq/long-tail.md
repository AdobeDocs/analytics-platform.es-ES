---
title: Elemento de dimensión de cola larga
description: Explica el elemento de dimensión "Cola larga" y por qué aparece en los informes.
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 8cee89a8ed656ad6376e64c8327aa7c94a937ce9
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Elemento de dimensión de cola larga

Si utiliza una dimensión que contiene un gran número de valores únicos, a veces puede ver un valor en los informes etiquetado **[!UICONTROL Cola larga]**. Este elemento de dimensión significa que la arquitectura de informes que utiliza CJA contenía demasiados valores únicos para que se procese.

## Arquitectura de procesamiento de CJA y valores únicos

CJA procesa los informes en el momento en que se ejecutan, distribuyendo el conjunto de datos combinado a una serie de servidores. Los datos por servidor de procesamiento se agrupan por ID de persona, lo que significa que un solo servidor de procesamiento contiene todos los datos de una persona determinada. Una vez finalizado el procesamiento, entrega su subconjunto de datos procesados a un servidor de agregador. Todos los subconjuntos de datos procesados se combinan y se devuelven en forma de informe de Workspace.

Si algún servidor individual que procese un subconjunto de datos encuentra más de 500 000 elementos de dimensión únicos, devuelve los 500 000 elementos de dimensión principales de su propio subconjunto y, a continuación, devuelve el resto en &quot;[!UICONTROL Cola larga]&quot;. El elemento de dimensión &#39;[!UICONTROL Cola larga]&#39; que se ve en un informe de Workspace es el total agregado de cada valor de servidor de procesamiento individual que superó los 500 000 valores únicos.

## Diferencias entre &quot;cola larga&quot; y &quot;poco tráfico&quot;

En versiones anteriores de Analytics, se utilizaba una arquitectura de procesamiento diferente. Los datos se procesaron en el momento en que se recopilaron. Los elementos de Dimension se colocaron en &quot;Poco tráfico&quot; después de que una dimensión alcanzara valores únicos de 500 000 y aplicara filtros más agresivos a valores únicos de 1M. Se restableció el recuento de valores únicos al principio de cada mes del calendario. Los datos procesados eran permanentes; no había forma de sacar los datos existentes de &quot;Poco tráfico&quot;.

En CJA, los elementos de dimensión solo se ponen en &quot;Cola larga&quot; si un servidor de procesamiento individual contiene más de 500 000 valores únicos. Los datos procesados no son permanentes, lo que significa que puede reducir el elemento de dimensión &quot;Cola larga&quot; modificando el informe.

## Reducir el elemento de dimensión &quot;Cola larga&quot;

Si desea reducir el elemento de dimensión &quot;Cola larga&quot;, Adobe recomienda cualquiera de las siguientes opciones:

* Utilice un [filtro](/help/components/filters/create-filters.md). Los filtros se aplican en el momento en que cada servidor procesa un subconjunto de datos. Limitar el número de valores únicos que devuelven reduce el elemento de dimensión &quot;Cola larga&quot;.
* Utilice una dimensión de conjunto de datos de búsqueda. Las dimensiones del conjunto de datos de búsqueda combinan elementos de dimensión del conjunto de datos de evento, lo que limita el número de valores únicos devueltos.

En general, es difícil consumir un informe que contenga más de 500 000 elementos de dimensión únicos. Si aplica un filtro o una dimensión de conjunto de datos de consulta, puede reducir la presencia de &quot;Seguimiento largo&quot; al mismo tiempo que facilita el consumo del informe. El Adobe tiene previsto mejorar esta experiencia a medida que CJA se desarrolla.
