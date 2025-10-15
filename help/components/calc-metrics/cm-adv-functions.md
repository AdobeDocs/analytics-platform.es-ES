---
title: Funciones avanzadas
description: Obtenga información sobre las funciones avanzadas de métricas calculadas.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '5241'
ht-degree: 98%

---

# Funciones avanzadas

El [Creador de métricas calculadas](cm-workflow/cm-build-metrics.md) permite aplicar funciones estadísticas y matemáticas. En este artículo se describe una lista alfabética de las funciones y sus definiciones.

Para obtener acceso a estas funciones, seleccione **[!UICONTROL Mostrar todo]** debajo de la lista ![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL Funciones]** en el panel Componentes. Desplácese hacia abajo para ver la lista de **[!UICONTROL Funciones avanzadas]**.

## Funciones de tabla en comparación con funciones de fila

Una función de tabla es aquella en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es aquella en la que el resultado es diferente para cada fila de la tabla.

Cuando sea aplicable y relevante, una función se anota con el tipo de función: [!BADGE Tabla]{type="Neutral"} o [!BADGE Fila]{type="Neutral"}

## ¿Qué significa el parámetro include-zeros?

Indica si se incluyen ceros en el cálculo. En algunas ocasiones cero significa *nada*, pero en ocasiones es importante.

Por ejemplo, si tiene una métrica Ingresos y, a continuación, agrega una métrica Vistas de página al informe, de repente hay más filas para sus ingresos, todas con valor de cero. Probablemente, no quiera que esa métrica adicional afecte a ninguna **[MEDIA](cm-functions.md#mean)**, **[MÍNIMO DE FILA](cm-functions.md#row-min)**, **[CUARTIL](cm-functions.md#quartile)** y más cálculos que tenga en la columna de ingresos. En este caso, comprobaría el parámetro `include-zeros`.

Un escenario alternativo es que tiene dos métricas de interés y una tiene un promedio o un mínimo más alto porque algunas de las filas son ceros. En ese caso, puede optar por no marcar el parámetro para incluir ceros


## Y {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-and"
>title="Y"
>abstract="Conjunción. No es igual a cero se considera verdadero y es igual a cero se considera falso. El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**

Conjunción. No es igual a cero se considera verdadero y es igual a cero se considera falso. El resultado es 0 (falso) o 1 (verdadero).

| Argumento | Descripción |
|---|---|
| logical_test | Requiere al menos un parámetro, pero puede tomar cualquier número de métricas como parámetros. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE |


## Recuento aproximado distinto {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-distinct-metric"
>title="Recuento aproximado distinto"
>abstract="Devuelve el recuento aproximado de elementos de dimensión independientes para la dimensión seleccionada."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT (dimension)]**


Devuelve el recuento aproximado distinto de elementos de dimensión para la dimensión seleccionada.


| Argumento | Descripción |
|---|---|
| dimensión | Dimensión para la que desea calcular el recuento de elementos distintos aproximado |

### Ejemplo

Un caso de uso común para esta función es cuando desea obtener un número aproximado de clientes.



## Arcocoseno {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-acos"
>title="Arcocoseno"
>abstract="Devuelve el arcocoseno, o la inversa del coseno, de una métrica. El arcocoseno es el ángulo cuyo coseno es el número. El ángulo devuelto se indica en radianes en el intervalo de 0 (cero) a pi. Si desea convertir el resultado de radianes a grados, multiplíquelo por 180/PI()."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE Fila]{type="Neutral"} Devuelve el arcocoseno o la inversa del coseno de una métrica. El arcocoseno es el ángulo cuyo coseno es el número. El ángulo devuelto se indica en radianes en el intervalo de 0 (cero) a pi. Si desea convertir el resultado de radianes a grados, multiplíquelo por 180/PI().


| Argumento | Descripción |
|---|---|
| métrica | El coseno del ángulo deseado de -1 a 1 |



