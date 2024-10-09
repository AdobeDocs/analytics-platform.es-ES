---
title: 'Referencia: funciones básicas'
description: El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: ecf8156df0b31e81f1a5546829c6100831b2a600
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 31%

---

# Referencia: funciones básicas


El [Creador de métricas calculadas](cm-workflow/cm-build-metrics.md) le permite aplicar funciones estadísticas y matemáticas.

Aquí se encuentra una lista alfabética de las funciones y sus definiciones.

>[!NOTE]
>
>Cuando [!DNL metric] se identifica como un argumento en una función, también se permiten otras expresiones de métricas. Por ejemplo, [COLUMN MAXIMUM(metrics)](#column-maximum) también permite [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum).


## Funciones de tabla frente a funciones de fila

Una función de tabla es una en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es aquella en la que el resultado es diferente para cada fila de la tabla. Si procede y es relevante, una función se anota con el tipo de función.


## Valor absoluto

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL VALOR ABSOLUTO(métrica)]**

[!BADGE Fila]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | La métrica para la que desea calcular el valor absoluto. |


## Máximo de columna

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MÁXIMO DE COLUMNA(métrica, include_zeros)]**

Devuelve el mayor valor en un conjunto de elementos de una dimensión para una columna de métrica. MAXV evalúa de forma vertical dentro de una única columna (métrica) entre elementos de dimensión.

| Argumento | Descripción |
|---|---|
| metric | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |


## Mínimo de columna

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MÍNIMO DE COLUMNA(métrica, include_zeros)]**

Devuelve el menor valor en un conjunto de elementos de una dimensión para una columna de métrica. MINV evalúa de forma vertical dentro de una única columna (métrica) entre elementos de dimensión.

| Argumento | Descripción |
|---|---|
| metric | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |


## Suma de columna

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL SUMA DE COLUMNA(métrica)]**

Suma todos los valores numéricos de una métrica dentro de una columna (entre los elementos de una dimensión).

| Argumento | Descripción |
|---|---|
| metric | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |


## Recuento

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECUENTO(métrica)]**

[!BADGE Tabla]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | La métrica que desea contar. |


## Exponente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTE(métrica)]**

[!BADGE Fila]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | El exponente aplicado a la base e. |


## Media

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIA(métrica, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | La métrica para la que desea calcular el promedio. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |


## Mediana

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIANA(métrica, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | La métrica para la que desea calcular la mediana. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |


## Módulo

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MÓDULO(metric_X, metric_Y)]**

Devuelve el resto después de dividir x por y utilizando la división euclidiana.

| Argumento | Descripción |
|---|---|
| metric_X | La primera métrica que le gustaría dividir. |
| metric_Y | La segunda métrica que le gustaría dividir. |

### Ejemplos

El valor devuelto tiene el mismo signo que la entrada (o es cero).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

Para asegurarse de que siempre obtiene un número positivo, utilice

```
MODULO(MODULO(x,y)+y,y)
```

## Percentil

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTIL(métrica, k, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | El valor en porcentaje dentro del rango de 0 a 100, ambos incluidos. |
| k | La columna de métrica que define la posición relativa. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |



## Operador de potencia

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL OPERADOR DE ENERGÍA(metric_X, metrix_Y)]**

Devuelve x elevado a la potencia y.

| Argumento | Descripción |
|---|---|
| metric_X | La métrica que desea elevar a la potencia metric_Y. |
| metric_Y | La potencia a la que le gustaría aumentar metric_X. |


## Cuartil

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CUARTIL(métrica, cuartil, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}[COLUMNA MÍNIMA](#column-minimum), [MEDIANA](#median) y [COLUMNA MÁXIMA](#column-maximum) devuelven el mismo valor que [CUARTIL](#quartile) cuando el cuartil es igual a `0` (cero), `2` y `4`, respectivamente.

| Argumento | Descripción |
|---|---|
| metric | La métrica para la que desea calcular el valor del cuartil. |
| cuartil | Indica el valor de cuartil que se va a devolver. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |


## Ronda

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REDONDEO(métrica, número)]**

Redondear sin un parámetro *number* es lo mismo que redondear con un parámetro *number* de 0, es decir, redondear al entero más próximo.  Con un parámetro *number*, ROUND devuelve los dígitos *number* a la derecha del decimal.  Si *number* es negativo, devuelve ceros a la izquierda del separador decimal.

| Argumento | Descripción |
|---|---|
| metric | La métrica que desee redondear. |
| number | Cuántos dígitos a la derecha del decimal que desea devolver. (Si es negativo, devuelve ceros a la izquierda del decimal). |

### Ejemplos

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```


## Recuento de fila

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECUENTO DE FILAS()]**

Devuelve el recuento de filas de una columna en concreto (el número de elementos únicos registrados en una dimensión). *Excesos en la cantidad de valores exclusivos* se cuentan como 1.


## Máximo de fila

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MAX DE FILA(métrica, include_zeros)]**

Máximo de las columnas de cada fila.

| Argumento | Descripción |
|---|---|
| metric | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |

## Mínimo de fila

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL FILA MÍN(métrica, include_zeros)]**

Mínimo de las columnas de cada fila.

| Argumento | Descripción |
|---|---|
| metric | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |



## Suma de fila

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL SUMA DE FILA(métrica, include_zeros)]**

Suma de las columnas de cada fila.

| Argumento | Descripción |
|---|---|
| metric | Requiere al menos una métrica, pero puede tomar cualquier número de métricas como parámetros. |


## Raíz cuadrada

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RAÍZ CUADRADA(métrica, include_zeros)]**

[!BADGE Fila]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | La métrica para la que desea calcular la raíz cuadrada. |


## Desviación estándar

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL DESVIACIÓN ESTÁNDAR(métrica, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| | La métrica para la que desea calcular la desviación estándar. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |


## Desviación

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANZA(métrica, include_zeros)]**

[!BADGE Tabla]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | La métrica para la que desea calcular la varianza. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos. |


La ecuación de VARIANCE es:

![](assets/variance_eq.png){width="100"}

Donde *x* es la media de la muestra, [MEDIA(*métrica*)](#mean) y *n* es el tamaño de la muestra.


Para calcular una varianza, se observa una columna entera de números. A partir de una lista de números, calcule primero el promedio. Una vez que tenga el promedio, revise cada entrada y haga lo siguiente:

1. Reste el promedio del número.

1. Multiplique el resultado por sí mismo.

1. Súmelo al total.

Una vez que haya iterado en toda la columna, tendrá un solo total. A continuación, divida el total entre el número de elementos de la columna. El número resultante es la varianza de la columna. Esta es un número único, aunque aparece como una columna de números.

En el ejemplo de la siguiente columna de tres elementos:

| columna |
|:---:|
| 1 |
| 2 |
| 3 |

El promedio de esta columna es 2. La varianza de la columna es ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3.




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

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

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