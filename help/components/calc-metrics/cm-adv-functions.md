---
title: 'Referencia: funciones avanzadas'
description: Seleccione Mostrar avanzadas para acceder a estas funciones en la lista desplegable Funciones.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '2944'
ht-degree: 100%

---

# Referencia: funciones avanzadas

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). [Más información...](/help/getting-started/cja-aa.md)

Seleccione **[!UICONTROL Mostrar avanzadas]** para acceder a estas funciones en la lista desplegable **[!UICONTROL Funciones]**.

## Funciones de tabla en comparación con funciones de fila

Una función de tabla es una en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es una en la que el resultado es diferente para cada fila de la tabla.

## ¿Qué significa el parámetro Include-Zeros?

Indica si se incluyen ceros en el cálculo. En algunas ocasiones cero significa &quot;nada&quot;, pero en ocasiones es importante.

Por ejemplo, si tiene una métrica Ingresos y, a continuación, agrega una métrica Vistas de página al informe, de repente hay más filas para sus ingresos todas con valor de cero. Probablemente no desea que esto afecte a ningún valor MEAN, MIN, QUARTILE, etc. los cálculos que tiene en la columna de ingresos. En este caso, debería marcar el parámetro para incluir ceros.

Por otra parte, si tiene dos métricas en las que está interesado, puede que no sea justo afirmar que una tiene una media superior o mínima porque algunas de sus filas eran ceros, por lo que no debería marcar el parámetro para incluir ceros.

## Y

Devuelve el valor de su argumento. Utilice NOT para asegurarse de que un valor no es igual a un valor en concreto.

>[!NOTE]
>
>0 (cero) significa Falso y cualquier otro valor es Verdadero.

```
AND(logical_test1,[logical_test2],...)
```

| Argumento | Descripción |
|---|---|
| *prueba_lógica1* | Requerido. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE. |
| *prueba_lógica2* | Opcional. Condiciones adicionales que desee evaluar como VERDADERO o FALSO. |

## Número aproximado de elementos distintos (dimensión)

Devuelve el número aproximado de elementos distintos de dimensiones para la dimensión seleccionada. Esta función usa el método HyperLogLog (HLL) de números aproximados de elementos distintos.  Está configurada para garantizar que el valor se encuentre en el 5 % del 95 % del valor actual del tiempo.

```
Approximate Count Distinct (dimension)
```

| Argumento |  |
|---|---|
| *dimensión* | Dimensión de la que se quiere obtener el número aproximado de elementos distintos. |

## Caso práctico de ejemplo

El número aproximado de elementos distintos (eVar del ID del cliente) es un caso práctico común para esta función.

Definición para una nueva métrica calculada “Clientes aproximados”:

![](assets/approx-count-distinct.png)

Así es como se podría usar la métrica “Clientes aproximados” en un informe:

![](assets/approx-customers.png)

## Se excedió la cantidad de valores exclusivos

