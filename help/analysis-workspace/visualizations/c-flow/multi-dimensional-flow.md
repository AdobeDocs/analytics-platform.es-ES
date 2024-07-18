---
description: Un flujo interdimensional le permite examinar las rutas del usuario entre diversas dimensiones.
title: Flujos interdimensionales
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 73%

---

# Flujos interdimensionales

Un flujo interdimensional le permite examinar las rutas del usuario entre diversas dimensiones.

Existe una etiqueta de dimensión en la parte superior de cada columna Flujo que hace que el uso de varias dimensiones en una visualización de flujo sea más intuitivo:

![Flujo interdimensional que resalta varias dimensiones, incluidas Producto, Página, Versión del SO y Tiempo empleado.](assets/flow.png)

Observaremos dos casos de uso: un caso de uso de aplicación y un caso de uso web.

## Caso de uso uno: app

La dimensión [!UICONTROL Nombre de la acción] se ha añadido al flujo, donde el principal elemento devuelto es [!UICONTROL ItemAdded]:

![Flujo que muestra el elemento agregado.](assets/multi-dimensional-flow.png)

Para explorar la interacción entre pantallas/páginas y acciones en esta aplicación, puede arrastrar la dimensión de página a múltiples lugares, en función de qué desee explorar:

* Arrástrela al final de la zona de colocación (dentro de la zona rectangular enmarcada en negro que aparece) para **sustituir** a los principales resultados en los extremos:

  ![Flujo que muestra la dimensión Página arrastrada a las diversas áreas.](assets/multi-dimensional-flow2.png) ![Diagrama de flujo que muestra los elementos arrastrados.](assets/multi-dimensional-flow3.png)

* Arrástrela al espacio en blanco al final (observe el horquillado negro) para **añadir en** la visualización:

  ![Flujo que muestra la dimensión Página arrastrada al espacio en blanco al final.](assets/multi-dimensional-flow4.png)

Este es el resultado si decide sustituir el elemento ItemScaled de la columna derecha por la dimensión Página. El resultado principal ahora cambia por el resultado principal de la dimensión Página:

![Un valor fLow que muestra los resultados de la dimensión Página en la parte superior de la lista.](assets/multi-dimensional-flow5.png)

Ahora puede ver cómo se mueven los clientes entre las acciones y páginas. Puede explorar aún más el flujo si hace clic en distintos nodos:

![Flujo que muestra los elementos agregados, los elementos arrastrados y la vista principal.](assets/multi-dimensional-flow6.png)

Esto es lo que sucede si añade otra dimensión Nombre de la acción al final de la visualización:

![Flujo que muestra el nombre de la acción agregado.](assets/multi-dimensional-flow7.png)

Esto permite obtener información exhaustiva y realizar posibles cambios a la aplicación que está analizando.

## Caso de uso dos: web

Este caso de uso le muestra cómo puede analizar qué campañas obtienen el máximo número de entradas al sitio web.

Arrastre la dimensión Nombre de campaña a un nuevo flujo:

![Flujo que muestra la dimensión Nombre de campaña arrastrado a un nuevo flujo.](assets/multi-dimensional-flow8.png)

Ahora deseo ver a qué páginas están impulsando el tráfico estas campañas, por lo que arrastro la dimensión Página a la derecha de los resultados de flujo para añadirlos a la visualización:

![Flujo que muestra la dimensión Página arrastrada a la derecha de los resultados del flujo.](assets/multi-dimensional-flow9.png)
