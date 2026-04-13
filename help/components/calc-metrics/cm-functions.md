---
title: Funciones básicas
description: Obtenga información sobre las funciones básicas de las métricas calculadas.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 211f0411d0bf70288cbd46bb219fce7ae99fe03d
workflow-type: tm+mt
source-wordcount: '3599'
ht-degree: 48%

---

# Funciones básicas


El [Creador de métricas calculadas](cm-workflow/cm-build-metrics.md) permite aplicar funciones estadísticas y matemáticas. Este artículo recoge una lista alfabética de las funciones y sus definiciones.

>[!NOTE]
>
>Cuando [!DNL metric] se identifica como un argumento en una función, también se permiten otras expresiones de métricas. Por ejemplo, [COLUMN MAXIMUM(metrics)](#column-maximum) también permite [COLUMN MAXIMUM(PageViews + Sessions)](#column-maximum).



## Funciones de tabla en comparación con funciones de fila

Una función de tabla es aquella en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es aquella en la que el resultado es diferente para cada fila de la tabla.

Cuando sea aplicable y relevante, una función se anota con el tipo de función: [!BADGE Tabla]{type="Neutral"} o [!BADGE Fila]{type="Neutral"}

## ¿Qué significa el parámetro include-zeros?

Indica si se incluyen ceros en el cálculo. En algunas ocasiones cero significa *nada*, pero en ocasiones es importante.

Por ejemplo, si tiene una métrica Ingresos y, a continuación, agrega una métrica Vistas de página al informe, de repente hay más filas para sus ingresos, todas con valor de cero. Probablemente, no quiera que esa métrica adicional afecte a ninguna **[MEDIA](cm-functions.md#mean)**, **[MÍNIMO DE FILA](cm-functions.md#row-min)**, **[CUARTIL](cm-functions.md#quartile)** y más cálculos que tenga en la columna de ingresos. En este caso, comprobaría el parámetro `include-zeros`.

Un escenario alternativo es que tiene dos métricas de interés y una tiene un promedio o un mínimo más alto porque algunas de las filas son ceros. En ese caso, puede optar por no marcar el parámetro para incluir ceros



## Valor absoluto {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="Valor absoluto"
>abstract="Devuelve el valor absoluto de un número. El valor absoluto de un número es el número con un valor positivo."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL VALOR ABSOLUTO(métrica)]**

[!BADGE Fila]{type="Neutral"} Devuelve el valor absoluto de un número. El valor absoluto de un número es el número con un valor positivo.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea calcular el valor absoluto. |

**Caso de uso**: Asegúrese de que todos los resultados sean positivos al analizar métricas que puedan producir valores negativos, como diferencias de ingresos o cambios de porcentaje. Esto ayuda a centrarse en la magnitud del cambio sin tener en cuenta la dirección.

**En el Creador de métricas calculadas**: ajuste la métrica o expresión en la función **Valor absoluto**, por ejemplo: **Valor absoluto**(Ingresos actuales - Ingresos anteriores). Esto convierte cualquier diferencia negativa en valores positivos.

>[!TIP]
>
>Utilice esto para medir diferencias absolutas entre dos períodos de tiempo o segmentos, independientemente de si el rendimiento ha aumentado o disminuido.
>

## Máximo de columna {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="Máximo de columna"
>abstract="Devuelve el mayor valor en un conjunto de elementos de una dimensión para una columna de métrica. MAXV se evalúa verticalmente dentro de una sola columna (métrica) entre elementos de dimensión."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MÁXIMO DE COLUMNA(métrica, include_zeros)]**

Devuelve el mayor valor en un conjunto de elementos de una dimensión para una columna de métrica. MAXV se evalúa verticalmente dentro de una sola columna (métrica) entre elementos de dimensión.

| Argumento | Descripción |
|---|---|
| métrica | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: identifique el valor más alto dentro de un desglose, como el día con la mayor cantidad de visitas o el producto con los ingresos más altos. Esto ayuda a resaltar el rendimiento máximo entre categorías.

**En el Creador de métricas calculadas**: aplique **Máximo de columna** a una métrica como *Ingresos* o *Sesiones* al desglosar por *Día* o *Producto*. La función devuelve el valor mayor de esa columna para cada fila.

>[!TIP]
>
>Use una instrucción [IF](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if) como **IF**(*Ingresos* = **Máximo de columna***(Ingresos*), 1, 0) para resaltar el elemento de mayor rendimiento en el desglose.
>

