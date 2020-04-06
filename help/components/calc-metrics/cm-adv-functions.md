---
title: 'Referencia: funciones avanzadas'
description: Seleccione Mostrar avanzadas para acceder a estas funciones en la lista desplegable Funciones.
translation-type: tm+mt
source-git-commit: 2dab33dca173fcc0eab657b810e85e4740e5d7e0

---


# Referencia: funciones avanzadas

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## Funciones de tabla en comparación con funciones de fila

Una función de tabla es aquella en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es aquella en la que el resultado es diferente para cada fila de la tabla.

## ¿Qué significa el parámetro Include-Zeros? 

Indica si se deben incluir ceros en el cálculo. A veces cero significa &quot;nada&quot;, pero a veces es importante.

Por ejemplo: si tiene una métrica Ingresos y luego agrega una métrica Vistas de página al informe, repentinamente hay más filas para los ingresos que son todas cero. Probablemente no quiera que esto afecte a ningún MEAN, MIN, QUARTILE, etc. cálculos que tiene en la columna de ingresos. En este caso, comprobaría el parámetro include-zeros.

Por otro lado, si tiene dos métricas en las que le interesa, puede que no sea justo decir que una tiene una media o un mínimo más altos porque algunas de sus filas eran ceros, por lo que no debería comprobar el parámetro para incluir los ceros.

## Y

Devuelve el valor de su argumento. Utilice NO para asegurarse de que un valor no es igual a un valor en particular.

>[!NOTE] 0 (cero) significa Falso y cualquier otro valor es Verdadero.

```
AND(logical_test1,[logical_test2],...)
```

| Argumento | Descripción |
|---|---|
| *logical_test1* | Obligatorio. Cualquier valor o expresión que pueda evaluarse como VERDADERO o FALSO. |
| *logical_test2* | Opcional. Condiciones adicionales que desea evaluar como VERDADERO o FALSO |

## Número aproximado de elementos distintos (dimensión)

Devuelve el número aproximado de elementos distintos para la dimensión seleccionada. La función utiliza el método HyperLogLog (HLL) para aproximar distintos recuentos.  Está configurada para garantizar que el valor se encuentre en el 5 % del 95 % del valor actual del tiempo.

```
Approximate Count Distinct (dimension)
```

| Argumento |  |
|---|---|
| *dimensión* | Dimensión para la que desea el recuento de elementos definido aproximado. |

## Caso práctico de ejemplo 

El número aproximado de elementos distintos (eVar del ID del cliente) es un caso práctico común para esta función.

Definición para una nueva métrica calculada “Clientes aproximados”:

![](assets/approx-count-distinct.png)

Así es como se podría usar la métrica “Clientes aproximados” en un informe:

![](assets/approx-customers.png)

## Se excedió la cantidad de valores exclusivos 

