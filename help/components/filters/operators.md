---
title: Operadores
description: Determine cómo interactúa un componente con un valor dentro de un segmento.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: 85a22d1e57925f0512ce0cc658cfba1008339d91
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 54%

---

# Operadores

El Generador de segmentos le permite comparar y restringir valores para componentes utilizando los operadores seleccionados. Existen dos categorías de operadores: [[!UICONTROL Estándar]](#standard-operators) y [[!UICONTROL Recuento específico]](#distinct-count-operators).

## Operadores estándar

| Operador | Descripción |
| --- | --- |
| **[!UICONTROL es igual a]** | Devuelve elementos que coinciden exactamente con un valor numérico o de cadena. Si utiliza caracteres comodín, utilice el operador coincidencias. |
| **[!UICONTROL no es igual a]** | Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido.  Si utiliza caracteres comodín, utilice el operador no coincide con. |
| **[!UICONTROL es igual a cualquiera de]** | Devuelve cualquier elemento que contenga la coincidencia de los valores de subcadena introducidos, delimitados por una coma. |
| **[!UICONTROL contiene]** | Devuelve elementos que se comparan con las subcadenas de los valores introducidos. Por ejemplo, si el valor de una dimensión Nombre de página contiene `Search`, este operador coincide con cualquier página que tenga la subcadena `Search` en su nombre, incluidos `Search Results`, `Search` y `Searching`. Esta variable distingue entre mayúsculas y minúsculas. |
| **[!UICONTROL no contiene]** | Todos los elementos que coincidan con el valor introducido se excluirán de los resultados. Por ejemplo, si el valor de una dimensión Nombre de página no contiene `Search`, este operador excluye cualquier página que tenga la subcadena `Search` en su nombre, incluidos `Search Results`, `Search` y `Searching`. |
| **[!UICONTROL contiene todo]** | Devuelve elementos que incluyen todas las subcadenas (separadas por un espacio) en cualquier orden. Por ejemplo, si se especifica `Search Results` como el valor de este operador, coincidirá con `Search Results` y `Results of Search`, pero no con `Search` ni con `Results` de forma independiente. Este operador admite hasta 100 palabras delimitadas por espacios. |
| **[!UICONTROL no contiene todos]** | Todos los elementos que coincidan con cada valor introducido se excluirán de los resultados. Por ejemplo, si se especifica `Search Results` como el valor de este operador, se excluirían `Search Results` y `Results of Search`, pero no `Search` ni `Results`. Este operador admite hasta 100 palabras delimitadas por espacios. |
| **[!UICONTROL contiene alguno]** | Devuelve elementos que contienen cualquiera de las subcadenas especificadas. Por ejemplo, si se especifica `Search Results` como el valor de este operador, coincidirá con `Search Results`, `Results of Search`, `Search` y `Results`. Este operador admite hasta 100 palabras delimitadas por espacios. |
| **[!UICONTROL no contiene ninguno]** | Todos los elementos que coincidan con cualquier subcadena se excluirán de los resultados. Por ejemplo, si se especifica `Search Results` como el valor de este operador, se excluirían `Search Results`, `Results of Search`, `Search` y `Results`. Este operador admite hasta 100 palabras delimitadas por espacios. |
| **[!UICONTROL comienza con]** | Devuelve elementos que comienzan con el carácter o cadenas del valor especificado. |
| **[!UICONTROL no comienza con]** | Devuelve todos los elementos que no comienzan con los caracteres o cadenas del valor especificado. |
| **[!UICONTROL termina con]** | Devuelve elementos que terminan con el carácter o cadenas del valor especificado. |
| **[!UICONTROL no termina con]** | Devuelve todos los elementos que no terminan con los caracteres o cadenas del valor especificado. |
| **[!UICONTROL coincidencias]** | Devuelve elementos que coinciden exactamente con elementos en función de un determinado valor numérico o de cadena. Admite caracteres comodín que utilizan un asterisco (`*`). Este operador tiene distinción de mayúsculas y minúsculas. Por ejemplo:<ul><li>`a*e` coincide con `ae`, `abcde`, `adobe` y `a whole sentence`.</li><li>`adob*` coincide con `adobe`, `adobe analytics` y `adobo recipe`</li><li>`*dobe` coincide con `dobe`, `adobe` y `cute little dobe`.</li></ul> |
| **[!UICONTROL no coincide con]** | Se excluyen todos los elementos que coincidan con la cadena. Admite caracteres comodín que utilizan un asterisco (`*`). |
| **[!UICONTROL existe]** | Devuelve elementos si el valor no es nulo. |
| **[!UICONTROL no existe]** | Devuelve elementos si el valor no es nulo. |

## Operadores de recuento distinto

Puede segmentar un recuento distinto de elementos dentro de una dimensión. Por ejemplo, puede crear segmentos para personas que vieron más de 5 productos diferentes o visitas donde se vieron más de 5 páginas diferentes.

| Operador | Descripción |
| --- | --- |
| **[!UICONTROL es igual a]** | Devuelve elementos de dimensión cuya cantidad única es igual al valor introducido. |
| **[!UICONTROL no es igual a]** | Devuelve elementos de dimensión cuya cantidad única no es igual al valor introducido. |
| **[!UICONTROL es mayor que]** | Devuelve elementos de dimensión cuya cantidad única sea mayor que el valor introducido. |
| **[!UICONTROL es menor que]** | Devuelve elementos de dimensión cuya cantidad única sea menor que el valor introducido. |
| **[!UICONTROL es mayor o igual que]** | Devuelve elementos de dimensión cuya cantidad única sea mayor o igual que el valor introducido. |
| **[!UICONTROL es menor o igual que]** | Devuelve elementos de dimensión cuya cantidad única sea menor o igual que el valor introducido. |
