---
title: 'Referencia: funciones básicas'
description: 'El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas. '
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Referencia: funciones básicas

El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas.

Aquí se encuentra una lista alfabética de las funciones y sus definiciones.

> [!NOTE] Cuando [!DNL metric] se identifica como un argumento en una función, también se permiten otras expresiones de métricas. Por ejemplo, [!DNL MAXV(metrics)] también permite [!DNL MAXV(PageViews + Visits).]

## Funciones de tabla en comparación con funciones de fila

Una función de tabla es aquella en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es aquella en la que el resultado es diferente para cada fila de la tabla.

## Valor absoluto (Fila)

Devuelve el valor absoluto de un número. El valor absoluto de un número es el número con signo positivo.

```
ABS(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee el valor absoluto. |

## Máximo de columna

Devuelve el valor más pequeño en un conjunto de elementos de dimensión para una columna de métrica. MAXV realiza una evaluación vertical dentro de una sola columna (métrica) en todos los elementos de dimensión.

```
MAXV(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | Una métrica que le gustaría haber evaluado. |

## Mínimo de columna

Devuelve el valor más pequeño en un conjunto de elementos de dimensión para una columna de métrica. MINV realiza una evaluación vertical dentro de una sola columna (métrica) en todos los elementos de dimensión.

```
MINV(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | Una métrica que le gustaría haber evaluado. |

## Suma de columna

Añade todos los valores numéricos de una métrica dentro de una columna (en todos los elementos de una dimensión).

```
SUM(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica para la cual desea el valor total o la suma. |

## Recuento (Tabla)

Devuelve el número, o recuento, de valores distintos a cero para una métrica dentro de una columna (el número de elementos únicos incluidos dentro de una dimensión).

```
COUNT(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica que desea contar. |

## Exponente (Fila)

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | The exponent applied to the base *e*. |

## Exponenciación

Operador de potencia

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y veces)
</pre>

## Media (Tabla)

Devuelve la media aritmética, o promedio, de una métrica en una columna.

```
MEAN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee la media. |

## Mediana (Tabla)

Devuelve la mediana de una métrica en una columna. La mediana es el número situado en el medio de un conjunto de números, es decir, la mitad de los números tienen un valor superior o igual a la mediana, y la otra mitad tienen un valor inferior o igual a esta.

```
MEDIAN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee la mediana. |

## Módulo

El resto de col1 / col2, utilizando la división euclidiana.

Devuelve el resto después de dividir x por y.

```
x = floor(x/y) + modulo(x,y)
```

El valor devuelto tiene el mismo signo que la entrada (o es cero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Para obtener siempre un número positivo, utilice

```
modulo(modulo(x,y)+y,y)
```

## Percentil (Tabla)

Devuelve el percentil k-th de los valores de una métrica. Puede utilizar esta función para establecer un umbral de aceptación. Por ejemplo, puede decidir si se examinan los elementos de la dimensión cuyo valor es superior al percentil 90.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>métrica</i> </td> 
   <td colname="col2"> La columna de métrica que define la posición relativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> El valor de percentil en el rango de 0 a 100, ambos incluidos. </td> 
  </tr> 
 </tbody> 
</table>

## Cuartil (Tabla)

Devuelve el cuartil de los valores de una métrica. Por ejemplo, los cuartiles se pueden usar para encontrar el 25 % de productos que genera más ingresos. MINV, MEDIAN y MAXV devuelven el mismo valor que QUARTILE cuando el cuarto es igual a 0 (cero), 2 y 4, respectivamente.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>métrica</i> </td> 
   <td colname="col2"> La métrica de la cual desee el valor de cuartil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cuarto </p> </td> 
   <td colname="col2"> Indica qué *valor devolver. </td> 
  </tr> 
 </tbody> 
</table>

*If *quart* = 0, QUARTILE returns the minimum value. Si *quart* = 1, QUARTILE muestra el primer cuartil (porcentaje 25). Si *quart* = 2, QUARTILE muestra el primer cuartil (porcentaje 50). Si *quart* = 3, QUARTILE muestra el primer cuartil (porcentaje 75). Si *cuarto* = 4, QUARTILE devuelve el valor máximo.

## Ronda

Devuelve el entero más próximo a un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe en los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula Round(*Ingresos*) para redondear al dólar más próximo o 569 $. Un sistema de informes de producto de $569.51 será redondeado al dólar más cercano, o $570.

```
ROUND(metric)
```

| Argumento | Descripción |
|---|---|
| *entero* | La métrica que desee redondear. |

Redondear sin un parámetro de dígitos es lo mismo que redondear con un parámetro de dígitos de 0, lo cual se denomina redondear al entero más próximo. Con un parámetro de dígitos, devuelve este número de dígitos a la derecha del decimal. Si el parámetro de dígitos es negativo, devuelve ceros a la izquierda del decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Recuento de fila

Devuelve el número de filas de una determinada columna (el número de elementos únicos incluidos dentro de una dimensión). “Únicos excedidos” cuenta como 1.

## Máximo de fila

Máximo de las columnas de cada fila.

## Mínimo de fila

Mínimo de las columnas de cada fila.

## Suma de fila

Suma de las columnas de cada fila.

## Raíz cuadrada (Fila)

Devuelve la raíz cuadrada positiva de un número. La raíz cuadrada de un número corresponde al valor de dicho número elevado a la potencia de 1/2.

```
SQRT(metric)
```

| Argumento | Descripción |
|---|---|
| *entero* | La métrica de la cual desee la raíz cuadrada. |

## Desviación estándar (Tabla)

Devuelve la desviación estándar, o raíz cuadrada de la varianza, en función de una población de datos de ejemplo.

La ecuación para STDEV es:

![](assets/std_dev.png)

donde x es la media de la muestra (*métrica*) y *n* es el tamaño de la muestra.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argumento</b> </td> 
   <td> <b> Descripción</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> métrica</i></b> </td> 
   <td> <p> La métrica de la cual desee la desviación estándar. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varianza (Tabla)

Devuelve la varianza en función de una población de datos de ejemplo.

La ecuación para VARIANCE es:

![](assets/variance_eq.png)

donde x es la media de la muestra, MEAN(*métrica*) y *n* es el tamaño de la muestra.

```
VARIANCE(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee la variación. |

Para calcular una varianza, observe toda una columna de números. A partir de esa lista de números, calcule primero el promedio. Una vez que tenga el promedio, vaya a través de cada entrada y haga lo siguiente:

1. Reste el promedio del número.

2. Multiplique el resultado por sí mismo.

3. Súmelo al total.

Una vez que haya repetido toda la columna, tendrá un solo total. A continuación, divida ese total por el número de elementos de la columna. Ese número es la varianza de la columna. Es un solo número. Sin embargo, se muestra como una columna de números.

Por ejemplo, supongamos que tiene una columna de tres elementos:

1

2

3

El promedio de esta columna es 2. La varianza de la columna será ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. En la Análisis ad hoc, este aspecto será el siguiente:

1 2/3

2 2/3

3 2/3
