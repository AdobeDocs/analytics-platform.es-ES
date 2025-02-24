---
description: Un flujo interdimensional le permite examinar las rutas del usuario entre diversas dimensiones.
title: Flujos interdimensionales
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 1eeba4dc9de52f2890cf25794e767f199a4aa04c
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 7%

---

# Flujos interdimensionales

Un flujo interdimensional le permite examinar rutas de usuario entre varias dimensiones. Este artículo muestra cómo utilizar este flujo para dos casos de uso: interacciones y eventos de aplicaciones móviles y cómo las campañas generan visitas web

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Eventos e interacciones de aplicaciones móviles

La dimensión [!UICONTROL Nombre de pantalla] se usa en este flujo de ejemplo para ver cómo utilizan los usuarios las distintas pantallas (escenas) de la aplicación. La pantalla principal devuelta es **[!UICONTROL luma: content: ios: en: home]**, que es la página principal de la aplicación:

![Flujo que muestra el elemento agregado.](assets/flowapp.png)

Para explorar la interacción entre pantallas y tipos de eventos (como agregar al carro de compras, compras, etc.) en esta aplicación, arrastre y suelte la dimensión **[!UICONTROL Tipos de eventos]**:

* Sobre cualquier paso disponible en el flujo, para reemplazar esa dimensión:

  ![Flujo que muestra la dimensión Página arrastrada a varias áreas.](assets/flowapp-replace.png)

* Fuera de la visualización de flujo actual, para añadir la dimensión:

  ![Flujo que muestra la dimensión Página arrastrada al espacio en blanco al final.](assets/flowapp-add.png)

La siguiente visualización de flujo muestra el resultado de agregar la dimensión **[!UICONTROL Tipos de eventos]**. La visualización proporciona perspectivas sobre cómo los usuarios de aplicaciones móviles se mueven por varias pantallas de la aplicación antes de añadir productos al carro de compras, cerrar la aplicación, presentar una oferta y mucho más.

![Un valor fLow que muestra los resultados de la dimensión Página en la parte superior de la lista.](assets/flowapp-result.png)

## Cómo impulsan las campañas las visitas web

Desea analizar qué campañas generan visitas al sitio web. Crea una visualización de flujo con **[!UICONTROL Campaign Name]** como dimensión

![Dimensión de nombre de campaña web de flujo](assets/flowweb.png)

Reemplace la última dimensión **[!UICONTROL Nombre de campaña]** por la dimensión **[!UICONTROL Nombre de página con formato]** y agregue otra dimensión **[!UICONTROL Nombre de página con formato]** al final de la visualización del flujo.

![Nombre de campaña web de flujo y dimensión de página web](assets/flowweb-replace.png)

Puede pasar el ratón sobre cualquiera de los flujos para ver más detalles. Por ejemplo, qué campañas han resultado en un cierre de compra del carro de compras.

![Desplazamiento de nombre de campaña web de flujo y dimensión de página web](assets/flowweb-hover.png)