## Mínimo de columna {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="Mínimo de columna"
>abstract="Devuelve el valor más pequeño en un conjunto de elementos de una dimensión para una columna de métrica. MINV se evalúa verticalmente dentro de una sola columna (métrica) entre elementos de dimensión."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MÍNIMO DE COLUMNA(métrica, include_zeros)]**

Devuelve el valor más pequeño en un conjunto de elementos de una dimensión para una columna de métrica. MINV se evalúa verticalmente dentro de una sola columna (métrica) entre elementos de dimensión.

| Argumento | Descripción |
|---|---|
| métrica | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: identifique el valor de menor rendimiento dentro de un desglose, como la campaña con la menor cantidad de conversiones o el día con la menor cantidad de ingresos. Esto ayuda a que aparezcan rápidamente segmentos de bajo rendimiento.

**En el Creador de métricas calculadas**: aplique **Mínimo de columna** a una métrica como *Ingresos* o *Tasa de conversión* al desglosar por *Campaña* o *Día*. La función devuelve el valor más pequeño de esa columna para cada fila.

>[!TIP]
>
>Use una instrucción [IF](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if) como **IF**(*Ingresos* = **Mínimo de columna***(Ingresos*), 1, 0) para resaltar el elemento con menor rendimiento en su desglose.
>


## Suma de columna {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="Suma de columna"
>abstract="Suma todos los valores numéricos de una métrica dentro de una columna (entre los elementos de una dimensión)."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL SUMA DE COLUMNA(métrica)]**

Suma todos los valores numéricos de una métrica dentro de una columna (entre los elementos de una dimensión).

| Argumento | Descripción |
|---|---|
| métrica | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |

**Caso de uso**: calcule el total de todos los valores dentro de un desglose, como los ingresos totales en todos los productos o las visitas totales en todos los días. Esto resulta útil cuando necesita un total general para compararlo con valores de fila individuales.

**En el Creador de métricas calculadas**: aplique **Suma de columna** a una métrica como *Ingresos* o *Sesiones* al desglosar por *Producto* o *Día*. La función devuelve el total de todos los valores de esa columna para cada fila.

>[!TIP]
>
>Utilícelo cuando necesite una referencia al total general para calcular acciones o porcentajes del rendimiento total.
>


## Recuento {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="Recuento"
>abstract="Devuelve un número, o recuento, de valores distintos de cero para una métrica dentro de una columna (el número de elementos únicos incluidos dentro de una dimensión)."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECUENTO(métrica)]**

[!BADGE Tabla]{type="Neutral"}Devuelve un número, o recuento, de valores distintos de cero para una métrica dentro de una columna (el número de elementos únicos notificados dentro de una dimensión).

| Argumento | Descripción |
|---|---|
| métrica | La métrica que desea contar. |

**Caso de uso**: cuente el número de puntos de datos incluidos en un cálculo, como el número de días en un intervalo de fechas o el número de productos en un desglose. Esto resulta útil cuando necesita saber cuántos elementos contribuyen a un valor agregado.

**En el Creador de métricas calculadas**: aplique **Count** a una métrica como *Sessions* o *Revenue* para devolver el número total de filas (o puntos de datos) incluidos en el desglose o intervalo de fechas actual.

>[!TIP]
>
>Use junto con **Suma de columna** para calcular promedios manualmente (por ejemplo, **Suma de columna**(*Ingresos*) / **Recuento**(Ingresos)).
>

## Exponente {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="Exponente"
>abstract="Devuelve e elevado a la potencia de un número determinado. La constante e es igual a 2,71828182845904, la base del logaritmo natural. EXPONENTE es el inverso de LN, el logaritmo natural de un número."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTE(métrica)]**

[!BADGE Fila]{type="Neutral"} Devuelve *e* elevado a la potencia de un número determinado. La constante *e* es igual a 2,71828182845904, la base del logaritmo natural. EXPONENTE es el inverso de LN, el logaritmo natural de un número.

| Argumento | Descripción |
|---|---|
| métrica | Exponente aplicado a la base *e*. |

**Caso de uso**: eleva a *e* a la potencia de un número o métrica determinados. Esto resulta útil para modelar las tendencias de crecimiento o escalar una métrica exponencialmente.

