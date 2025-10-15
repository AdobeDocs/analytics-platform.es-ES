---
description: Aprenda a utilizar los operadores del generador de segmentos para comparar y restringir valores.
title: Operadores
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 38%

---

# Operadores

El Generador de segmentos le permite comparar y restringir valores para componentes utilizando los operadores seleccionados. Existen tres categorías de operadores: [Estándar](#standard-operators), [Data Warehouse](#data-warehouse-operators) y [Recuento distinto](#distinct-count-operators).

Según el operador seleccionado:

* Puede introducir un valor.
* Puede introducir parte de un valor y seleccionarlo en un menú desplegable (si está disponible).
* Seleccione inmediatamente un valor del menú desplegable (si está disponible).

Cuando escribe un valor para un operador que valida valores disponibles, como **[!UICONTROL igual a]**, y el valor no coincide con los valores disponibles para el componente, verá un icono ![AlertRed](/help/assets/icons/AlertRed.svg). Puede seleccionar un valor del menú desplegable o presionar **[!UICONTROL _Intro_]** para escribir el valor.

![Segmento igual a](assets/segment-operator-equals.png)

## Comodines

El único carácter comodín admitido para los operadores que admiten caracteres comodín es el asterisco: `*`. Si necesita buscar el carácter &#42; específico, puede especificarlo con una barra invertida, como `\*`.

Por ejemplo, tiene un nombre de página denominado *Mi excelente producto*.

* La regla de segmento **[!UICONTROL Nombre de página]** **[!UICONTROL coincide con]** `* product` coincidirá con el nombre de página anterior.
* Sin embargo, la regla **[!UICONTROL Nombre de página]** **[!UICONTROL coincide]** `My \* product` coincide únicamente con el nombre de página *Mi * Producto*.

## Operadores estándar

| Operador | La dimensión, segmento o evento de métrica seleccionado... |
|--- |--- |
| **[!UICONTROL es igual que]** | Devuelve elementos que coinciden exactamente con un valor numérico o de cadena. Nota: Si usa caracteres comodín, use el operador **[!UICONTROL matches]**. |
| **[!UICONTROL no es igual a]** | Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido.  Nota: Si usa caracteres comodín, use el operador **[!UICONTROL no coincide con]**. |
| **[!UICONTROL es igual a cualquiera de]** | Devuelve elementos que coinciden exactamente con cualquier valor del campo de entrada (hasta 500 elementos). Por ejemplo, si se introduce `Search Results, Homepage` para la dimensión **[!UICONTROL Nombre de página]** con este operador, coincidirá con *Resultados de búsqueda* y *Página principal*, y se contará como 2 elementos. El campo de entrada para este operador está delimitado por comas. |
| **[!UICONTROL no es igual a ninguno de]** | Identifica los elementos que coinciden exactamente con cualquier valor del campo de entrada (hasta 500 elementos) y, a continuación, solo devuelve elementos sin estos valores. Por ejemplo, si se introduce `Search Results, Homepage` con este operador para la dimensión **[!UICONTROL Nombre de página]**, se identificarán *Resultados de búsqueda* y *Página principal* y, a continuación, se excluirán **8&rbrace; de los elementos devueltos.** Este ejemplo contaría como 2 elementos. El campo de entrada para este operador está delimitado por comas. |
| **[!UICONTROL contiene]** | Devuelve elementos que se comparan con las subcadenas de los valores introducidos. Por ejemplo, si la regla es **[!UICONTROL Nombre de página]** **[!UICONTROL contiene]** `Search`, entonces esta regla coincidirá con cualquier página que contenga la subcadena `Search`, incluidos *Resultados de búsqueda*, *Búsqueda* y *Búsquedas*. La cláusula “contiene” no distingue entre mayúsculas y minúsculas en Adobe Analytics, pero en Customer Journey Analytics sí. |
| **[!UICONTROL no contiene]** | Devuelve lo contrario a la regla **[!UICONTROL contains]**. En concreto, todos los elementos que coincidan con el valor introducido se excluirán de los valores introducidos. Por ejemplo, si la regla es **[!UICONTROL Nombre de página]** **[!UICONTROL no contiene]** `Search`, no coincidirá con ninguna página que contenga la subcadena `Search`, incluidos *Resultados de búsqueda*, *Búsqueda* y *Búsquedas*. Estos valores se excluirán de los resultados. |
| **[!UICONTROL contiene todo(a)]** | Devuelve elementos comparados con las subcadenas, incluidos valores múltiples unidos. Por ejemplo, si se escribe `Search Results` con este operador para la dimensión **[!UICONTROL Nombre de página]**, coincidirá con *Resultados de búsqueda* y *Resultados de la búsqueda*, pero no con *Búsqueda* ni con *Resultados* por separado. La regla coincidiría con *Search* y *Results* encontrados juntos. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| **[!UICONTROL no contiene todos(as) los/las]** | Identifica elementos comparados con subcadenas, incluidos valores múltiples unidos, y luego solo elementos devueltos sin estos valores. Por ejemplo, si se escribe `Search Results` con este operador para la dimensión **[!UICONTROL Nombre de página]**, se identificarán *Resultados de búsqueda* y *Resultados de la búsqueda* (pero no *Búsqueda* o *Resultados* individualmente) y después se excluirán estos elementos. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| **[!UICONTROL contiene cualquiera de]** | Devuelve elementos comparados con las subcadenas, incluidos valores múltiples unidos o identificados por separado. Por ejemplo, si se escribe `Search Results` con este operador, coincidirá con *Resultados de búsqueda*, *Resultados de la búsqueda*, *Búsqueda* y *Resultados*. Coincidirá con *Search* O *Results* que se encuentren juntos o por separado. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| **[!UICONTROL no contiene ninguno de]** | Identifica elementos en función de subcadenas y devuelve valores que no contienen estas subcadenas. Puede tener varios valores unidos o valores identificados independientemente. Por ejemplo, si se escribe `Search Results` para la dimensión **[!UICONTROL Nombre de página]**, coincidirá con *Resultado de búsqueda* s, *Resultados de la búsqueda*, *Búsqueda* y *Resultados*, donde *Búsqueda* o *Resultado* se encuentran juntos o por separado. Luego excluiría los elementos que contengan estas subcadenas. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| **[!UICONTROL comienza con]** | Devuelve elementos que comienzan con el valor de cadena introducido. |
| **[!UICONTROL no comienza con]** | Devuelve todos los elementos que no comienzan con el valor de cadena introducido. Esto es lo contrario al operador **[!UICONTROL starts with]**. |
| **[!UICONTROL termina con]** | Devuelve elementos que terminan con un valor de cadena ingresado. |
| **[!UICONTROL no termina con]** | Devuelve todos los elementos que no terminan con el valor de cadena introducido. Es el operador contrario a **[!UICONTROL termina con]**. |
| **[!UICONTROL coincidencias]** | Devuelve elementos que coinciden exactamente en función de un determinado valor numérico o de cadena. La cláusula **[!UICONTROL matches]** distingue entre mayúsculas y minúsculas en Adobe Analytics y en Customer Journey Analytics. **Nota**: use este operador al usar las características de [comodín](#wildcards) (globalización). Ejemplos de “globalización”:<ul><li>`a*e` coincidiría con `ae`, `abcde`, `adobe` y `a whole sentence`</li><li>`adob*` coincidiría con `adobe`, `adobe analytics` y `adobo recipe`</li><li>`*dobe` coincidiría con `dobe`, `adobe` y `cute little dobe`</li></ul> |
| **[!UICONTROL no coincide con]** | Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido. Nota: Use este operador cuando use las características de [comodín](#wildcards) (globalización). |
| **[!UICONTROL existe]** | Devuelve el número de elementos que existen. Por ejemplo, si evalúa la dimensión **[!UICONTROL Páginas no encontradas]** con el operador **[!UICONTROL exists]**, se devuelve el número de páginas con error que existen. |
| **[!UICONTROL no existe]** | Devuelve todos los elementos que no existen. Por ejemplo, si evalúa la dimensión **[!UICONTROL Páginas no encontradas]** con el operador **[!UICONTROL no existe]**, se devuelve el número de páginas donde no existió esta página con error. |

## operadores de Data Warehouse

| Operador | La dimensión, segmento o evento de métrica seleccionado... |
| --- | --- |
| **[!UICONTROL es menor que]** | Devuelve elementos cuyo recuento numérico sea menor que el valor introducido. |
| **[!UICONTROL es menor o igual que]** | Devuelve elementos cuyo recuento numérico sea menor o igual que el valor introducido. |
| **[!UICONTROL es mayor que]** | Devuelve elementos cuyo recuento numérico sea mayor que el valor introducido. |
| **[!UICONTROL es mayor o igual que]** | Devuelve elementos cuyo recuento numérico sea mayor o igual que el valor introducido. |

## Operadores de recuento distinto

Puede segmentar un recuento distinto de elementos dentro de una dimensión. Ejemplos: *Visitantes que vieron más de 5 productos diferentes*, o *Visitas donde se vieron más de 5 páginas diferentes*.

| Operador | La dimensión, segmento o evento de métrica seleccionado... |
| --- | --- |
| **[!UICONTROL es igual que]** | Devuelve elementos de dimensión cuya cantidad única es igual al valor introducido. |
| **[!UICONTROL no es igual a]** | Devuelve elementos de dimensión cuya cantidad única no es igual al valor introducido. |
| **[!UICONTROL es mayor que]** | Devuelve elementos de dimensión cuya cantidad única sea mayor que el valor introducido. |
| **[!UICONTROL es menor que]** | Devuelve elementos de dimensión cuya cantidad única sea menor que el valor introducido. |
| **[!UICONTROL es mayor o igual que]** | Devuelve elementos de dimensión cuya cantidad única sea mayor o igual que el valor introducido. |
| **[!UICONTROL es menor o igual que]** | Devuelve elementos de dimensión cuya cantidad única sea menor o igual que el valor introducido. |


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Recuentos distintos de dimensiones](https://video.tv.adobe.com/v/27257?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]