## Arcoseno {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-asin"
>title="Arcoseno"
>abstract="Devuelve el arcoseno, o seno inverso, de un número. El arcoseno es el ángulo cuyo seno es un número. El ángulo devuelto se indica en radianes en el intervalo -pi/2 a pi/2. Para expresar el arcoseno en grados, multiplique el resultado por 180/PI()"

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE Fila]{type="Neutral"} Devuelve el arcoseno o la inversa del seno de un número. El arcoseno es el ángulo cuyo seno es un número. El ángulo devuelto se indica en radianes en el intervalo -pi/2 a pi/2. Para expresar el arcoseno en grados, multiplique el resultado por 180/PI().


| Argumento | Descripción |
|---|---|
| métrica | El seno del ángulo deseado de -1 a 1 |



## Arcotangente {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-atan"
>title="Arcotangente"
>abstract="Devuelve el arcotangente, o tangente inversa, de un número. El arcotangente es el ángulo cuya tangente es un número. El ángulo devuelto se indica en radianes en el intervalo -pi/2 a pi/2. Para expresar el arcotangente en grados, multiplique el resultado por 180/PI()."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE Fila]{type="Neutral"} Devuelve el arcotangente o la inversa de la tangente de un número. El arcotangente es el ángulo cuya tangente es un número. El ángulo devuelto se indica en radianes en el intervalo -pi/2 a pi/2. Para expresar el arcotangente en grados, multiplique el resultado por 180/PI().


| Argumento | Descripción |
|---|---|
| métrica | La tangente del ángulo deseado de -1 a 1 |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-t"
>title="Cdf-T"
>abstract="Devuelve la probabilidad de que una variable aleatoria con una distribución de estudiante t con n grados de libertad tenga una puntuación z inferior a col."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**

Devuelve la probabilidad de que una variable aleatoria con una distribución de estudiante t con n grados de libertad tenga una puntuación z inferior a col.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la que desea la función de distribución acumulativa de la distribución t de estudiante |
| number | Los grados de libertad para la función de distribución acumulativa de la distribución t de estudiante |

