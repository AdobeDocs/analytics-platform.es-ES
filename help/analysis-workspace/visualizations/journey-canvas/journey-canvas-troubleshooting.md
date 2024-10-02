---
description: Ejemplos al configurar una visualización de lienzo de Recorrido
title: ejemplos de lienzo de recorrido
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: c79d1174d78c0bfb1c9b082eb93855bdab4283e4
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 1%

---

# solución de problemas de lienzo de recorrido

{{release-limited-testing}}

La visualización del lienzo de Recorrido le permite analizar y obtener perspectivas profundas sobre los recorridos que proporciona a sus usuarios y clientes.

Para obtener más información sobre el lienzo de Recorrido, vea [Información general sobre el lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) y [Configuración de una visualización del lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


## Compatibilidad entre la métrica del contenedor y la métrica principal

Puede configurar el contenedor del lienzo de Recorrido para que sea Persona (que utiliza la métrica Personas ) o Sesión (que utiliza la métrica Sesiones ).

Al elegir una métrica principal o secundaria, asegúrese de elegir una métrica que sea compatible con la métrica de contenedor seleccionada actualmente. La mayoría de las métricas son compatibles con las métricas de contenedor disponibles. Sin embargo, deben evitarse algunas combinaciones de métricas de contenedor y métricas principales o secundarias.

Por ejemplo, si utiliza Persona como contenedor con Sesión como métrica principal o secundaria


| Contenedor | Métrica principal o secundaria | Resultado |
|---------|----------|---------|
| Personas | Sesión | Esta combinación puede dar lugar a resultados no deseados. En concreto, el resultado de esta combinación puede ser |
| A2 | B2 | C2 |
| A3 | B3 | C3 |


## Porcentajes que superan el 100%

Las siguientes configuraciones pueden dar como resultado nodos que muestran porcentajes que superan el 100%:

* Cuando el campo **[!UICONTROL Valor porcentual]** está establecido en **[!UICONTROL Porcentaje del total]** o **[!UICONTROL Porcentaje del nodo de inicio]**, y se selecciona una métrica principal que genera menos datos para el nodo de inicio que en los nodos subsiguientes.

  Por ejemplo, si se seleccionan los ingresos como métrica principal y no se obtienen ingresos en la métrica principal, en cualquier nodo en el que se obtengan ingresos se muestran como superiores al 100%.

## Nodos que tienen un porcentaje o valor mayor que los nodos anteriores

## Nodos que tienen un porcentaje o valor mayor que los nodos anteriores

## Los nodos que se producen más adelante en el recorrido tienen un porcentaje o valor mayor que los que se producen más temprano

## Nodo con un porcentaje o valor mayor que los nodos que lo preceden en el recorrido

## Nodos con un porcentaje o valor mayor que los nodos anteriores

## Nodos

## Un porcentaje o valor mayor en los nodos siguientes

## Un recorrido sin forma de embudo

En el lienzo de Recorrido, es posible que los nodos que se producen más adelante en el recorrido muestren un porcentaje o un recuento de números mayor que los que se producen más temprano en el recorrido.

En otras palabras, a diferencia de las visualizaciones de visitas en el orden previsto, que siempre tienen forma de embudo (con una participación que disminuye con cada paso), las visualizaciones de lienzo de Recorrido pueden tener una mayor participación en los pasos posteriores del recorrido.

Considere un recorrido con las siguientes características:

* El recorrido contiene 3 nodos: nodo A —> nodo B —> nodo C

* El campo **[!UICONTROL Valor porcentual]** se ha establecido en **[!UICONTROL Porcentaje del total]**

* **[!UICONTROL Persona]** se ha establecido como contenedor

* **[!UICONTROL Evento]** se ha establecido como métrica principal

En este escenario, supongamos que un visitante visitó el nodo A, el nodo B y, a continuación, el nodo C. Cada una de estas visitas se cuenta como un solo evento en cada nodo, ya que se visitaron en el orden definido por el recorrido.

En una visita posterior al sitio, el visitante solo visita el nodo C, lo que da como resultado un evento adicional en el nodo C.

En este caso, los nodos A y B mostrarían cada uno 1 evento y 100%, mientras que el nodo C mostraría 2 eventos y 200%.

Por otro lado, si Sesión se estableciera como contenedor, los nodos A, B y C mostrarían cada uno 1 evento y el 100 %, ya que la visita posterior al sitio donde el visitante visitó solo el nodo C no habría cumplido los requisitos de recorrido, ya que el nodo A y el nodo B no se visitaron antes de visitar el nodo C.
