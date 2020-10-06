---
title: Elemento de dimensión de cola larga
description: Explica el elemento de dimensión "Larga cola" y por qué aparece en sistema de informes.
translation-type: tm+mt
source-git-commit: ff1a11a18de0825b6338de98865e3bddeef14f39
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Elemento de dimensión de cola larga

Si utiliza una dimensión que contiene un gran número de valores únicos, a veces puede ver un valor en el sistema de informes etiquetado como &quot;Larga cola&quot;. Este elemento de dimensión significa que el CJA de la arquitectura de sistema de informes contiene demasiados valores únicos para que se procese.

## Arquitectura de procesamiento de CJA y valores únicos

CJA procesa los informes en el momento en que se ejecutan, distribuyendo el conjunto de datos combinado a una serie de servidores. Los datos por servidor de procesamiento se agrupan por ID de persona, lo que significa que un único servidor de procesamiento contiene todos los datos de una persona determinada. Una vez finalizado el procesamiento, entrega su subconjunto de datos procesados a un servidor de agregador. Todos los subconjuntos de datos procesados se combinan y devuelven en forma de informe de Workspace.

Si algún servidor individual que procesa un subconjunto de datos encuentra más de 500.000 elementos de dimensión únicos, devuelve los 500.000 elementos de dimensión principales de su propio subconjunto y, a continuación, devuelve el resto en &#39;Cola larga&#39;. El elemento de dimensión &#39;Cola larga&#39; que se ve en un informe de Workspace es el total agregado de los valores individuales de cada servidor de procesamiento que superan los 500.000 valores únicos.

## Diferencias entre &#39;Cola larga&#39; y &#39;Poco tráfico&#39;

En versiones anteriores de Adobe Analytics, se utilizaba una arquitectura de procesamiento diferente. Los datos se procesaron en el momento en que se recopilaron. Los elementos de Dimension se colocaron en &#39;Poco tráfico&#39; después de que una dimensión alcanzara valores únicos de 500.000 y se aplicara un filtrado más agresivo en valores únicos de 1M. El recuento de valores únicos se restableció al principio de cada mes calendario. Los datos procesados eran permanentes; no había forma de obtener los datos existentes de &quot;Poco tráfico&quot;.

En CJA, los elementos de dimensión solo se colocan en &#39;Cola larga&#39; si un servidor de procesamiento individual contiene más de 500.000 valores únicos. Los datos procesados no son permanentes, lo que significa que puede reducir el elemento de dimensión &#39;Cola larga&#39; modificando el informe.

## Reducir el elemento de dimensión &#39;Cola larga&#39;

Si desea reducir el elemento de dimensión &#39;Cola larga&#39;, Adobe recomienda cualquiera de las siguientes opciones:

* Utilice un filtro. Los filtros se aplican en el momento en que cada servidor procesa un subconjunto de datos. Al limitar el número de valores únicos que devuelven, se reduce el elemento de dimensión &#39;Cola larga&#39;.
* Utilice una dimensión de conjunto de datos de búsqueda. Las dimensiones del conjunto de datos de búsqueda combinan elementos de dimensión del conjunto de datos de evento, lo que limita el número de valores únicos devueltos.

En general, es difícil consumir un informe que contenga más de 500.000 elementos de dimensión únicos. Si aplica una dimensión de segmento o de conjunto de datos de búsqueda, puede reducir la presencia de &#39;Cola larga&#39; y, al mismo tiempo, facilitar el consumo del informe. El Adobe tiene previsto mejorar esta experiencia a medida que se siga desarrollando la ECP.