Igual que Count() y RowCount(), Approximate Count Distinct() está sujeto a [límites de “valores exclusivos excedidos”](https://experienceleague.adobe.com/docs/analytics/technotes/low-traffic.html?lang=es). Si una dimensión alcanza el límite de “valores exclusivos excedidos” en un mes en concreto, el valor se cuenta como un elemento de dimensión.

## Comparación de funciones de recuento

La función Approximate Count Distinct() es una mejora de las funciones Count() y RowCount() porque la métrica que se crea puede usarse en cualquier informe dimensional para representar un número aproximado de elementos para una dimensión distinta. Por ejemplo, un recuento de los ID de cliente que se usan en un informe sobre tipos de dispositivos móviles.

Esta función será ligeramente menos precisa que Count() y RowCount() porque usa el método HLL, mientras que Count() y RowCount() son recuentos exactos.

## Arcocoseno (Fila)

Devuelve el arcocoseno o la inversa del coseno de una métrica. El arcocoseno es el ángulo cuyo coseno es un número. El ángulo devuelto se da en radianes dentro del rango de 0 (cero) a pi. Si desea convertir el resultado de radianes a grados, multiplíquelo por 180/PI( ).

```
ACOS(metric)
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que desee desde -1 a 1. |

## Arcoseno (Fila)

Devuelve el arcoseno o la inversa del seno de un número. El arcoseno es el ángulo cuyo seno es un número. El ángulo devuelto se da en radianes dentro del rango de -pi/2 a pi/2. Para expresar el arcoseno en grados, multiplique el resultado por 180/PI( ).

```
ASIN(metric)
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que desee desde -1 a 1. |

## Arcotangente (Fila)

Devuelve el arcotangente o la inversa de la tangente de un número. El arcotangente es el ángulo cuya tangente es un número. El ángulo devuelto se da en radianes dentro del rango de -pi/2 a pi/2. Para expresar el arcotangente en grados, multiplique el resultado por 180/PI( ).

```
ATAN(metric)
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que desee desde -1 a 1. |

## Regresión exponencial: Y predicha (Fila)

Calcula los valores Y predichos (metric_Y), dados los valores x conocidos (metric_X) usando el método de &quot;mínimos cuadrados&quot; para calcular la línea que mejor se ajusta según la fórmula.

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Cdf-T

Devuelve el porcentaje de valores en una distribución t de Student con n grados de libertad que tiene un valor z inferior al de x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Devuelve el porcentaje de valores en una distribución normal que tienen un valor de z inferior al valor de x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499
```

## Techo (Fila)

Devuelve el menor entero igual o mayor que un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe en los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula CEILING(*Ingresos*) para redondear hacia arriba al dólar más próximo o 570 $.

```
CEILING(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica que desee redondear. |

## Coseno (Fila)

Devuelve el coseno de un ángulo determinado. Si el ángulo es en grados, multiplique el ángulo por PI( )/180.

```
COS(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea el coseno. |

## Raíz cúbica

Devuelve la raíz cúbica positiva de un número. La raíz cúbica de un número es el valor de dicho número elevado a la potencia de 1/3.

```
CBRT(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea la raíz cúbica. |

## Acumulativo

Devuelve la suma de X para las últimas N filas (según lo solicite la dimensión, utilizando valores hash para los campos basados en cadenas).

Si N &lt;= 0 utiliza todas las filas anteriores. Como se ordena por la dimensión, solo resulta útil en dimensiones que tienen un orden natural como la fecha o la longitud de ruta.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) |
|------+------+--------------+--------------|
| May  | $500 | $500         | $500         |
| June | $200 | $700         | $700         |
| July | $400 | $1100        | $600         |
```

## Media acumulada

Devuelve la media de las últimas N filas.

Si N &lt;= 0 utiliza todas las filas anteriores. Como se ordena por la dimensión, solo resulta útil en dimensiones que tienen un orden natural como la fecha o la longitud de ruta.

>[!NOTE]
>
>Esto no funcionará de la forma esperada con métricas de tasa, tales como ingresos o visitantes. Calcula la media de las tasas, en lugar de sumar los ingresos y los visitantes del último N y después dividirlos. En su lugar utilice

```
cumul(revenue)/cumul(visitor)
```

## Igual

Devuelve elementos que coinciden exactamente con un valor numérico o de cadena.

## Regresión exponencial: coeficiente de correlación (Tabla)

Devuelve el coeficiente de correlación, *r*, entre dos columnas de métricas (*metric_A* y *metric_B*) en la ecuación de regresión.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión exponencial: intersección (Tabla)

Devuelve la intersección, *b*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión exponencial: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Suelo (Fila)

Devuelve el mayor entero igual o menor a un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe en los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula FLOOR(*Ingresos*) para redondear hacia arriba al dólar más próximo o 569 $.

```
FLOOR(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica que desee redondear. |

## Mayor que

Devuelve elementos cuyo recuento numérico sea mayor que el valor introducido.

## Mayor o igual que

Devuelve elementos cuyo recuento numérico sea mayor o igual que el valor introducido.

## Coseno hiperbólico (Fila)

Devuelve el coseno hiperbólico de un número.

```
COSH(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea encontrar el coseno hiperbólico. |

## Seno hiperbólico (Fila)

Devuelve el seno hiperbólico de un número.

```
SINH(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea encontrar el seno hiperbólico. |

## Tangente hiperbólica (Fila)

Devuelve la tangente hiperbólica de un número.

```
TANH(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea encontrar la tangente hiperbólica. |

## IF (Fila)

La función IF devuelve un valor si una condición que haya especificada se evalúa como TRUE y otro valor si esa condición se evalúa como FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argumento | Descripción |
|---|---|
| *logical_test* | Requerido. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE. |
| *[value_if_true]* | El valor que desea que sea devuelto si el argumento *logical_test* se evalúa como TRUE. (Este argumento es 0 de forma predeterminada si no se incluye). |
| *[value_if_false]* | El valor que desea que sea devuelto si el argumento *logical_test* se evalúa como FALSE. (Este argumento es 0 de forma predeterminada si no se incluye). |

## Menor que

Devuelve elementos cuyo recuento numérico sea menor que el valor introducido.

## Menor o igual que

Devuelve elementos cuyo recuento numérico sea menor o igual que el valor introducido.

## Regresión lineal: coeficiente de correlación

Y = a X + b. Devuelve el coeficiente de correlación.

## Regresión lineal: intercepción

Y = a X + b. Devuelve b.

## Regresión lineal: Y predicha

Y = a X + b. Devuelve Y.

## Regresión lineal: pendiente

Y = a X + b. Devuelve a.

## Logaritmo decimal (Fila)

Devuelve el logaritmo decimal de un número.

```
LOG10(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El número real positivo del cual desea el logaritmo decimal. |

## Regresión logarítmica: coeficiente de correlación (Tabla)

Devuelve el coeficiente de correlación, *r*, entre dos columnas de métricas (*metric_X* y *metric_Y*) en la ecuación de regresión [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación CORREL.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión logarítmica: intersección (Tabla)

Devuelve la intersección *b* como la regresión con menos cuadrados entre dos columnas de métricas (*metric_X* y *metric_Y*) para la ecuación de regresión [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación INTERCEPT.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión de registro: Y predicha (fila)

Calcula los valores [!DNL y] predichos (metric_Y), dados los valores [!DNL x] conocidos (metric_X) con el método de &quot;menos cuadrados&quot; para calcular la mejor opción basándose en [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación ESTIMATE.

En el análisis de regresión, esta función calcula los valores [!DNL y] predichos (*metric_Y*), dados los valores [!DNL x] conocidos (*metric_X*) usando el logaritmo para calcular la mejor opción para la ecuación de regresión [!DNL Y = a ln(X) + b]. Los valores [!DNL a] se corresponden con cada valor x y [!DNL b] es un valor constante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión logarítmica: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y *metric_Y*) en la ecuación de regresión [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación SLOPE.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_A* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_B* | Una métrica que le gustaría designar como datos independientes. |

## Logaritmo natural

Devuelve el logaritmo natural de un número. Los logaritmos naturales se basan en la constante *e* (2,71828182845904). El logaritmo natural es la inversa de la función exponencial.

```
LN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El número real positivo del cual desea el logaritmo natural. |

## NO

Devuelve 1 si el número es 0 o devuelve 0 si es otro número.

```
NOT(logical)
```

| Argumento | Descripción |
|---|---|
| *lógico* | Requerido. Un valor o expresión que puede evaluarse como TRUE o FALSE. |

Si utiliza NOT, es necesario conocer si las expresiones (&lt;, >, =, &lt;> , etc.) devuelven valores 0 o 1.

## Distinto a

Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido.

## O (Fila)

Devuelve TRUE si algún argumento es TRUE o devuelve FALSE si todos los argumentos son FALSE.

>[!NOTE]
>
>0 (cero) significa Falso y cualquier otro valor es Verdadero.

```
OR(logical_test1,[logical_test2],...)
```

| Argumento | Descripción |
|---|---|
| *prueba_lógica1* | Requerido. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE. |
| *prueba_lógica2* | Opcional. Condiciones adicionales que desee evaluar como VERDADERO o FALSO. |

## Pi

Devuelve la constante PI, 3,14159265358979, con una precisión de 15 dígitos.

```
PI()
```

La función [!DNL PI] no tiene argumentos.

## Regresión potencial: coeficiente de correlación (Tabla)

Devuelve el coeficiente de correlación, *r*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión potencial: intersección (Tabla)

Devuelve la intersección, *b*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión potencial: Y predicha (Fila)

Calcula los valores [!DNL y] predichos ([!DNL metric_Y]), dados los valores [!DNL x] conocidos ([!DNL metric_X]) utilizando el método de “menos cuadrados” para calcular la mejor opción de línea para [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión potencial: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = b*X]a.

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión cuadrática: coeficiente de correlación (Tabla)

Devuelve el coeficiente de correlación *r*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión cuadrática: intersección (Tabla)

Devuelve la intersección, *b*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión cuadrática: Y predicha (Fila)

Calcula los valores [!DNL y] predichos (metric_Y), dados los valores [!DNL x] conocidos (metric_X) utilizando el método de los menos cuadrados para calcular la mejor opción de línea para [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_A* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_B* | Una métrica que le gustaría designar como datos dependientes. |

## Regresión cuadrática: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y metric_Y) para [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión recíproca: coeficiente de correlación (Tabla)

Devuelve el coeficiente de correlación, *r*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión recíproca: intersección (Tabla)

Devuelve la intersección, *b*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión recíproca: Y predicha (Fila)

Calcula los valores [!DNL y] predichos (metric_Y), dados los valores [!DNL x] conocidos (metric_X) utilizando el método de los menos cuadrados para calcular la mejor opción de línea para [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión recíproca: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = a/X+b]a.

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Seno (Fila)

Devuelve el seno de un ángulo determinado. Si el ángulo es en grados, multiplique el ángulo por PI( )/180.

```
SIN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea el seno. |

## Unidad tipificada

Es el nombre por el que también se conoce una variable estandarizada, concretamente, la desviación de la media dividida por la desviación estándar.

## Prueba T

Realiza una prueba T con una distribución m con una unidad tipificada de col y n grados de libertad.

La firma es `t_test( x, n, m )`. Debajo, simplemente llama `m*cdf_t(-abs(x),n)`. (esto es similar a la función z-test que ejecuta `m*cdf_z(-abs(x))`.

Aquí, `m` es la cantidad de colas y `n`, los grados de la libertad. Estos deben ser números (constantes en todo el informe, es decir, que no se modifiquen de fila a fila).

`X` es la estadística t-test y es normalmente una fórmula (por ejemplo, zscore) basada en una métrica y se evaluará en cada fila.

El valor de retorno es la probabilidad de ver la estadística test x dados los grados de libertad y el número de colas.

**Ejemplos:**

1. Úselo para buscar periféricos:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combínelo con `if` para ignorar cualquier tasa de devolución alta o baja y haga un recuento de visitas en el resto:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangente

Devuelve la tangente de un ángulo determinado. Si el ángulo es en grados, multiplique el ángulo por PI( )/180.

```
TAN (metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea la tangente. |

## Variable estandarizada (Fila)

Devuelve la variable estandarizada, o una puntuación normal, basada en una distribución normal. La variable estandarizada es el número de desviaciones estándar a las que se encuentra una observación con respecto a la media. Una variable estandarizada de 0 (cero) significa que la puntuación es la misma que la media. Una variable estandarizada puede ser positiva o negativa, lo cual indica si está por encima o por debajo de la media y a cuantas desviaciones estándar.

La ecuación de variable estandarizada es:

![](assets/z_score.png)

donde [!DNL x] es la puntuación sin procesar, [!DNL μ] es la media de población y [!DNL σ] es la desviación estándar de la población.

>[!NOTE]
>
>[!DNL μ] (mu) y [!DNL σ] (sigma) se calculan automáticamente a partir de la métrica.

Puntuación Z(métrica)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argumento </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>métrica</i> </td>
   <td colname="col2"> <p> Devuelve el valor del primer argumento distinto a cero. </p> </td>
  </tr>
 </tbody>
</table>

## Prueba Z

Realiza una prueba Z con una distribución n con una variable estandarizada de A.

Devuelve la probabilidad de que la fila actual pueda verse por casualidad en la columna.

>[!NOTE]
>
>Asume que los valores se distribuyen de forma normal.
