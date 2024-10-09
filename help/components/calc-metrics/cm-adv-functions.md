---
title: Funciones avanzadas
description: Seleccione Mostrar avanzadas para acceder a estas funciones en la lista desplegable Funciones.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '3126'
ht-degree: 19%

---

# Funciones avanzadas

El [Creador de métricas calculadas](cm-workflow/cm-build-metrics.md) le permite aplicar funciones estadísticas y matemáticas. Este artículo documenta la lista alfabética de las funciones avanzadas y sus definiciones.

Para obtener acceso a estas funciones, seleccione **[!UICONTROL Mostrar todo]** debajo de la lista ![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL Funciones]** en el panel Componentes. Desplácese hacia abajo para ver la lista de **[!UICONTROL funciones avanzadas]**.

## Funciones de tabla frente a funciones de fila

Una función de tabla es una en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es una en la que el resultado es diferente para cada fila de la tabla.

Cuando sea aplicable y relevante, una función se anota con el tipo de función: [!BADGE Tabla]{type="Neutral"}[!BADGE Fila]{type="Neutral"}

## ¿Qué significa el parámetro include-zeros?

Indica si se incluyen ceros en el cálculo. A veces cero significa *nada*, pero a veces es importante.

Por ejemplo, si tiene una métrica Ingresos y luego agrega una métrica Vistas de página al informe, de repente hay más filas para los ingresos, que son todas cero. Probablemente no quiera que esa métrica adicional afecte a ningún **[MEDIA](cm-functions.md#mean)**, **[MÍNIMO DE FILA](cm-functions.md#row-min)**, **[CUARTIL](cm-functions.md#quartile)** y más cálculos que tenga en la columna de ingresos. En este caso, comprobaría el parámetro `include-zeros`.

Un escenario alternativo es que tiene dos métricas de interés y una tiene un promedio o un mínimo más alto porque algunas de las filas son ceros.  En ese caso, puede optar por no marcar el parámetro para incluir ceros.


## Y

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL Y(prueba_lógica)]**


Conjunción. No igual a cero se considera verdadero y es igual a cero se considera falso. El resultado es un 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| logical_test | Requiere al menos un parámetro, pero puede tomar cualquier número de parámetros. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE |

## Approximate Count Distinct

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RECUENTO APROXIMADO DISTINCT(dimensión)]**


Devuelve el recuento aproximado distinto de elementos de dimensión para la dimensión seleccionada.


| Argumento | Descripción |
|---|---|
| dimensión | Dimensión para la que se desea calcular el recuento aproximado de elementos distintos |

### Ejemplo

Un caso de uso común para esta función es cuando desea obtener un número aproximado de clientes.




## Arcocoseno

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL COSENO DE ARCO(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | El coseno del ángulo deseado de -1 a 1 |



## Arcoseno

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL ARCO SENO(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | El seno del ángulo deseado de -1 a 1 |



## Arcotangente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL ARCO TANGENTE(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | La tangente del ángulo que desee de -1 a 1 |



## Cdf-T

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(métrica, número)]**


Devuelve la probabilidad de que una variable aleatoria con distribución Student-t con n grados de libertad tenga un valor z inferior al de col.


| Argumento | Descripción |
|---|---|
| metric | La métrica para la que desea la función de distribución acumulativa de la distribución t de Student |
| number | Los grados de libertad para la función de distribución acumulativa de la distribución t-Student |

### Ejemplo

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(métrica, número)]**


Devuelve la probabilidad de que una variable aleatoria con una distribución normal tenga un valor de z inferior al valor de col.


| Argumento | Descripción |
|---|---|
| metric | La métrica para la cual desea la función de distribución acumulativa de la distribución normal estándar |

### Ejemplos

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Techo

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL TECHO(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | La métrica que desea redondear |


## Confianza (inferior)

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIANZA(contenedor de normalización, métrica de éxito, control, umbral de relevancia)]**