### Ejemplo

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z {#cdf-z}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-z"
>title="Cdf-Z"
>abstract="Devuelve la probabilidad de que una variable aleatoria con una distribución normal tenga una puntuación z menor que el valor de col."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**

Devuelve la probabilidad de que una variable aleatoria con una distribución normal tenga una puntuación z menor que el valor de col.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea la función de distribución acumulativa de la distribución normal estándar |

### Ejemplos

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Límite superior {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ceil"
>title="Límite superior"
>abstract="Devuelve el menor entero igual o mayor que un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe para los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula LÍMITE SUPERIOR (Ingresos) para redondear hacia arriba al dólar más próximo o 570 $."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**

[!BADGE Fila]{type="Neutral"} Devuelve el menor entero igual o mayor que un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe para los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula LÍMITE SUPERIOR (Ingresos) para redondear hacia arriba al dólar más próximo o 570 $.

| Argumento | Descripción |
|---|---|
| métrica | La métrica que desea redondear |


## Confianza {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence"
>title="Confianza"
>abstract="Calcule la confianza válida en cualquier momento utilizando el método WASKR como se describe en [Teoría del límite central uniforme en el tiempo y secuencias de confianza asintótica](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold]**

Calcule la confianza válida en cualquier momento utilizando el método WASKR como se describe en [Teoría del límite central uniforme en el tiempo y secuencias de confianza asintótica](https://arxiv.org/pdf/2103.06476).

La confianza es una medida probabilística del grado de evidencia de que una variante determinada sea la misma que la variante de control. Una mayor confianza indica menos evidencia para el supuesto de que la variante de control y la que no es de control tienen un rendimiento igual.

| Argumento | Descripción |
| --- | --- |
| normalizing-container | La base (Personas, Sesiones o Eventos) en la que se ejecutará una prueba. |
| success-metric | La métrica o métricas con las que un usuario compara variantes. |
| control | La variante con la que se comparan todas las demás variantes del experimento. Introduzca el nombre del elemento de dimensión de variante de control. |
| significance-threshold | El umbral en esta función se establece en un 95 % de forma predeterminada. |


## Confianza (inferior) {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lower-individual-confidence-sequence"
>title="Confianza (inferior)"
>abstract="Calcule la confianza válida en cualquier momento **inferior** utilizando el método WASKR como se describe en [Teoría del límite central uniforme en el tiempo y secuencias de confianza asintótica](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold]**

Calcule la confianza válida en cualquier momento **inferior** utilizando el método WASKR como se describe en [Teoría del límite central uniforme en el tiempo y secuencias de confianza asintótica](https://arxiv.org/pdf/2103.06476).

La confianza es una medida probabilística del grado de evidencia de que una variante determinada sea la misma que la variante de control. Una mayor confianza indica menos evidencia para el supuesto de que la variante de control y la que no es de control tienen un rendimiento igual.

| Argumento | Descripción |
| --- | --- |
| normalizing-container | La base (Personas, Sesiones o Eventos) en la que se ejecutará una prueba. |
| success-metric | La métrica o métricas con las que un usuario compara variantes. |
| control | La variante con la que se comparan todas las demás variantes del experimento. Introduzca el nombre del elemento de dimensión de variante de control. |
| significance-threshold | El umbral en esta función se establece en un 95 % de forma predeterminada. |

## Confianza (superior) {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-upper-individual-confidence-sequence"
>title="Confianza (superior)"
>abstract="Calcule la confianza válida en cualquier momento **superior** utilizando el método WASKR como se describe en [Teoría del límite central uniforme en el tiempo y secuencias de confianza asintótica](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcule la confianza válida en cualquier momento **superior** utilizando el método WASKR como se describe en [Teoría del límite central uniforme en el tiempo y secuencias de confianza asintótica](https://arxiv.org/pdf/2103.06476).

La confianza es una medida probabilística del grado de evidencia de que una variante determinada sea la misma que la variante de control. Una mayor confianza indica menos evidencia para el supuesto de que la variante de control y la que no es de control tienen un rendimiento igual.

| Argumento | Descripción |
| --- | --- |
| normalizing-container | La base (Personas, Sesiones o Eventos) en la que se ejecutará una prueba. |
| success-metric | La métrica o métricas con las que un usuario compara variantes. |
| control | La variante con la que se comparan todas las demás variantes del experimento. Introduzca el nombre del elemento de dimensión de variante de control. |
| significance-threshold | El umbral en esta función se establece en un 95 % de forma predeterminada. |


## Coseno {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cos"
>title="Coseno"
>abstract="Devuelve el coseno del ángulo determinado. Si el ángulo se expresa en grados, multiplique el ángulo por PI()/180."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(métrica)]**

[!BADGE Fila]{type="Neutral"} Devuelve el coseno de un ángulo determinado. Si el ángulo se expresa en grados, multiplique el ángulo por PI()/180.

| Argumento | Descripción |
|---|---|
| métrica | El ángulo en radianes para el que desea el coseno |


## Raíz cúbica {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cube-root"
>title="Raíz cúbica"
>abstract="Devuelve la raíz cúbica positiva de un número. La raíz cúbica de un número es el valor de ese número elevado a la potencia de 1/3."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


Devuelve la raíz cúbica positiva de un número. La raíz cúbica de un número es el valor de ese número elevado a la potencia de 1/3.


| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea la raíz cuadrada |



## Acumulativo {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul"
>title="Acumulativo"
>abstract="Devuelve la suma de los últimos n elementos de la columna x. Si n > 0, sume los últimos n elementos o x. Si n &lt; 0, sume los elementos precedentes."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Devuelve la suma de los últimos n elementos de la columna x. Si n > 0, sume los últimos n elementos o x. Si n &lt; 0, sume los elementos precedentes.

| Argumento | Descripción |
| --- | --- |
| número | El último número N de filas para las que se devuelve la suma. Si N &lt;= 0 utilice todas las filas anteriores.  |
| métrica | La métrica para la que desea obtener la suma acumulativa. |

### Ejemplos

| Fecha | Ingresos | CUMULATIVE(0, Revenue) | CUMULATIVE(2, Revenue) |
|------|------:|--------------:|--------------:|
| Mayo | 500 USD | 500 USD | 500 USD |
| Junio | 200 USD | 700 USD | 700 USD |
| Julio | $400 | 1100 USD | $600 |


## Acumulativo (promedio) {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul-avg"
>title="Acumulativo (promedio)"
>abstract="Devuelve el promedio de los últimos n elementos de la columna x. Si n > 0, sume los últimos n elementos o x. Si n &lt; 0, sume los elementos precedentes."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

Devuelve el promedio de los últimos n elementos de la columna x. Si n > 0, sume los últimos n elementos o x. Si n &lt; 0, sume los elementos precedentes.

| Argumento | Descripción |
| --- | --- |
| número | El último número N de filas para las que se devuelve el promedio. Si N &lt;= 0 utilice todas las filas anteriores.  |
| métrica | La métrica para la que desea el promedio acumulado. |

>[!NOTE]
>
>Esta función no funciona con métricas de tarifa, como los ingresos por persona. La función promedia los porcentajes en lugar de sumar los ingresos durante los últimos N y sumar las personas durante los últimos N y luego dividirlas. <br/>En su lugar, use [**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![Dividir](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative).
>


## Igual {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-eq"
>title="Igual"
>abstract="Igual. El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**

Igual. El resultado es 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| metric_X | La métrica que desea utilizar para comparar. |
| metric_Y | La métrica que desea utilizar para comparar. |

### Ejemplo

`Metric 1 = Metric 2`


## Regresión exponencial: coeficiente de correlación {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-exp"
>title="Regresión exponencial: coeficiente de correlación"
>abstract="Regresión exponencial: Y = a X + b. Devuelve el coeficiente de correlación."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros))]**


[!BADGE Tabla]{type="Neutral"} Regresión exponencial: Y = a exp(X) + b. Devuelve el coeficiente de correlación.


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |

## Regresión exponencial: predicción Y {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-exp"
>title="Regresión exponencial: predicción Y"
>abstract="Regresión exponencial: Y = a exp(X) + b. Devuelve Y."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros))]**