Al igual que Count() y RowCount(), Approximate Count Distinct() está sujeto a límites [de](https://marketing.adobe.com/resources/help/es_ES/reference/metrics_uniques_high_numbers.html)&quot;valores exclusivos excedidos&quot;. Si se alcanza el límite de &quot;valores exclusivos excedidos&quot; en un mes concreto para una dimensión, el valor se cuenta como 1 elemento de dimensión.

## Comparación de funciones de recuento 

Approximate Count Distinct() es una mejora con respecto a las funciones Count() y RowCount() porque la métrica creada puede utilizarse en cualquier informe dimensional para representar un recuento aproximado de elementos para una dimensión independiente. Por ejemplo, un recuento de los ID de cliente utilizados en un informe de tipo de dispositivo móvil.

Esta función será ligeramente menos precisa que Count() y RowCount() porque utiliza el método HLL, mientras que Count() y RowCount() son recuentos exactos.

## Arcocoseno (Fila)

Devuelve el arco coseno, o la inversa del coseno, de una métrica. El arco coseno es el ángulo cuyo coseno es el número. El ángulo devuelto se indica en radianes en el intervalo de 0 (cero) a pi. Si quiere convertir el resultado de radianes a grados, debe multiplicarlo por 180/pi( ).

```
ACOS(metric)
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que quiera de -1 a 1. |

## Arcoseno (Fila)

Devuelve el arco seno, o seno inverso, de un número. El arco seno es el ángulo cuyo seno es el número. El ángulo devuelto se indica en radianes en el intervalo de -pi/2 a pi/2. Para expresar el arco seno en grados, hay que multiplicar el resultado por 180/pi( ).

```
ASIN(metric) 
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que quiera de -1 a 1. |

## Arcotangente (Fila)

Devuelve el arco tangente, o tangente inversa, de un número. El arco tangente es el ángulo cuya tangente es el número. El ángulo devuelto se indica en radianes en el intervalo de -pi/2 a pi/2. Para expresar el arco tangente en grados, hay que multiplicar el resultado por 180/pi( ).

```
ATAN(metric)
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que quiera de -1 a 1. |

## Regresión exponencial: Y predicha (Fila)

Calcula los valores Y predichos (metric_Y), dados los valores x conocidos (metric_X) usando el método de &quot;mínimos cuadrados&quot; para calcular la línea que mejor se ajusta según la fórmula .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

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

Devuelve el coseno del ángulo proporcionado. Si el ángulo se expresa en grados, multiplíquelo por pi( )/180.

```
COS(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desee el coseno. |

## Raíz cúbica

Devuelve la raíz cúbica positiva de un número. La raíz cúbica de un número corresponde al valor de dicho número elevado a la potencia de 1/3.

```
CBRT(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee la raíz cúbica. |

## Acumulativo

Devuelve la suma de x para las últimas N filas (según el orden de la dimensión, mediante valores hash para campos basados en cadenas).

Si N &lt;= 0, utiliza todas las filas anteriores. Dado que se ordena por la dimensión, solo es útil en dimensiones que tienen un orden natural, como la fecha o la longitud de ruta.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Media acumulada

Devuelve el promedio de las últimas N filas.

Si N &lt;= 0, utiliza todas las filas anteriores. Dado que se ordena por la dimensión, solo es útil en dimensiones que tienen un orden natural, como la fecha o la longitud de ruta.

>[!NOTE] Esto no funcionará de la forma esperada con métricas de tasa, tales como ingresos o visitantes. Calcula la media de las tasas, en lugar de sumar los ingresos y los visitantes del último N y después dividirlos. En su lugar utilice

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
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Regresión exponencial: intersección (Tabla)

Devuelve la intersección, *b*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión exponencial: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para.

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

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
| *métrica* | El ángulo en radianes del cual desee encontrar el coseno hiperbólico. |

## Seno hiperbólico (Fila)

Devuelve el seno hiperbólico de un número.

```
SINH(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desee encontrar el seno hiperbólico. |

## Tangente hiperbólica (Fila)

Devuelve la tangente hiperbólica de un número.

```
TANH(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea encontrar la tangente hiperbólica. |

## IF (Fila)

La función IF devuelve un valor si una condición especificada se evalúa como VERDADERO y otro valor si esa condición se evalúa como FALSO.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argumento | Descripción |
|---|---|
| *logical_test* | Obligatorio. Cualquier valor o expresión que pueda evaluarse como VERDADERO o FALSO. |
| *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.) |
| *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.) |

## Menor que

Devuelve elementos cuyo recuento numérico sea menor que el valor introducido.

## Menor o igual que

Devuelve elementos cuyo recuento numérico sea menor o igual que el valor introducido.

## Regresión lineal: coeficiente de correlación

Y = a X + b. Devuelve el coeficiente de correlación

## Regresión lineal: intercepción

Y = a X + b. Devuelve b.

## Regresión lineal: Y predicha

Y = a X + b. Devuelve Y.

## Regresión lineal: pendiente

Y = a X + b. Devuelve a.

## Logaritmo decimal (Fila)

Devuelve el logaritmo en base 10 de un número.

```
LOG10(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El número real positivo del que desee el logaritmo en base 10. |

## Regresión logarítmica: coeficiente de correlación (Tabla)

Devuelve el coeficiente de correlación, *r*, entre dos columnas de métricas (*metric_X* y *metric_Y*) en la ecuación de regresión [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación CORREL.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Regresión logarítmica: intersección (Tabla)

Devuelve la intersección *b* como la regresión con menos cuadrados entre dos columnas de métricas (*metric_X* y *metric_Y*) para la ecuación de regresión [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación INTERCEPT.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión de registro: Y predicha (fila)

Calcula los valores [!DNL y] predichos (metric_Y), dados los valores [!DNL x] conocidos (metric_X) con el método de &quot;menos cuadrados&quot; para calcular la mejor opción basándose en [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación ESTIMATE.

En el análisis de regresión, esta función calcula los valores [!DNL y] predichos (*metric_Y*), dados los valores [!DNL x] conocidos (*metric_X*) usando el logaritmo para calcular la mejor opción para la ecuación de regresión [!DNL Y = a ln(X) + b]. Los valores [!DNL a] se corresponden con cada valor x y [!DNL b] es un valor constante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión logarítmica: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y *metric_Y*) en la ecuación de regresión [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación SLOPE.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_A* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_B* | Una métrica que le gustaría designar como dato independiente. |

## Logaritmo natural

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El número real positivo del que desee el logaritmo en natural. |

## NO

Devuelve 1 si el número es 0 o devuelve 0 si es otro número.

```
NOT(logical)
```

| Argumento | Descripción |
|---|---|
| *lógica* | Obligatorio. Un valor o expresión que puede evaluarse como VERDADERO o FALSO. |

El uso de NO requiere saber si las expresiones (&lt;, >, =, &lt;>, etc.) devuelve valores 0 o 1.

## Distinto a

Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido.

## O (Fila)

Devuelve TRUE si algún argumento es VERDADERO o devuelve FALSE si todos los argumentos son FALSOS.

>[!NOTE] 0 (cero) significa Falso y cualquier otro valor es Verdadero.

```
OR(logical_test1,[logical_test2],...)
```

| Argumento | Descripción |
|---|---|
| *logical_test1* | Obligatorio. Cualquier valor o expresión que pueda evaluarse como VERDADERO o FALSO. |
| *logical_test2* | Opcional. Condiciones adicionales que desea evaluar como VERDADERO o FALSO |

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
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Regresión potencial: intersección (Tabla)

Devuelve la intersección, *b*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión potencial: Y predicha (Fila)

Calcula los valores [!DNL y] predichos ([!DNL metric_Y]), dados los valores [!DNL x] conocidos ([!DNL metric_X]) utilizando el método de “menos cuadrados” para calcular la mejor opción de línea para [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión potencial: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = b*X]a.

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión cuadrática: coeficiente de correlación (Tabla)

Devuelve el coeficiente de correlación *r*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Regresión cuadrática: intersección (Tabla)

Devuelve la intersección, *b*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión cuadrática: Y predicha (Fila)

Calcula los valores [!DNL y] predichos (metric_Y), dados los valores [!DNL x] conocidos (metric_X) utilizando el método de los menos cuadrados para calcular la mejor opción de línea para [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_A* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_B* | Una métrica que le gustaría designar como dato dependiente. |

## Regresión cuadrática: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y metric_Y) para [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión recíproca: coeficiente de correlación (Tabla)

Devuelve el coeficiente de correlación, *r*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Regresión recíproca: intersección (Tabla)

Devuelve la intersección, *b*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión recíproca: Y predicha (Fila)

Calcula los valores [!DNL y] predichos (metric_Y), dados los valores [!DNL x] conocidos (metric_X) utilizando el método de los menos cuadrados para calcular la mejor opción de línea para [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Regresión recíproca: pendiente (Tabla)

Devuelve la pendiente, *a*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = a/X+b]a.

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como dato dependiente. |
| *metric_Y* | Una métrica que le gustaría designar como dato independiente. |

## Seno (Fila)

Devuelve el seno del ángulo proporcionado. Si el ángulo se expresa en grados, multiplíquelo por pi( )/180.

```
SIN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desee el seno. |

## Unidad tipificada

Es el nombre por el que también se conoce una variable estandarizada, concretamente, la desviación de la media dividida por la desviación estándar

## Prueba T

Realiza una prueba T con una distribución m con una unidad tipificada de col y n grados de libertad.

La firma es `t_test( x, n, m )`. Debajo, simplemente llama `m*cdf_t(-abs(x),n)`. (esto es similar a la función z-test que ejecuta `m*cdf_z(-abs(x))`.

Aquí, `m` es la cantidad de colas y `n`, los grados de la libertad. Estos deben ser números (constantes en todo el informe, es decir, que no se modifiquen de fila a fila).

`X` es la estadística t-test y es normalmente una fórmula (por ejemplo, zscore) basada en una métrica y se evaluará en cada fila.

El valor devuelto es la probabilidad de ver la estadística de prueba x dados los grados de libertad y el número de colas.

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

Devuelve la tangente del ángulo proporcionado. Si el ángulo se expresa en grados, multiplíquelo por pi( )/180.

```
TAN (metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desee la tangente. |

## Variable estandarizada (Fila)

Devuelve la variable estandarizada, o puntuación normal, según una distribución normal. La variable estandarizada es el número de desviaciones estándar que una observación representa con respecto a la media. Una puntuación Z de 0 (cero) significa que la puntuación es la misma que la media. Una variable estandarizada puede ser positiva o negativa, indicando si está por encima o por debajo de la media y cuántas desviaciones estándar.

La ecuación de la variable estandarizada es:

![](assets/z_score.png)

donde [!DNL x] es la puntuación sin procesar, [!DNL μ] es la media de población y [!DNL σ] es la desviación estándar de la población.

>[!NOTE] [!DNL μ] (mu) y[!DNL σ] (sigma) se calculan automáticamente a partir de la métrica.

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
   <td colname="col2"> <p> Devuelve el valor de su primer argumento distinto a cero. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prueba Z

Realiza una prueba Z n-personalizada con la puntuación Z de A.

Devuelve la probabilidad de que la fila actual se pueda ver por casualidad en la columna.

>[!NOTE] Asume que los valores se distribuyen de forma normal.

