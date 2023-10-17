---
title: Formato de configuración de componentes
description: Configure el formato de una métrica.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 6945026bd452e1dabe90812f8d056f19aac71490
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 30%

---

# Formato de configuración de componentes

El formato le permite determinar cómo se muestra una métrica determinada.

![Configuración de formato](../assets/format-settings.png)

| Configuración | Descripción |
| --- | --- |
| **[!UICONTROL Formato]** | Permite especificar el formato de una métrica, como Decimal, Hora, Porcentaje o Moneda. |
| **[!UICONTROL Lugares decimales]** | No visible en los tipos de datos de esquema de enteros. Permite especificar el número de decimales que debe mostrar una métrica. |
| **[!UICONTROL Fecha]** | Permite determinar cómo desea que se muestre el campo de fecha y hora cuando se utiliza como dimensión en la creación de informes.  [Más información](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Fecha-hora]** | Permite determinar cómo desea que se muestre el campo de fecha y hora cuando se utiliza como dimensión en la creación de informes.  [Más información](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Moneda]** | Permite determinar en qué moneda desea que se muestre la métrica. Consulte [Moneda](#currency) para obtener más información. |
| **[!UICONTROL Mostrar tend ascendente como]** | Permite especificar si una tendencia al alza en esta métrica debe considerarse buena (verde) o mala (rojo). |
| **[!UICONTROL Valor verdadero]** y **[!UICONTROL Valor falso]** | Solo visible en los tipos de datos de esquema booleano. Permite personalizar la etiqueta del elemento de dimensión para los valores `true` y `false`. |

{style="table-layout:auto"}

## Moneda

Al seleccionar **[!UICONTROL Moneda]** como el [!UICONTROL Formato] para una métrica, puede determinar cómo mostrar y convertir monedas.

### Mostrar moneda

Para mostrar una moneda para una métrica:

1. Introduzca el número de **[!UICONTROL Cifras decimales]**.

1. Seleccione una divisa en la **[!UICONTROL Mostrar moneda en]** lista.


### Convertir y mostrar moneda

Para habilitar la conversión de una moneda para una o varias métricas:

- Configure la conexión de Customer Journey Analytics para que contenga al menos un conjunto de datos de evento que contenga una dimensión de código de moneda para cada evento que contenga una métrica de moneda. Esa dimensión de código de moneda utiliza un código de moneda alfabético que se ajusta a la variable [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) estándar para representar monedas. Estos valores deben estar en formato completo en mayúsculas, como USD para $, EUR para €, GBP para £.

   1. Seleccione la dimensión de uno de los conjuntos de datos que contiene los códigos de moneda. Por ejemplo, [!UICONTROL Código de divisa].

   1. Seleccionar **[!UICONTROL Código de divisa]** de la lista de dimensiones.

- Repita estos pasos en caso de que tenga más dimensiones que contengan códigos de moneda que desee utilizar para la conversión de moneda.

>[!NOTE]
>
>La métrica que seleccione para la conversión de moneda debe tener un tipo numérico (Double, Long, Integer, Short, Byte).


Para definir cómo convertir y mostrar una moneda para una métrica:

1. Introduzca el número de **[!UICONTROL Cifras decimales]**.

1. Seleccionar **[!UICONTROL Convertir concurrencia]**.

1. Seleccione la dimensión adecuada de la lista de dimensiones que contiene el campo de código de moneda.

1. Seleccione una divisa en la **[!UICONTROL Conversión y visualización de moneda en]** lista.

### Preguntas frecuentes 

+++ ¿Cómo se ejecuta la conversión de moneda?

Tras la creación del informe, el valor de la métrica y el código de moneda original se convierten a USD y, a continuación, a la moneda configurada para su visualización. Para esta conversión, se utilizan los tipos de cambio de moneda diarios, aplicables en el momento del evento.

+++


+++ ¿Hasta dónde se mantienen las tasas de conversión diarias?

¿Se han mantenido las tasas de conversión diarias durante los últimos cuatro años?

+++


+++ ¿Qué sucede si no tengo un campo de código de moneda como parte de mi esquema de datos actual?

Existen varias opciones para crear un nuevo campo de código de moneda, incluidas la preparación de datos, la Distiller de datos y los campos derivados. La preparación de datos sería ideal para nuevas implementaciones, ya que solo sería en adelante. Según la configuración de una organización, Data Distiller y los campos derivados se pueden utilizar para acceder a los valores de código de moneda históricamente.

+++