[!BADGE Fila]{type="Neutral"} Regresión exponencial: Y = a exp(X) + b. Devuelve Y.


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos independientes. |
| metric_Y | Una métrica que le gustaría designar como datos dependientes. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión exponencial: intersección {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-exp"
>title="Regresión exponencial: intersección"
>abstract="Regresión exponencial: Y = a exp(X) + b. Devuelve b."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg)  **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"} Regresión exponencial: Y = a exp(X) + b. Devuelve b.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión exponencial: pendiente {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-exp"
>title="Regresión exponencial: pendiente"
>abstract="Regresión exponencial: Y = a exp(X) + b. Devuelve a."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"} Regresión exponencial: Y = a exp(X) + b. Devuelve a.


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Límite mínimo {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-floor"
>title="Límite mínimo"
>abstract="Devuelve el mayor entero igual o menor a un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe para los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula LÍMITE MÍNIMO(Ingresos) para redondear hacia abajo al dólar más próximo o 569 $."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE Fila]{type="Neutral"} Devuelve el mayor entero más grande que no sea mayor que un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe para los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula LÍMITE MÍNIMO(Ingresos) para redondear hacia abajo al dólar más próximo o 569 $.

| Argumento | Descripción |
|---|---|
| métrica | La métrica que desee redondear. |


## Mayor que {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-gt"
>title="Mayor que"
>abstract="El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER()]**

El resultado es 0 (falso) o 1 (verdadero).

| Argumento | Descripción |
|---|---|
| metric_X | La métrica base que desea utilizar para comparar. |
| metric_Y | La métrica que desea utilizar para comparar. |

### Ejemplo

`Metric 1 > Metric 2`


## Mayor o igual que {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ge"
>title="Mayor o igual que"
>abstract="Mayor o igual que. El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**

Mayor o igual que. El resultado es 0 (falso) o 1 (verdadero).

| Argumento | Descripción |
|---|---|
| metric_X | La métrica base que desea utilizar para comparar. |
| metric_Y | La métrica que desea utilizar para comparar. |

### Ejemplo