Calcule la confianza válida en cualquier momento **lower** utilizando el método WASKR como se describe en [Teoría del límite central uniforme en el tiempo y secuencias de confianza asintótica](http://arxiv.org/pdf/2103.06476).

La confianza es una medida probabilística de cuánta evidencia existe de que una variante determinada es la misma que la de control. Una mayor confianza indica menos evidencia para el supuesto de que la variante de control y la que no es de control tienen un rendimiento igual.

| Argumento | Descripción |
| --- | --- |
| normalizing-container | La base (Personas, Sesiones o Eventos) en que se ejecuta una prueba. |
| métrica de éxito | La métrica o métricas con las que un usuario compara variantes. |
| dominar | La variante con la que se comparan todas las demás variantes del experimento. Introduzca el nombre del elemento de dimensión de variante de control. |
| umbral de relevancia | El umbral en esta función se establece en un 95 % de forma predeterminada. |

## Confianza (superior)

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIANZA(contenedor de normalización, métrica de éxito, control, umbral de relevancia)]**

Calcule la confianza válida en cualquier momento **upper** utilizando el método WASKR como se describe en [Teoría del límite central uniforme en el tiempo y secuencias de confianza asintótica](http://arxiv.org/pdf/2103.06476).

La confianza es una medida probabilística de cuánta evidencia existe de que una variante determinada es la misma que la de control. Una mayor confianza indica menos evidencia para el supuesto de que la variante de control y la que no es de control tienen un rendimiento igual.

| Argumento | Descripción |
| --- | --- |
| normalizing-container | La base (Personas, Sesiones o Eventos) en que se ejecuta una prueba. |
| métrica de éxito | La métrica o métricas con las que un usuario compara variantes. |
| dominar | La variante con la que se comparan todas las demás variantes del experimento. Introduzca el nombre del elemento de dimensión de variante de control. |
| umbral de relevancia | El umbral en esta función se establece en un 95 % de forma predeterminada. |


## Coseno

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL COSENO(métrica)]**

[!BADGE Fila]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | El ángulo en radianes del que se desea obtener el coseno |


## Raíz cúbica

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL RAÍZ DE CUBO(métrica)]**


Devuelve la raíz cúbica positiva de un número. La raíz cúbica de un número es el valor de dicho número elevado a la potencia de 1/3.


| Argumento | Descripción |
|---|---|
| metric | La métrica para la que desea calcular la raíz de cubo |



## Acumulativo

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL ACUMULATIVO(número, métrica)]**

Devuelve la suma de los últimos n elementos de la columna x. Si n > 0, suma los últimos n elementos o x. Si n &lt; 0, suma los elementos precedentes.

| Argumento | Descripción |
| --- | --- |
| number | El último número N de filas para las que se devuelve la suma. Si N &lt;= 0, se deben utilizar todas las filas anteriores. |
| metric | La métrica para la que desea obtener la suma acumulada. |

### Ejemplos

| Fecha | Ingresos | ACUMULATIVO(0, Ingresos) | CUMULATIVE(2, Ingresos) |
|------|------:|--------------:|--------------:|
| Mayo | 500 $ | 500 $ | 500 $ |
| Junio | 200 $ | 700 $ | 700 $ |
| Julio | $400 | 1100 $ | $600 |


## Acumulativo (promedio)

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PROMEDIO ACUMULADO(número, métrica)]**

Devuelve el promedio de los últimos n elementos de la columna x. Si n > 0, suma los últimos n elementos o x. Si n &lt; 0, suma los elementos precedentes.

| Argumento | Descripción |
| --- | --- |
| number | El último número N de filas para las que se devuelve el promedio. Si N &lt;= 0, se deben utilizar todas las filas anteriores. |
| metric | La métrica para la cual desea el Promedio acumulado. |

>[!NOTE]
>
>Esta función no funciona con métricas de tasa, como los ingresos por persona. La función promedia las tasas en lugar de sumar los ingresos durante los últimos N y sumar las personas durante los últimos N y luego dividirlas. <br/>En su lugar, use [**[!UICONTROL ACUMULATIVO(ingresos)]**](#cumulative) ![Dividir](/help/assets/icons/Divide.svg) [**[!UICONTROL ACUMULATIVO(persona)]**](#cumulative).
>


## Igual

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL IGUAL()]**


Igual. El resultado es un 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| metric_X | |
| metric_Y | |

### Ejemplo

`Metric 1 = Metric 2`



## Regresión exponencial: coeficiente de correlación

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN EXPONENCIAL: COEFICIENTE DE CORRELACIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |

## Regresión exponencial: Y predicha

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN EXPONENCIAL: Y PREDICHA(metric_X, metric_Y, include_zeros)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos independientes. |
| metric_Y | Una métrica que le gustaría designar como datos dependientes. |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión exponencial: intersección

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN EXPONENCIAL: INTERSECCIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión exponencial: pendiente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN EXPONENCIAL: PENDIENTE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Floor

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PISO(metric_X, metric_Y, include_zeros)]**

