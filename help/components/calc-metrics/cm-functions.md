---
title: 'Referencia: funciones básicas'
description: El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '1077'
ht-degree: 100%

---

# Referencia: funciones básicas

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). [Más información...](/help/getting-started/cja-aa.md)

El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas.

Aquí se encuentra una lista alfabética de las funciones y sus definiciones.

>[!NOTE]
>
>Cuando [!DNL metric] se identifica como un argumento en una función, también se permiten otras expresiones de métricas. Por ejemplo, [!DNL MAXV(metrics)] también permite [!DNL MAXV(PageViews + Visits).]

## Funciones de tabla en comparación con funciones de fila

Una función de tabla es una en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es una en la que el resultado es diferente para cada fila de la tabla.

## Valor absoluto (Fila)

Devuelve el valor absoluto de un número. El valor absoluto de un número es el número con un valor positivo.

```
ABS(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea el valor absoluto. |

## Máximo de columna

Devuelve el mayor valor en un conjunto de elementos de una dimensión para una columna de métrica. MAXV evalúa de forma vertical dentro de una única columna (métrica) entre elementos de dimensión.

```
MAXV(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | Una métrica que le gustaría evaluar. |

## Mínimo de columna

Devuelve el menor valor en un conjunto de elementos de una dimensión para una columna de métrica. MINV evalúa de forma vertical dentro de una única columna (métrica) entre elementos de dimensión.

```
MINV(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | Una métrica que le gustaría evaluar. |

## Suma de columna

Suma todos los valores numéricos de una métrica dentro de una columna (entre los elementos de una dimensión).

```
SUM(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea el valor total o la suma. |

## Recuento (Tabla)

Devuelve un número, o recuento, de valores distintos de cero para una métrica dentro de una columna (el número de elementos únicos informados dentro de una dimensión).

```
COUNT(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica que desea contar. |

## Exponente (Fila)

Devuelve *e* elevado a la potencia de un número determinado. La constante *e* es igual a 2,71828182845904, la base del logaritmo natural. EXP es la inversa de LN, el logaritmo natural de un número.

```
EXP(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El exponente aplicado a la base *e*. |

## Exponenciación

Operador de potencia

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y veces)
</pre>

## Media (Tabla)

Devuelve la media aritmética, o el promedio, de una métrica en una columna.

```
MEAN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea la media. |

## Mediana (Tabla)

Devuelve la mediana de una métrica en una columna. La mediana es el número central de un conjunto de números; es decir, la mitad de los valores son mayores o iguales que la mediana y la mitad son menores o iguales que la mediana.

```
MEDIAN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea la mediana. |

## Módulo

El resto de la columna 1/columna 2, utilizando la división euclídea.

Devuelve el resto tras dividir x entre y.

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

Devuelve el percentil k-ésimo de los valores de una métrica. Puede utilizar esta función para establecer un umbral de aceptación. Por ejemplo, puede decidir si se examinan los elementos de la dimensión cuyo valor es superior al percentil 90.

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
   <td colname="col2"> El valor en porcentaje dentro del rango de 0 a 100, ambos incluidos. </td> 
  </tr> 
 </tbody> 
</table>

## Cuartil (Tabla)

Devuelve el cuartil de los valores de una métrica. Por ejemplo, los cuartiles se pueden utilizar para encontrar el primer 25 % de los productos que generan los mayores ingresos. MINV, MEDIAN y MAXV devuelven el mismo valor que QUARTILE cuando el cuartil es igual a 0 (cero), 2 y 4, respectivamente.

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
   <td colname="col2"> La métrica de la cual desea el valor de cuartil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cuarto </p> </td> 
   <td colname="col2"> Indica qué *valor debe devolver. </td> 
  </tr> 
 </tbody> 
</table>

*Si *cuarto* = 0, QUARTILE devuelve el valor mínimo. Si *cuarto* = 1, QUARTILE muestra el primer cuartil (porcentaje 25). Si *cuarto* = 2, QUARTILE muestra el primer cuartil (porcentaje 50). Si *cuarto* = 3, QUARTILE muestra el primer cuartil (porcentaje 75). Si *cuarto* = 4, QUARTILE devuelve el valor máximo.

## Ronda

Devuelve el entero más próximo a un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe en los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula Round(*Revenue*) para redondear al dólar más próximo o 569 $. Un producto de 569,51 $ se redondeará al dólar más cercano o 570 $.

```
ROUND(metric)
```

| Argumento | Descripción |
|---|---|
| *entero* | La métrica que desee redondear. |

Redondear sin un parámetro de dígito es lo mismo que redondear con un parámetro de dígito de 0, es decir, redondear al entero más próximo. Con un parámetro de dígito devuelve ese número de dígitos a la derecha del decimal. Si el dígito es negativo, devuelve ceros a la izquierda del decimal.

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

Devuelve la raíz cuadrada positiva de un número. La raíz cuadrada de un número es el valor de dicho número elevado a la potencia de 1/2.

```
SQRT(metric)
```

| Argumento | Descripción |
|---|---|
| *entero* | La métrica de la cual desea la raíz cuadrada. |

## Desviación estándar (Tabla)

Devuelve la desviación estándar, o la raíz cuadrada de la varianza, de una recopilación de datos de muestra.

La ecuación de STDEV es:

![](assets/std_dev.png)

donde x es la media de muestra (*métrica*) y *n* es el tamaño de la muestra.

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
   <td> <b> <i> métrica</i> </b> </td> 
   <td> <p> La métrica de la cual desee la desviación estándar. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varianza (Tabla)

Devuelve la varianza de una recopilación de datos de muestra.

La ecuación de VARIANCE es:

![](assets/variance_eq.png)

donde x es la media de la muestra, MEAN(*metric*) y *n* es el tamaño de la muestra.

```
VARIANCE(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea la varianza. |

Para calcular una varianza para ver una columna entera de números. A partir de una lista de números, calcule primero el promedio. Cuando tenga el promedio, examine cada entrada y realice lo siguiente:

1. Reste el promedio del número.

2. Multiplique el resultado por sí mismo.

3. Súmelo al total.

Cuando repita la operación sobre toda la columna, obtendrá un único total. A continuación, divida el total entre el número de elementos de la columna. El número resultante es la varianza de la columna. Esta es un número único, aunque aparece como una columna de números.

A modo de ejemplo, suponga que tiene una columna de tres elementos:

1

2

3

El promedio de esta columna es 2. La varianza de la columna será ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3.