`Metric 1 >= Metric 2`



## Coseno hiperbólico {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cosh"
>title="Coseno hiperbólico"
>abstract="Devuelve el coseno hiperbólico de un número."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(métrica)]**


[!BADGE Fila]{type="Neutral"} Devuelve el coseno hiperbólico de un número.


| Argumento | Descripción |
|---|---|
| métrica | El ángulo en radianes del cual desea encontrar el coseno hiperbólico |



## Seno hiperbólico {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sinh"
>title="Seno hiperbólico"
>abstract="Devuelve el seno hiperbólico de un número."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**

[!BADGE Fila]{type="Neutral"} Devuelve el seno hiperbólico de un número.

| Argumento | Descripción |
|---|---|
| métrica | El ángulo en radianes del cual desea encontrar el seno hiperbólico |


## Tangente hiperbólica {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tanh"
>title="Tangente hiperbólica"
>abstract="Devuelve la tangente hiperbólica de un número."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**

[!BADGE Fila]{type="Neutral"} Devuelve la tangente hiperbólica de un número.

| Argumento | Descripción |
|---|---|
| métrica | El ángulo en radianes del cual desea encontrar la tangente hiperbólica |


## Si {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-if"
>title="Si"
>abstract="Si el valor del parámetro de condición es distinto de cero (true), el resultado es el valor del parámetro value_if_true. De lo contrario, es el valor del parámetro value_if_false."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Fila]{type="Neutral"} Si el valor del parámetro de condición es distinto de cero (true), el resultado es el valor del parámetro value_if_true. De lo contrario, es el valor del parámetro value_if_false.


| Argumento | Descripción |
|---|---|
| logical_test | Obligatorio. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE |
| value_if_true | El valor que desea que sea devuelto si el argumento logical_test se evalúa como TRUE. (Este argumento es 0 de forma predeterminada si no se incluye). |
| value_if_false | El valor que desee que se devuelva si el argumento logical_test evalúa en FALSE. (El valor predeterminado de este argumento es 0 si no se incluye.) |


## Menor que {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-lt"
>title="Menor que"
>abstract="El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**

El resultado es 0 (falso) o 1 (verdadero).

| Argumento | Descripción |
|---|---|
| metric_X | La métrica que desea utilizar para comparar. |
| metric_Y | La métrica que desea utilizar para comparar. |

### Ejemplo

`Metric 1 < Metric 2`


## Menor o igual que {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-le"
>title="Menor o igual que"
>abstract="Menor o igual que. El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

Menor o igual que. El resultado es 0 (falso) o 1 (verdadero).

| Argumento | Descripción |
|---|---|
| metric_X | La métrica que desea utilizar para comparar. |
| metric_Y | La métrica que desea utilizar para comparar. |

### Ejemplo

`Metric 1 <= Metric 2`



## Lift {#lift}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lift"
>title="Lift"
>abstract="El alza de la proporción comparada con el valor de control."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LIFT(contenedor-normalizador, métrica-éxito, control)]**

El alza de la proporción comparada con el valor de control.

| Argumento | Descripción |
| --- | --- |
| normalizing-container | La base (Personas, Sesiones o Eventos) en la que se ejecutará una prueba. |
| success-metric | La métrica o métricas con las que un usuario compara variantes. |
| control | La variante con la que se comparan todas las demás variantes del experimento. Introduzca el nombre del elemento de dimensión de variante de control. |



## Regresión lineal: coeficiente de correlación {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-linear"
>title="Regresión lineal: coeficiente de correlación"
>abstract="Regresión lineal: Y = a X + b. Devuelve el coeficiente de correlación."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros))]**