[!BADGE Fila]{type="Neutral"}

| Argumento | Descripción |
|---|---|
| metric | La métrica que desee redondear. |


## Mayor que

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MAYOR QUE()]**


El resultado es un 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| metric_X | |
| metric_Y | |

### Ejemplo

`Metric 1 > Metric 2`

## Mayor o igual que

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MAYOR O IGUAL QUE()]**


Mayor o igual que. El resultado es un 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| metric_X |  |
| metric_Y |  |

### Ejemplo

`Metric 1 >= Metric 2`



## Coseno hiperbólico

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL COSENO HIPERBÓLICO(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | El ángulo en radianes del que se desea encontrar el coseno hiperbólico |



## Seno hiperbólico

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL SENO HIPERBÓLICO(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | El ángulo en radianes del que se desea encontrar el seno hiperbólico |



## Tangente hiperbólica

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENTE HIPERBÓLICA(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | El ángulo en radianes del que se desea encontrar la tangente hiperbólica |


## Si

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL IF(prueba_lógica, valor_si_verdadero, valor_si_falso)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| logical_test | Requerido. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE |
| value_if_true | El valor que desea que sea devuelto si el argumento logical_test se evalúa como TRUE. (Este argumento es 0 de forma predeterminada si no se incluye). |
| value_if_false | El valor que desee que se devuelva si el argumento logical_test evalúa en FALSE. (El valor predeterminado de este argumento es 0 si no se incluye.) |


## Menor que

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MENOR QUE()]**


El resultado es un 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| metric_X | |
| metric_Y | |


### Ejemplo

`Metric 1 < Metric 2`

## Menor o igual que

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL MENOR O IGUAL QUE()]**

Menor o igual que. El resultado es un 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| metric_X | |
| metric_Y | |

### Ejemplo

`Metric 1 <= Metric 2`



## Regresión lineal: coeficiente de correlación

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN LINEAL: COEFICIENTE DE CORRELACIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión lineal: intersección

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN LINEAL: INTERSECCIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión lineal: Y predicha

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN LINEAL: Y PREDICHA(metric_X, metric_Y, include_zeros)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión lineal: pendiente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN LINEAL: PENDIENTE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Logaritmo decimal

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | Número real positivo cuyo logaritmo en base 10 se desea obtener |


## Regresión logarítmica: coeficiente de correlación

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN DE REGISTRO: COEFICIENTE DE CORRELACIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión logarítmica: intersección

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN DE REGISTRO: INTERSECCIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión logarítmica: Y predicha

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN DE REGISTRO: Y PREDICHA (metric_X, metric_Y, include_zeros)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión logarítmica: pendiente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN DE REGISTRO: PENDIENTE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Logaritmo natural

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGISTRO NATURAL(métrica)]**


Devuelve el logaritmo natural de un número. Los logaritmos naturales se basan en la constante e (2,71828182845904). El logaritmo natural es la inversa de la función exponencial.


| Argumento | Descripción |
|---|---|
| metric | El número real positivo cuyo logaritmo natural se desea obtener |



## No

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL NO(lógico)]**


Negación como booleano. El resultado es 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| lógico | Requerido. Un valor o expresión que puede evaluarse como TRUE o FALSE |



## Distinto a

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL NO IGUAL()]**


No es igual. El resultado es un 0 (falso) o 1 (verdadero).


| Argumento | Descripción |
|---|---|
| metric_X | |
| metric_Y | |

### Ejemplo

`Metric 1 != Metric 2`