**En el Creador de métricas calculadas**: use **Exponente** con una métrica. Por ejemplo: **Exponente**(*Sesiones*) eleva *e* al poder de la métrica *Sesiones*.

>[!TIP]
>
>Combínelo con **Logarithm** para obtener modelos avanzados o para suavizar datos muy variables al comparar patrones de crecimiento.
>


## Media {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="Media"
>abstract="Devuelve la media aritmética, o el promedio, de una métrica en una columna."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIA(métrica, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Devuelve la media aritmética, o el promedio, de una métrica en una columna.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea calcular la media. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: calcule el promedio aritmético de un conjunto de valores, como el promedio de ingresos diarios o el número promedio de visitas por campaña. Esto ayuda a establecer una línea de base para comparar valores individuales dentro de un conjunto de datos.

**En el Creador de métricas calculadas**: aplique **Media** a una métrica como *Ingresos* o *Sesiones* para devolver el valor promedio en todos los puntos de datos del desglose o intervalo de fechas seleccionado.

>[!TIP]
>
>Úselo para comprender las tendencias generales de rendimiento o combínelo con **Desviación estándar** para medir la consistencia en torno al promedio.
>

## Mediana {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="Mediana"
>abstract="Devuelve la mediana de una métrica en una columna. La mediana es el número situado en medio de un conjunto de números. Es decir, la mitad de los números tienen valores mayores o iguales a la mediana y la mitad son menores o iguales a la mediana."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIANA(métrica, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}Devuelve la mediana de una métrica en una columna. La mediana es el número situado en medio de un conjunto de números. Es decir, la mitad de los números tienen valores mayores o iguales a la mediana y la mitad son menores o iguales a la mediana.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea calcular la mediana. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: identifique el valor medio de un conjunto de datos, como la mediana de ingresos diarios o la mediana de vistas de página por visita. Esto resulta útil cuando desea reducir el impacto de los periféricos y ver la tendencia central de los datos.

**En el Creador de métricas calculadas**: aplique la mediana a una métrica como Ingresos o Vistas de página para devolver el valor de punto medio en todos los puntos de datos del desglose o intervalo de fechas seleccionado.

>[!TIP]
>
>Use en lugar de **Media** cuando sus datos contengan máximos o mínimos extremos que puedan distorsionar el promedio.
>


## Módulo {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="Módulo"
>abstract="Devuelve el resto tras dividir x por y utilizando la división euclídea. "

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MÓDULO(metric_X, metric_Y)]**

Devuelve el resto tras dividir x por y utilizando la división euclídea.

| Argumento | Descripción |
|---|---|
| metric_X | La primera métrica que le gustaría dividir. |
| metric_Y | La segunda métrica que le gustaría dividir. |

**Caso de uso**: devuelva el resto después de dividir un número por otro. Esto puede resultar útil para patrones cíclicos o repetidos, como identificar cada enésimo día o campaña en una secuencia.

**En el Creador de métricas calculadas**: use **Módulo** con dos entradas numéricas. Por ejemplo: **Módulo**(*Número de día*, 7) devuelve el resto después de dividir el número de día por siete, lo que puede ayudar a agrupar los datos por semana.

>[!TIP]
>
>Combínelos con la lógica condicional para resaltar intervalos recurrentes o para segmentar datos en función de ciclos repetidos.
>

### Más ejemplos

El valor devuelto tiene el mismo signo que la entrada (o es cero).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

Para obtener siempre un número positivo, utilice

```
MODULO(MODULO(x,y)+y,y)
```

## Percentil {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="Percentil"
>abstract="Devuelve el percentil número n, que es un valor entre 0 y 100. Cuando n &lt; 0, la función utiliza cero. Cuando n > 100, la función devuelve 100."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTIL(métrica, k, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}Devuelve el percentil número n, que es un valor entre 0 y 100. Cuando n &lt; 0, la función utiliza cero. Cuando n > 100, la función devuelve 100.

| Argumento | Descripción |
|---|---|
| métrica | El valor en porcentaje dentro del rango de 0 a 100, ambos incluidos. |
| k | La columna de métrica que define la posición relativa. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: identifique el valor por debajo del cual cae un porcentaje determinado de puntos de datos, como el percentil 90 de ingresos diarios o vistas de página. Esto ayuda a medir la distribución y detectar periféricos de alto rendimiento.

