---
title: Operadores de filtro
description: Determine cómo interactúa un componente con un valor dentro de un filtro.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
source-git-commit: a8b884148a197b081e321582f70a9188a1bdc51e
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 97%

---

# Operadores de filtro

El Generador de filtros le permite comparar y restringir valores utilizando los operadores seleccionados. Existen dos categorías de operadores: [!UICONTROL Estándar] y [!UICONTROL Recuento específico].

## Operadores estándar

| Operador | Descripción |
| --- | --- |
| es igual que | Devuelve elementos que coinciden exactamente con un valor numérico o de cadena. Si utiliza caracteres comodín, utilice el operador “coincidencias”. |
| no es igual | Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido.  Si utiliza caracteres comodín, utilice el operador “no coincide con”. |
| es igual a cualquiera | Devuelve cualquier elemento que contenga la coincidencia de los valores de subcadena introducidos, delimitados por una coma. |
| contiene | Devuelve elementos que se comparan con las subcadenas de los valores introducidos. Por ejemplo, si la regla de una dimensión de cadena contiene `"Search"`, coincide con cualquier página que tenga la subcadena `"Search"` en ella, incluido `"Search Results"`, `"Search"` y `"Searching"`. Esta variable distingue entre mayúsculas y minúsculas. |
| no contiene | Todos los elementos que coincidan con el valor introducido se excluirán de los resultados. Por ejemplo, si la regla de una dimensión de cadena no contiene `"Search"`, excluye cualquier página que tenga la subcadena `"Search"` en ella, incluido `"Search Results"`, `"Search"` y `"Searching"`. |
| contiene todo | Devuelve elementos que incluyen todas las subcadenas (separadas por un espacio) en cualquier orden. Por ejemplo, al introducir `"Search Results"` con este operador coincidiría `"Search Results"` y `"Results of Search"`, pero no `"Search"` o `"Results"` de forma independiente. Este operador admite hasta 100 palabras delimitadas por espacios. |
| no contiene todos | Todos los elementos que coincidan con todo valor introducido se excluirán de los resultados. Por ejemplo, al introducir `"Search Results"` con este operador se excluiría `"Search Results"` y `"Results of Search"`, pero no `"Search"` o `"Results"`. Este operador admite hasta 100 palabras delimitadas por espacios. |
| contiene alguno | Devuelve elementos que contienen cualquiera de las subcadenas especificadas. Por ejemplo, al introducir `"Search Results"` con este operador coincidiría `"Search Results"`, `"Results of Search"`, `"Search"` y `"Results"`. Este operador admite hasta 100 palabras delimitadas por espacios. |
| no contiene ninguno | Todos los elementos que coinciden con cualquier subcadena se excluyen de los resultados. Por ejemplo, introducir `"Search Results"` excluiría `"Search Results"`, `"Results of Search"`, `"Search"` y `"Results"`. Este operador admite hasta 100 palabras delimitadas por espacios. |
| comienza con | Devuelve elementos que comienzan con el carácter o cadenas del valor introducido. |
| no comienza con | Devuelve todos los elementos que no comienzan con los caracteres o cadenas de los valores introducidos. |
| finaliza con | Devuelve elementos que terminan con el carácter o cadenas del valor introducido. |
| no termina con | Devuelve todos los elementos que no terminan con los caracteres o cadenas del valor introducido. |
| coincide | Devuelve elementos que coinciden exactamente en función de un determinado valor numérico o de cadena. Admite caracteres comodín que utilizan un asterisco (`*`). Este operador tiene distinción de mayúsculas y minúsculas. Por ejemplo:<ul><li>`a*e` coincide con `ae`, `abcde`, `adobe` y `a whole sentence`.</li><li>`adob*` coincide con `adobe`, `adobe analytics` y `adobo recipe`</li><li>`*dobe` coincide con `dobe`, `adobe` y `cute little dobe`.</li></ul> |
| no coincide | Se excluyen todos los elementos que coincidan con la cadena. Admite caracteres comodín que utilizan un asterisco (`*`). |
| existe | Devuelve elementos si el valor no es nulo. |
| no existe | Devuelve elementos si el valor no es nulo. |

## Operadores de recuento distinto

Puede segmentar un recuento distinto de elementos dentro de una dimensión. Por ejemplo, puede crear filtros para los visitantes que vieron más de 5 productos diferentes o visitas donde se vieron más de 5 páginas diferentes.

| Operador | Descripción |
| --- | --- |
| es igual que | Devuelve elementos de dimensión cuya cantidad única es igual al valor introducido. |
| no es igual | Devuelve elementos de dimensión cuya cantidad única no es igual al valor introducido. |
| es mayor que | Devuelve elementos de dimensión cuya cantidad única sea mayor que el valor introducido. |
| es menor que | Devuelve elementos de dimensión cuya cantidad única sea menor que el valor introducido. |
| es mayor o igual que | Devuelve elementos de dimensión cuya cantidad única sea mayor o igual que el valor introducido. |
| es menor o igual que | Devuelve elementos de dimensión cuya cantidad única sea menor o igual que el valor introducido. |