## O

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL O(prueba_lógica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| logical_test | Requiere al menos un parámetro, pero puede tomar cualquier número de parámetros. Cualquier valor o expresión que pueda evaluarse como TRUE o FALSE |


>[!NOTE]
>
>0 (cero) significa Falso y cualquier otro valor es Verdadero.


## Pi

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Devuelve Pi: 3.14159...


## Regresión potencial: coeficiente de correlación

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN DE POTENCIA: COEFICIENTE DE CORRELACIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión potencial: intersección

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN DE POTENCIA: INTERSECCIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión potencial: Y predicha

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN DE POTENCIA: Y PREDICHA(metric_X, metric_Y, include_zeros)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión potencial: pendiente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN DE POTENCIA: PENDIENTE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión cuadrática: coeficiente de correlación

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN CUADRÁTICA: COEFICIENTE DE CORRELACIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |

## Regresión cuadrática: intersección

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN CUADRÁTICA: INTERSECCIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión cuadrática: Y predicha

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN CUADRÁTICA: Y PREDICHA(metric_X, metric_Y, include_zeros)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |

## Regresión cuadrática: pendiente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN CUADRÁTICA: PENDIENTE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |



## Regresión recíproca: coeficiente de correlación

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN RECÍPROCA: COEFICIENTE DE CORRELACIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría correlacionar con metric_Y |
| metric_Y | Una métrica que le gustaría correlacionar con metric_X |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión recíproca: intersección

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN RECÍPROCA: INTERSECCIÓN(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión recíproca: Y predicha

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN RECÍPROCA: Y PREDICHA(metric_X, metric_Y, include_zeros)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Regresión recíproca: pendiente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESIÓN RECÍPROCA: PENDIENTE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabla]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric_X | Una métrica que le gustaría designar como datos dependientes |
| metric_Y | Una métrica que le gustaría designar como datos independientes |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |




## Seno

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL SENO(métrica)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | El ángulo en radianes del que desea obtener el seno |




## Unidad tipificada

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PUNTUACIÓN-T(métrica, include_zeros)]**


La desviación de [MEDIA](cm-functions.md#mean), dividida por la desviación estándar. Alias de [puntuación Z](#z-score).


| Argumento | Descripción |
|---|---|
| metric | La métrica para la cual desea la puntuación T |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |


## Prueba T

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(métrica, grados, colas)]**


Realiza una prueba T con una distribución m con una puntuación t de x y n grados de libertad.


| Argumento | Descripción |
|---|---|
| metric | La métrica en la que desea realizar una prueba T |
| grados | Los grados de libertad |
| colas | Longitud de la cola que se utilizará para realizar la prueba T |

### Detalles

La firma es T-TEST (métrica, grados, colas). Debajo, simplemente llama a ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Esta función es similar a **[Z-TEST](#z-test)**, que ejecuta ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**.

- ***m*** es el número de colas.
- ***n*** es el grado de libertad y debe ser un número constante para todo el informe, es decir, que no cambie de fila a fila.
- ***x*** es la estadística de prueba T y, a menudo, sería una fórmula (por ejemplo, **[PUNTUACIÓN Z](#z-score)**) basada en una métrica y evaluada en cada fila.

El valor de retorno es la probabilidad de ver la estadística test x dados los grados de libertad y el número de colas.

**Ejemplos:**

1. Utilice la función para buscar periféricos:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Combine la función con **[IF](#if)** para omitir las tasas de devolución muy altas o bajas y cuente las sesiones en todo lo demás:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```




## Tangente

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENTE(métrica)]**


Devuelve la tangente de un ángulo determinado. Si el ángulo es en grados, multiplique el ángulo por PI( )/180.


| Argumento | Descripción |
|---|---|
| metric | Ángulo en radianes del que se desea obtener la tangente |



## Variable estandarizada

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PUNTUACIÓN Z(métrica, include_zeros)]**


[!BADGE Fila]{type="Neutral"}


| Argumento | Descripción |
|---|---|
| metric | La métrica para la cual desea la puntuación Z |
| include_zeros | Indica si se deben incluir o no valores cero en los cálculos |

Una puntuación Z de 0 (cero) implica que la puntuación es la misma que la media. Una variable estandarizada puede ser positiva o negativa, lo cual indica si está por encima o por debajo de la media y a cuantas desviaciones estándar.

La ecuación de variable estandarizada es:

![](assets/z_score.png)

Donde ***[!DNL x]*** es la puntuación sin procesar, ***[!DNL μ]*** es la media de población y ***[!DNL σ]*** es la desviación estándar de la población.

>[!NOTE]
>
>***[!DNL μ]*** (mu) y ***[!DNL σ]*** (sigma) se calculan automáticamente a partir de la métrica.



## Prueba Z

![Efecto](/help/assets/icons/Effect.svg) **[!UICONTROL PRUEBA Z(metric_tails)]**


Realiza una prueba z con una distribución n con una puntuación z de x.


| Argumento | Descripción |
|---|---|
| metric | La métrica en la que desea realizar una prueba Z |
| colas | Longitud de la cola que se utilizará para realizar la prueba Z |

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