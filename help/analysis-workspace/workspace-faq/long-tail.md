---
title: Elemento de dimensión de larga cola
description: Explica el elemento de dimensión Larga cola y por qué aparece en los informes.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 5603eef365365cea941ba5b261aeb56e58a84236
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 38%

---

# Advertencia de truncamiento

Cuando se utiliza una dimensión que contiene un gran número de valores únicos, a veces se muestra una advertencia que indica **[!UICONTROL Resultados truncados]**.  Esto significa que la arquitectura de informes que utiliza CJA contenía demasiados valores únicos para que se procesaran de forma eficiente y, por lo tanto, eliminaba los elementos que suponía menos importantes.

## Arquitectura de procesamiento de CJA y valores únicos

CJA procesa los informes en el momento en que se ejecutan y distribuye el conjunto de datos combinado a una serie de servidores. Los datos de cada servidor de procesamiento se agrupan por ID de persona, lo que significa que un solo servidor de procesamiento contiene todos los datos de una persona determinada. Una vez finalizado el procesamiento, entrega su subconjunto de datos procesados a un servidor de agregador. Todos los subconjuntos de datos procesados se combinan y se devuelven en forma de informe de Workspace.

Si un servidor individual agrega un conjunto de resultados que supera un umbral de tamaño, truncará los resultados antes de enviarlos de vuelta.  Esto mantiene el tráfico de red y la agregación en límites para permitir informes rápidos.  Como trunca los resultados solo con la vista de sus propios datos, es posible (aunque improbable) que los elementos mostrados en Analysis Workspace tengan valores de métricas incorrectos.

Elige qué elementos descartar en función de la métrica utilizada para la clasificación.  Si se trata de una métrica calculada, puede que no sea obvio cómo ordenarla, por lo que los resultados pueden ser menos precisos.  Por ejemplo, al calcular los ingresos por visitante, la cantidad total de ingresos y la cantidad total de visitantes se devuelven y agregan antes de hacer la división, y por lo tanto cada nodo elige qué artículos eliminar sin saber realmente cómo afectarán sus resultados a la clasificación general.

## Diferencias entre Larga cola y Bajo tráfico

En versiones anteriores de Analytics, se utilizaba una arquitectura de procesamiento diferente. Los datos se procesaban en el momento en que se recopilaron. Los elementos de dimensión se colocaban en Bajo tráfico después de que una dimensión alcanzara 500 000 valores únicos y aplicara un filtrado más agresivo con un millón de valores únicos. El recuento de valores únicos se restablecía al principio de cada mes de calendario. Los datos procesados eran permanentes; no había forma de sacar los datos existentes de Bajo tráfico.

En CJA, los elementos de dimensión solo se truncan si los resultados de un informe son demasiado grandes. Los datos procesados no son permanentes, lo que significa que puede reducir o eliminar el truncamiento modificando el informe.

## Reducción del elemento de dimensión Larga cola

Si desea reducir el truncamiento de &quot;larga cola&quot;, Adobe recomienda cualquiera de las siguientes opciones:

* Utilice un [filtro](/help/components/filters/create-filters.md). Los filtros se aplican en el momento en que cada servidor procesa un subconjunto de datos. Limitar el número de valores únicos que devuelven reduce el truncamiento &quot;Cola larga&quot;.
* Utilice una búsqueda.  Si se utiliza una búsqueda, los elementos que no coincidan con la búsqueda se truncarán primero, lo que aumenta la probabilidad de que vea los elementos que desea.
* Utilice una dimensión del conjunto de datos de búsqueda. Las dimensiones del conjunto de datos de búsqueda combinan elementos de dimensión del conjunto de datos de evento, lo que limita el número de valores únicos devueltos.

En general, es difícil consumir un informe que contenga demasiados elementos de dimensión únicos. Si aplica un filtro o una dimensión de conjunto de datos de consulta, puede reducir el truncamiento de &quot;cola larga&quot; y facilitar el consumo del informe.