**En el Creador de métricas calculadas**: aplique el **Percentil** a una métrica como *Ingresos* o *Sesiones*, y especifique el valor de percentil deseado (por ejemplo, **Percentil**(*Ingresos*, 90)). El resultado muestra el umbral en el que el 90 % de los puntos de datos se encuentran por debajo.

>[!TIP]
>
>Se utiliza para establecer puntos de referencia de rendimiento o para filtrar por los días, las campañas o los productos de mejor rendimiento.
>

## Operador de potencia {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="Operador de potencia"
>abstract="Devuelve x elevado a la potencia y."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL OPERADOR DE ENERGÍA(metric_X, metrix_Y)]**

Devuelve x elevado a la potencia y.

| Argumento | Descripción |
|---|---|
| metric_X | La métrica que desea elevar a la potencia metric_Y. |
| metric_Y | La potencia a la que le gustaría aumentar metric_X. |

**Caso de uso**: eleve un número o métrica a la potencia de otro, por ejemplo, al cuadrado de un valor o al aplicar un peso exponencial. Esto resulta útil para modelar el crecimiento, escalar valores o realizar transformaciones matemáticas avanzadas.

**En el Creador de métricas calculadas**: use **Operador avanzado** entre dos valores numéricos o métricas. Por ejemplo: *Ingresos* ^ 2 eleva el valor de *Ingresos* a la segunda potencia.

>[!TIP]
>
>Similar a la función **Exponente** pero expresada como operador matemático, lo que permite fórmulas más compactas dentro de las métricas calculadas.
>

## Cuartil {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="Cuartil"
>abstract="Devuelve el cuartil de los valores de una métrica. Por ejemplo, los cuartiles se pueden utilizar para encontrar el 25 % de productos que genera la mayor cantidad de ingresos."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CUARTIL(métrica, cuartil, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}Devuelve el cuartil de los valores de una métrica. Por ejemplo, los cuartiles se pueden utilizar para encontrar el primer 25 % de los productos que generan los mayores ingresos. [COLUMNA MÍNIMA](#column-minimum), [MEDIANA](#median) y [COLUMNA MÁXIMA](#column-maximum) devuelven el mismo valor que [CUARTIL](#quartile) cuando el cuartil es igual a `0` (cero), `2` y `4`, respectivamente.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea el valor de cuartil. |
| cuartil | Indica qué valor de cuartil se devolverá. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: divida un conjunto de datos en cuatro partes iguales para comprender cómo se distribuyen los valores, como identificar el 25 % superior de días por ingresos o visitas. Esto ayuda a segmentar el rendimiento en grupos clasificados para realizar una comparación más detallada.

**En el Creador de métricas calculadas**: aplique **Quartile** a una métrica como *Ingresos* o *Sesiones*, y especifique qué cuartil se devolverá (por ejemplo, **Cuartil**(*Ingresos*, 3) para encontrar el umbral del tercer cuartil o el 25 % superior).

>[!TIP]
>
>Se utiliza para agrupar valores en niveles de rendimiento como campañas o productos de bajo, medio y alto rendimiento.
>

## Redondeo {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="Redondeo"
>abstract="Redondear sin un parámetro de *número* es lo mismo que redondear con un parámetro de *número* de 0, es decir, redondear al número entero más próximo.  Con un parámetro de *número*, REDONDEAR devuelve los dígitos de *número* a la derecha del decimal. Si *número* es negativo, devuelve ceros a la izquierda del decimal."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REDONDEO(métrica, número)]**

Redondear sin un parámetro de *número* es lo mismo que redondear con un parámetro de *número* de 0, es decir, redondear al número entero más próximo.  Con un parámetro de *número*, REDONDEAR devuelve los dígitos de *número* a la derecha del decimal. Si *número* es negativo, devuelve ceros a la izquierda del decimal.

| Argumento | Descripción |
|---|---|
| métrica | La métrica que desee redondear. |
| número | Cuántos dígitos a la derecha del decimal se devolverán. (Si es negativo devuelve ceros a la izquierda del decimal). |

**Caso de uso**: Simplifique los resultados numéricos redondeándolos a un número determinado de decimales. Esto resulta útil para crear visualizaciones más limpias o para facilitar la lectura de las métricas calculadas en los informes.

**En el Creador de métricas calculadas**: aplique **Redondeo** a una métrica o expresión y especifique el número de decimales. Por ejemplo: **Redondeo**(*Tasa de conversión*, 2) redondea el valor a dos decimales.

