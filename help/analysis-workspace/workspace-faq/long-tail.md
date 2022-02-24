---
title: Elemento de dimensión de larga cola
description: Explica el elemento de dimensión Larga cola y por qué aparece en los informes.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '437'
ht-degree: 100%

---

# Elemento de dimensión de larga cola

Si utiliza una dimensión que contiene un gran número de valores únicos, a veces puede ver un valor en los informes etiquetado como **[!UICONTROL Larga cola]**. Este elemento de dimensión significa que la arquitectura de informes que utiliza CJA contenía demasiados valores únicos para que se procese.

## Arquitectura de procesamiento de CJA y valores únicos

CJA procesa los informes en el momento en que se ejecutan y distribuye el conjunto de datos combinado a una serie de servidores. Los datos de cada servidor de procesamiento se agrupan por ID de persona, lo que significa que un solo servidor de procesamiento contiene todos los datos de una persona determinada. Una vez finalizado el procesamiento, entrega su subconjunto de datos procesados a un servidor de agregador. Todos los subconjuntos de datos procesados se combinan y se devuelven en forma de informe de Workspace.

Si algún servidor individual que procese un subconjunto de datos encuentra más de 500 000 elementos de dimensión únicos, devuelve los 500 000 elementos de dimensión principales de su propio subconjunto y, a continuación, devuelve el resto en [!UICONTROL Larga cola]. El elemento de dimensión [!UICONTROL Larga cola] que se ve en un informe de Workspace es el total agregado de los valores de cada servidor de procesamiento individual que superaron los 500 000 valores únicos.

## Diferencias entre Larga cola y Bajo tráfico

En versiones anteriores de Analytics, se utilizaba una arquitectura de procesamiento diferente. Los datos se procesaban en el momento en que se recopilaron. Los elementos de dimensión se colocaban en Bajo tráfico después de que una dimensión alcanzara 500 000 valores únicos y aplicara un filtrado más agresivo con un millón de valores únicos. El recuento de valores únicos se restablecía al principio de cada mes de calendario. Los datos procesados eran permanentes; no había forma de sacar los datos existentes de Bajo tráfico.

En CJA, los elementos de dimensión solo se ponen en Larga cola si un servidor de procesamiento individual contiene más de 500 000 valores únicos. Los datos procesados no son permanentes, lo que significa que puede reducir el elemento de dimensión Larga cola modificando el informe.

## Reducción del elemento de dimensión Larga cola

Si desea reducir el elemento de dimensión Larga cola, Adobe recomienda cualquiera de las siguientes opciones:

* Utilice un [filtro](/help/components/filters/create-filters.md). Los filtros se aplican en el momento en que cada servidor procesa un subconjunto de datos. Limitar el número de valores únicos que devuelven reduce el elemento de dimensión Larga cola.
* Utilice una dimensión del conjunto de datos de búsqueda. Las dimensiones del conjunto de datos de búsqueda combinan elementos de dimensión del conjunto de datos de evento, lo que limita el número de valores únicos devueltos.

En general, es difícil utilizar un informe que contenga más de 500 000 elementos de dimensión únicos. Si aplica un filtro o una dimensión del conjunto de datos de consulta, puede reducir la presencia de Larga cola al mismo tiempo que facilita el uso del informe. Adobe tiene previsto mejorar esta experiencia a medida que CJA se desarrolle.