[!BADGE Tabla]{type="Neutral"} Regresión lineal: Y = a X + b. Devuelve el coeficiente de correlación.


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión lineal: intersección {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-linear"
>title="Regresión lineal: intersección"
>abstract="Regresión lineal: Y = a X + b. Devuelve b."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"} Regresión lineal: Y = a X + b. Devuelve b.


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión lineal: predicción Y {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-linear"
>title="Regresión lineal: predicción Y"
>abstract="Y = a X + b. Devuelve Y."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Fila]{type="Neutral"} Regresión lineal: Y = a X + b. Devuelve Y.


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión lineal: pendiente {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-linear"
>title="Regresión lineal: pendiente"
>abstract="Y = a X + b. Devuelve a."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión lineal: Y = a X + b. Devuelve a.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Log base 10 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log10"
>title="Log base 10"
>abstract="Devuelve el logaritmo en base 10 de un número."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE Fila]{type="Neutral"} Devuelve el logaritmo en base 10 de un número.


| Argumento | Descripción |
|---|---|
| métrica | El número real positivo del cual desea el logaritmo decimal base-10 |


## Regresión logística: coeficiente de correlación {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-log"
>title="Regresión logística: coeficiente de correlación"
>abstract="Regresión logística: Y = a X + b. Devuelve el coeficiente de correlación."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión logarítmica: Y = a ln(X) + b. Devuelve el coeficiente de correlación.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión logística: intersección {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-log"
>title="Regresión logística: intersección"
>abstract="Regresión logística: Y = a ln(X) + b. Devuelve b."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión logarítmica: Y = a ln(X) + b. Devuelve b.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión logística: predicción Y  {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-log"
>title="Regresión logística: predicción Y "
>abstract="Regresión logística: Y = a ln(X) + b. Devuelve Y."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Fila]{type="Neutral"} Regresión logarítmica: Y = a ln(X) + b. Devuelve Y.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión logística: pendiente  {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-log"
>title="Regresión logística: pendiente "
>abstract="Regresión logística: Y = a ln(X) + b. Devuelve a."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión logarítmica: Y = a ln(X) + b. Devuelve a.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Logaritmo natural {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log"
>title="Logaritmo natural"
>abstract="Devuelve el logaritmo natural de un número. Los logaritmos naturales se basan en la constante e (2,71828182845904). LN es el inverso de la función EXP."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**

Devuelve el logaritmo natural de un número. Los logaritmos naturales se basan en la constante e (2,71828182845904). LN es el inverso de la función EXP.

| Argumento | Descripción |
|---|---|
| métrica | El número real positivo del cual desea el logaritmo natural |



## No {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-not"
>title="No"
>abstract="Negación como booleano. El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL NO(logical)]**

Negación como booleano. El resultado es 0 (falso) o 1 (verdadero).

| Argumento | Descripción |
|---|---|
| logical | Obligatorio. Un valor o expresión que puede evaluarse como TRUE o FALSE |



## No es igual {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ne"
>title="No es igual"
>abstract="No es igual. El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


No es igual. El resultado es 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| metric_X | La métrica que desea utilizar para comparar. |
| metric_Y | La métrica que desea utilizar para comparar. |

### Ejemplo

`Metric 1 != Metric 2`


## O bien {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-or"
>title="O bien"
>abstract="Disyunción. No es igual a cero se considera verdadero y es igual a cero se considera falso. El resultado es 0 (falso) o 1 (verdadero)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


Disyunción de [!BADGE fila]{type="Neutral"}. No es igual a cero se considera verdadero y es igual a cero se considera falso. El resultado es 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| logical_test | Requiere al menos un parámetro, pero puede tomar cualquier número de parámetros. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE |


>[!NOTE]
>
>0 (cero) significa Falso y cualquier otro valor es Verdadero.


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pi"
>title="Pi"
>abstract="Devuelve Pi: 3,14159..."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Devuelve Pi: 3,14159...


## Regresión potencial: coeficiente de correlación {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-power"
>title="Regresión potencial: coeficiente de correlación"
>abstract="Regresión potencial: Y = b X ^ a. Devuelve el coeficiente de correlación."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión potencial: Y = b X ^ a. Devuelve el coeficiente de correlación.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión potencial: intersección {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-power"
>title="Regresión potencial: intersección"
>abstract="Regresión potencial: Y = b X ^ a. Devuelve b."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"} Regresión potencial: Y = b X ^ a. Devuelve b.


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión potencial: predicción Y {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-power"
>title="Regresión potencial: predicción Y"
>abstract="Regresión potencial: Y = b X ^ a. Devuelve Y."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Fila]{type="Neutral"} Regresión potencial: Y = b X ^ a. Devuelve Y.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión potencial: pendiente {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-power"
>title="Regresión potencial: pendiente"
>abstract="Regresión potencial: Y = b X ^ a. Devuelve a."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión potencial: Y = b X ^ a. Devuelve a.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión cuadrática: coeficiente de correlación  {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-quadratic"
>title="Regresión cuadrática: coeficiente de correlación "
>abstract="Regresión cuadrática: Y = (a + bX) ^ 2, Devuelve el coeficiente de correlación."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión cuadrática: Y = (a + bX) ^ 2, Devuelve el coeficiente de correlación.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |

## Regresión cuadrática: intersección  {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-quadratic"
>title="Regresión cuadrática: intersección "
>abstract="Regresión cuadrática: Y = (a + bX) ^ 2, Devuelve a."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión cuadrática: Y = (a + bX) ^ 2, Devuelve a.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión cuadrática: predicción Y {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-quadratic"
>title="Regresión cuadrática: predicción Y"
>abstract="Regresión cuadrática: Y = (a + bX) ^ 2, Devuelve Y."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Fila]{type="Neutral"} Regresión cuadrática: Y = (a + bX) ^ 2, Devuelve Y.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión cuadrática: pendiente {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-quadratic"
>title="Regresión cuadrática: pendiente"
>abstract="Regresión cuadrática: Y = (a + bX) ^ 2, Devuelve b."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros]**

[!BADGE Tabla]{type="Neutral"} Regresión cuadrática: Y = (a + bX) ^ 2, Devuelve b.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión recíproca: coeficiente de correlación {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-reciprocal"
>title="Regresión recíproca: coeficiente de correlación"
>abstract="Regresión recíproca: Y = a + b X ^ -1. Devuelve el coeficiente de correlación."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros]**

[!BADGE Tabla]{type="Neutral"} Regresión recíproca: Y = a + b X ^ -1. Devuelve el coeficiente de correlación.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión recíproca: intersección {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-reciprocal"
>title="Regresión recíproca: intersección"
>abstract="Regresión recíproca: Y = a + b X ^ -1. Devuelve a."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabla]{type="Neutral"} Regresión recíproca: Y = a + b X ^ -1. Devuelve a.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión recíproca: predicción Y  {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-reciprocal"
>title="Regresión recíproca: predicción Y "
>abstract="Regresión recíproca: Y = a + b X ^ -1. Devuelve Y."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros]**

[!BADGE Fila]{type="Neutral"} Regresión recíproca: Y = a + b X ^ -1. Devuelve Y.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión recíproca: pendiente {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-reciprocal"
>title="Regresión recíproca: pendiente"
>abstract="Regresión recíproca: Y = a + b X ^ -1. Devuelve b."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros]**

[!BADGE Tabla]{type="Neutral"} Regresión recíproca: Y = a + b X ^ -1. Devuelve b.

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Varianza de muestra

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-variance-estimate"
>title="Varianza de muestra"
>abstract="Calcula una estimación de la varianza de muestra mediante la fórmula (sum(metric^2) / (N - 1)) - (sum(metric))^2/(N*(N-1)).  donde N es el recuento del contenedor de normalización. <br/>Esto se usa como parte de los cálculos de confianza *válidos en cualquier momento*. Por lo general, esta función no es útil por sí sola, pero se puede utilizar para comprobar cálculos o para realizar cálculos de confianza *manualmente*."

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANZA DE MUESTRA (contenedor de normalización, métrica de éxito)]**

Calcula una estimación de la varianza de muestra.

| Argumento | Descripción |
| --- | --- |
| normalizing-container | La base (Personas, Sesiones o Eventos) en la que se ejecutará una prueba. |
| success-metric | La métrica o métricas con las que un usuario compara variantes. |

<!-- markdownlint-enable MD034 -->



## Seno {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sin"
>title="Seno"
>abstract="Devuelve el seno del ángulo determinado. Si el ángulo se expresa en grados, multiplique el ángulo por PI()/180."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE Fila]{type="Neutral"} Devuelve el seno de un ángulo determinado. Si el ángulo se expresa en grados, multiplique el ángulo por PI()/180.


| Argumento | Descripción |
|---|---|
| métrica | El ángulo en radianes para el que desea el seno |




## Puntuación T {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-score"
>title="Puntuación T"
>abstract="La desviación de la [MEDIA](cm-functions.md#mean), dividida por la desviación estándar. Alias de la [puntuación Z](#z-score)."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**

La desviación de la [MEDIA](cm-functions.md#mean), dividida por la desviación estándar. Alias de la [puntuación Z](#z-score).

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la cual desea la puntuación T |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Prueba T {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-test"
>title="Prueba T"
>abstract="Realiza una prueba t de cola m con una puntuación t de x y n grados de libertad."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails]**

Realiza una prueba t de cola m con una puntuación t de x y n grados de libertad.

| Argumento | Descripción |
|---|---|
| métrica | La métrica en la que desea realizar una prueba T |
| degrees | Los grados de libertad |
| tails | La longitud de la cola que se utilizará para realizar la prueba T |

### Detalles

La firma es T-TEST (metric, degrees, tails). Debajo, simplemente llama a ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Esta función es similar a la función **[PRUEBA_Z](#z-test)**, que ejecuta ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**.

- ***m*** es el número de colas.
- ***n*** es el grado de libertad y debe ser un número constante para todo el informe, es decir, no cambia fila a fila.
- ***X*** es la estadística de la prueba T y normalmente es es una fórmula (por ejemplo **[PUNTUACIÓN_Z](#z-score)** basada en una métrica y se evaluará en cada fila.

El valor de retorno es la probabilidad de ver la estadística test x dados los grados de libertad y el número de colas.

### Ejemplos

1. Utilice la función para buscar periféricos:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. &#x200B;2. Combínelo con **[IF](#if)** para ignorar cualquier porcentaje de rechazo muy alto o muy bajo y haga un recuento de las sesiones en el resto:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## Tangente {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tan"
>title="Tangente"
>abstract="Devuelve la tangente del ángulo determinado. Si el ángulo se expresa en grados, multiplique el ángulo por PI()/180."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**

Devuelve la tangente del ángulo determinado. Si el ángulo se expresa en grados, multiplique el ángulo por PI()/180.

| Argumento | Descripción |
|---|---|
| métrica | El ángulo en radianes para el que desea la tangente. |



## Puntuación Z {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-score"
>title="Puntuación Z"
>abstract="La desviación de la media dividida por la desviación estándar."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**

[!BADGE Fila]{type="Neutral"} La desviación de la media dividida por la desviación estándar.

| Argumento | Descripción |
|---|---|
| métrica | La métrica para la que desea la puntuación Z |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |

Una puntuación Z de 0 (cero) significa que la puntuación es la misma que la media. Una puntuación Z puede ser positiva o negativa, lo que indica si está por encima o por debajo de la media y por cuántas desviaciones estándar.

La ecuación para la puntuación Z es:

![](assets/z_score.png)

donde ***[!DNL x]*** es la puntuación sin procesar, ***[!DNL μ]*** es la media de población y ***[!DNL σ]*** es la desviación estándar de la población.

>[!NOTE]
>
>***[!DNL μ]*** (mu) y ***[!DNL σ]*** (sigma) se calculan automáticamente a partir de la métrica.



## Prueba Z {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-test"
>title="Prueba Z"
>abstract="Realiza una prueba z de cola n con una puntuación z de x."

<!-- markdownlint-enable MD034 -->

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**

Realiza una prueba z de cola n con una puntuación z de x.

| Argumento | Descripción |
|---|---|
| métrica | La métrica en la que desea realizar una prueba Z |
| tails | Longitud de la cola que se utilizará para realizar la prueba Z |

>[!NOTE]
>
>Asume que los valores se distribuyen de forma normal.




<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->