>[!TIP]
>
>Se utiliza para estandarizar el formato de las métricas en los informes, especialmente cuando se muestran porcentajes o valores de moneda.
>

### Más ejemplos

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## Recuento de filas {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="Recuento de filas"
>abstract="Devuelve el recuento de filas de una columna en concreto (el número de elementos únicos registrados en una dimensión). *Se han superado los límites* se cuenta como 1."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECUENTO DE FILAS()]**

Devuelve el recuento de filas de una columna en concreto (el número de elementos únicos registrados en una dimensión). *Se han superado los límites* se cuenta como 1.

**Caso de uso**: Cuenta el número total de filas devueltas en un desglose o conjunto de datos, como el número de días, campañas o productos incluidos en un informe. Esto ayuda a comprender cuántos elementos contribuyen al análisis.

**En el Creador de métricas calculadas**: Aplique **Recuento de filas** para devolver el número total de filas en el desglose o segmento actual. Por ejemplo, al ver *Ingresos* por *Producto*, **Recuento de filas** devuelve el número de productos mostrados.

>[!TIP]
>
>Se usa con otras funciones como **Suma de columna** para calcular promedios manualmente (por ejemplo, **Suma de columna**(*Ingresos*) / **Recuento de fila**()).
>

## Máximo de fila {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="Máximo de fila"
>abstract="Número máximo de las columnas de cada fila."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MAX DE FILA(métrica, include_zeros)]**

Número máximo de las columnas de cada fila.

| Argumento | Descripción |
|---|---|
| métrica | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: identifique el valor más alto de todas las métricas de una sola fila; por ejemplo, determine qué métrica (por ejemplo, *Ingresos*, *Pedidos* o *Sesiones*) tiene el valor más alto para un día o segmento específico. Esto ayuda a resaltar qué posibles clientes de métrica dentro de cada fila de datos.

**En el Creador de métricas calculadas**: aplique **Máximo de fila** cuando se incluyan varias métricas en una métrica calculada. Por ejemplo: **Máximo de fila**(*Ingresos*, *Pedidos*, *Sesiones*) devuelve el valor más alto entre esas métricas para cada fila.

>[!TIP]
>
>Utilice para comparar métricas relacionadas una al lado de la otra e identificar cuál contribuye más al rendimiento dentro de cada fila.
>

## Mínimo de fila {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="Mínimo de fila"
>abstract="Número mínimo de las columnas de cada fila."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL FILA MÍN(métrica, include_zeros)]**

Número mínimo de las columnas de cada fila.

| Argumento | Descripción |
|---|---|
| métrica | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: identifique el valor más bajo de todas las métricas de una sola fila, como por ejemplo qué métrica (por ejemplo, *Ingresos*, *Pedidos* o *Sesiones*) tiene el valor más pequeño para un día o segmento en particular. Esto ayuda a identificar la métrica de menor rendimiento dentro de cada fila de datos.

**En el Creador de métricas calculadas**: aplique **Mínimo de fila** al comparar varias métricas. Por ejemplo: **Mínimo de fila**(*Ingresos*, *Pedidos*, *Sesiones*) devuelve el valor más pequeño entre esas métricas para cada fila.

>[!TIP]
>
>Combinar con Máximo de fila para calcular intervalos de rendimiento o resaltar métricas de bajo rendimiento en una comparación en paralelo.
>

## Suma de fila {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="Suma de fila"
>abstract="Suma de las columnas de cada fila."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL SUMA DE FILA(métrica, include_zeros)]**

Suma de las columnas de cada fila.

| Argumento | Descripción |
|---|---|
| métrica | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |

**Caso de uso**: suma los valores de varias métricas en una sola fila, como sumar *Ingresos* e *Impuestos* para calcular el valor total de la transacción o combinar *Sesiones* de diferentes fuentes. Esto ayuda a consolidar las métricas relacionadas en un total.

**En el Creador de métricas calculadas**: aplique **Suma de fila** para combinar varias métricas. Por ejemplo: **Suma de fila**(*Ingresos*, *Impuestos*) agrega esas dos métricas a cada fila del desglose.

>[!TIP]
>
>Se utiliza para crear totales combinados o para agrupar indicadores de rendimiento relacionados en una sola métrica calculada.
>

