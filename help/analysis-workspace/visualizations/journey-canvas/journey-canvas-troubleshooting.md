---
description: Aprenda a utilizar la visualización del lienzo de Recorrido en Analysis Workspace para analizar los recorridos de los usuarios, las visitas en el orden previsto y las conversiones de varias rutas.
title: Resolución de problemas del lienzo de recorrido
feature: Visualizations
role: User
exl-id: f0ac3752-9244-4d9e-807b-e6471e6aa55b
autotag-review: '2026-05-19T08:43:53.628Z'
TQID: 'https://experienceleague.adobe.com/E0LdSu06SM3c1ZBnOcIz352mqIkTN7dXfH9qC1BM-4g'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1303
ht-degree: 93%

---

# Resolución de problemas del lienzo de recorrido

La visualización de lienzo de recorrido le permite analizar y obtener información detallada sobre los recorridos que proporciona a sus usuarios y clientes.

Para obtener más información sobre el lienzo de recorrido, consulte [Información general sobre el lienzo de recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) y [Configuración de una visualización de lienzo de recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

La siguiente información puede ayudarle a solucionar problemas con resultados no deseados, como los nodos que aparecen más adelante en el recorrido y que muestran un porcentaje o un recuento mayor que los nodos que aparecen antes en el recorrido.

## Nodos con un porcentaje o valor mayor que los nodos anteriores

En el lienzo de recorrido, es posible que los nodos que aparecen más adelante en el recorrido muestren un porcentaje o un recuento mayor que los que aparecen antes en el recorrido.

Es decir, a diferencia de las visualizaciones de visitas en el orden previsto, que siempre tienen forma de embudo (con una participación que disminuye con cada paso), las visualizaciones del lienzo de recorrido pueden tener una participación mayor en los pasos posteriores del recorrido que en los pasos anteriores.

Esto puede ocurrir en los siguientes escenarios:

* Cuando se utiliza una métrica principal distinta de Personas o Sesiones

* Cuando varias rutas convergen en un solo nodo

### El recorrido utiliza una métrica principal distinta de Personas o Sesiones

Dado que el lienzo de recorrido le permite utilizar cualquier métrica como métrica principal, esto se puede traducir en que los nodos que aparecen más adelante en el recorrido muestran un porcentaje o un recuento mayor que los que aparecen antes en el recorrido.

![Recorrido con nodos con un porcentaje mayor que el nodo anterior](assets/journey-canvas-higher-percentage.png)

El recorrido utilizado en los siguientes escenarios se configura con esta configuración:

* **[!UICONTROL Persona]** se establece como contenedor

* **[!UICONTROL Evento]** se establece como métrica principal

#### Escenario 1: el usuario A sigue la ruta del recorrido en la primera sesión. En una sesión posterior, el usuario tiene un evento que coincide únicamente con un nodo posterior.

Supongamos que el usuario A visita el sitio y completa el recorrido (Nodo 1: “Visitar sitio” > Nodo 2: “Ver producto A”> Nodo 3: “Cierre de compra”). Dado que el usuario A tenía un evento que coincidía con cada nodo del recorrido en orden, se cuenta un evento en cada nodo del recorrido.

Ahora, supongamos que el usuario A vuelve a visitar el sitio en una sesión posterior. Dado que el usuario A ya completó el recorrido en una sesión anterior siguiendo la ruta de recorrido, esto significa que cada vez que el usuario A tiene un evento que coincide con cualquier nodo del recorrido (incluso si el usuario A no ha seguido la ruta del recorrido en su sesión actual), se cuenta un evento en el nodo correspondiente del recorrido. Por ejemplo, si el usuario A finaliza la compra, un evento se cuenta en el nodo “Cierre de compra”. Esto puede dar como resultado un porcentaje y un número mayores en el nodo “Cierre de compra” que en el nodo anterior, “Ver producto A”.

En este ejemplo, la configuración del contenedor del recorrido de “Persona” desempeña un papel fundamental para determinar que el evento del tercer nodo (“Cierre de compra”) se cuente en la sesión posterior.

Alternativamente, si la configuración del contenedor se hubiera establecido en “Sesión”, el evento que se produjo solo en el tercer nodo de la visita posterior no se habría contabilizado en el recorrido, ya que las estadísticas que se muestran en el recorrido se restringirían a una sola sesión definida para una persona determinada. Para obtener más información acerca de la configuración del contenedor, consulte [Comenzar a crear una visualización de lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) en el artículo [Configurar una visualización de lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Escenario 2: el usuario B abandona el recorrido

Supongamos que el usuario B visita el sitio y no completa el recorrido (visita el sitio, ve el producto B y a continuación cierra la compra). En este caso, se cuenta un evento para el nodo de inicio del recorrido, “Visitar sitio”, pero un evento no se cuenta para los nodos restantes y el usuario B abandona el recorrido. Aunque el usuario B haya cerrado la compra, un evento no se cuenta en el tercer nodo (“Cierre de compra”) porque el usuario B no completó el recorrido consultando el producto A antes de finalizar la compra.

Esto se debe a que los eventos se cuentan para cada nodo solo cuando las personas siguen la “ruta final” del recorrido. Esto significa que los eventos se cuentan únicamente si la persona se mueve de un nodo al otro, independientemente de los eventos que se produzcan entre los dos nodos.

### El recorrido tiene varias rutas que convergen en un solo nodo

El lienzo de recorrido permite incluir varios nodos de inicio en un único recorrido, lo que da como resultado varias rutas. Estas rutas pueden converger en un nodo común, lo que se traduce en que los nodos que se producen más adelante en el recorrido muestran un porcentaje o un recuento mayor que los que se producen antes en el recorrido.

![Un recorrido con varias rutas convergiendo en un solo nodo](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Porcentajes de recorrido

Aunque los números mostrados en cada nodo de un recorrido permanecen constantes independientemente de lo que se seleccione en el campo **[!UICONTROL Valor porcentual]**, los porcentajes en sí mismos pueden cambiar.

Las secciones siguientes muestran cómo pueden cambiar los porcentajes para el mismo recorrido, dependiendo de cuál de las siguientes opciones esté seleccionada en el campo **[!UICONTROL Valor porcentual]**:

+++Porcentaje del nodo de inicio

Los nodos de este recorrido contienen las siguientes estadísticas cuando el campo **[!UICONTROL Valor porcentual]** se establece en **[!UICONTROL Porcentaje del nodo de inicio]**:

![Recorrido con nodos con un porcentaje mayor que el nodo anterior](assets/journey-canvas-higher-percentage.png)

| Nodo | Estadísticas |
|---------|----------|
| Nodo 1: “Visitar sitio” | En este recorrido, se registraron 354 147 eventos en el sitio dentro del rango de fecha del informe, como se muestra en el nodo inicial del recorrido, “Visitar sitio”. |
| Nodo 2: “Ver producto A” | Del número total de eventos mostrados en el nodo de inicio, el 14 % (48 394) de ellos coincidían con los criterios del segundo nodo del recorrido, “Ver producto A”. |
| Nodo 3: “Cierre de compra” | Del número total de eventos mostrados en el nodo de inicio, el 32 % (113 782) de ellos coincidían con los criterios del tercer nodo del recorrido, “Cierre de compra”. |

+++

+++Porcentaje del nodo anterior

Los nodos de este recorrido contienen las siguientes estadísticas cuando el campo **[!UICONTROL Valor porcentual]** se establece en **[!UICONTROL Porcentaje del nodo anterior]**:

![Recorrido con nodos con un porcentaje mayor que el nodo anterior](assets/journey-canvas-percentage-previous.png)

| Nodo | Estadísticas |
|---------|----------|
| Nodo 1: “Visitar sitio” | En este recorrido, se registraron 354 147 eventos en el sitio dentro del rango de fecha del informe, como se muestra en el nodo inicial del recorrido, “Visitar sitio”. |
| Nodo 2: “Ver producto A” | Del número total de eventos mostrados en el nodo anterior, el 14 % (48.394) de ellos coincidían con los criterios del segundo nodo del recorrido, “Ver producto A”. |
| Nodo 3: “Cierre de compra” | Del número total de eventos mostrados en el nodo anterior, más del 100 % (113 782) de ellos coincidían con los criterios del tercer nodo del recorrido, “Cierre de compra”. |

+++

+++Porcentaje del total

Los nodos de este recorrido contienen las siguientes estadísticas cuando el campo **[!UICONTROL Valor porcentual]** se establece en **[!UICONTROL Porcentaje del total]**:

![Recorrido con nodos con un porcentaje mayor que el nodo anterior](assets/journey-canvas-percentage-total.png)

| Nodo | Estadísticas |
|---------|----------|
| Nodo 1: “Visitar sitio” | En este recorrido, se registraron 354 147 eventos en el sitio dentro del rango de fecha del informe, como se muestra en el nodo inicial del recorrido, “Visitar sitio”. |
| Nodo 2: “Ver producto A” | Del número total de eventos, menos del 1 % (48 394) de ellos coincidían con los criterios del segundo nodo del recorrido, “Ver producto A”. |
| Nodo 3: “Cierre de compra” | Del número total de eventos, el 1 % (113 782) de ellos coincidió con los criterios del tercer nodo del recorrido, “Cierre de compra”. |

+++

## Compatibilidad entre la métrica del contenedor y la métrica principal

Puede configurar el contenedor del lienzo de recorrido para que sea Persona (que utiliza la métrica Personas ) o Sesión (que utiliza la métrica Sesiones ).

Asegúrese de elegir una métrica principal compatible con la métrica de contenedor seleccionada actualmente. La mayoría de las métricas son compatibles con las métricas de contenedor que hay disponibles. Sin embargo, se deben evitar algunas combinaciones de métricas de contenedor y métricas principales.

Por ejemplo, si se utiliza Persona como contenedor con Sesión como métrica principal, pueden producirse resultados no deseados.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