## Raíz cuadrada {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="Raíz cuadrada"
>abstract="Devuelve la raíz cuadrada positiva de un número. La raíz cuadrada de un número es el valor de ese número elevado a la potencia de 1/2."

<!-- markdownlint-enable MD034 -->


![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RAÍZ CUADRADA(métrica, include_zeros)]**

[!BADGE Fila]{type="Neutral"} Devuelve la raíz cuadrada positiva de un número. La raíz cuadrada de un número es el valor de ese número elevado a la potencia de 1/2.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea la raíz cuadrada. |

**Caso de uso**: devuelve la raíz cuadrada de un número o métrica, como la búsqueda de la raíz de la varianza al calcular la desviación estándar o al normalizar valores en un conjunto de datos. Esto resulta útil para realizar cálculos estadísticos o de transformación de datos avanzados.

**En el Creador de métricas calculadas**: aplique **Raíz cuadrada** a una métrica o expresión. Por ejemplo: **Raíz cuadrada**(Varianza(*Ingresos*)) devuelve la desviación estándar de *Ingresos*.

>[!TIP]
>
>Utilícelo cuando necesite escalar las métricas proporcionalmente o para admitir otras funciones estadísticas que dependan de los valores raíz.
>

## Desviación estándar {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="Desviación estándar"
>abstract="Devuelve la desviación estándar, o la raíz cuadrada de la varianza, de una muestra de datos de una población."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL DESVIACIÓN ESTÁNDAR(métrica, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Devuelve la desviación estándar, o la raíz cuadrada de la varianza, basada en una muestra de datos de una población.

| Argumento | Descripción |
|---|---|
| | La métrica para la cual desea la desviación estándar. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: mida cuántos valores varían del promedio, por ejemplo, evaluando la consistencia de los ingresos diarios o las visitas con el paso del tiempo. Esto ayuda a identificar volatilidad, estabilidad o fluctuaciones inusuales en el rendimiento.

**En el Creador de métricas calculadas**: aplique **Desviación estándar** a una métrica como *Ingresos* o *Sesiones* para calcular la propagación de valores dentro del desglose o intervalo de fechas seleccionado. Por ejemplo: **Desviación estándar**(*Ingresos*) muestra cuánto se desvían los ingresos diarios de la media.

>[!TIP]
>
>Úselo con *Media* para detectar anomalías o comparar la coherencia del rendimiento en campañas, productos o segmentos.
>

## Varianza {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="Varianza"
>abstract="Devuelve la varianza de una muestra de datos de una población."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANZA(métrica, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Devuelve la varianza basada en una muestra de datos de una población.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea la varianza. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

**Caso de uso**: mida hasta qué punto los valores de un conjunto de datos se extienden más allá de la media, como por ejemplo el análisis de cuánto varían los ingresos diarios o la duración de la sesión con el paso del tiempo. Esto ayuda a cuantificar el grado de coherencia o fluctuación del rendimiento.

**En el Creador de métricas calculadas**: aplique **Varianza** a una métrica como *Ingresos* o *Tiempo empleado por visita* para calcular la desviación cuadrada promedio de la media. Por ejemplo: **Varianza**(*Ingresos*) muestra cuánto difieren los valores de ingresos del promedio en el rango seleccionado.

>[!TIP]
>
>Úselo con **Desviación estándar** para comprender mejor la variabilidad de los datos e identificar áreas de rendimiento impredecible.
>

La ecuación de VARIANZA es:

![](assets/variance_eq.png){width="100"}

Donde *x* es la media de la muestra, [MEDIA(*métrica*)](#mean), y *n* es el tamaño de la muestra.


Para calcular una varianza, se considera una columna entera de números. A partir de una lista de números, calcule primero el promedio. Cuando tenga el promedio, examine cada entrada y realice lo siguiente:

1. Reste el promedio del número.

1. Multiplique el resultado por sí mismo.

1. Súmelo al total.

Cuando repita la operación sobre toda la columna, obtendrá un total único. A continuación, divida ese total por el número de elementos de la columna. Ese número es la variación de la columna. Es un solo número. Sin embargo, se muestra como una columna de números.

En el ejemplo de la siguiente columna de tres elementos:

| columna |
|:---:|
| 1 |
| 2 |
| 3 |

El promedio de esta columna es 2. La varianza de la columna es ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3.

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers-that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->