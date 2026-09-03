---
description: Descubra cómo un flujo interdimensional le permite examinar las rutas del usuario entre diversas dimensiones.
title: Flujos interdimensionales
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
autotag-review: '2026-05-19T08:41:06.716Z'
TQID: 'https://experienceleague.adobe.com/1er03t5uOypgXP6sjFW3z7vbN8IucVak2OiDeUG-OaU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 89%

---

# Flujos interdimensionales

Un flujo interdimensional le permite examinar rutas de usuario entre varias dimensiones. Este artículo muestra cómo utilizar este flujo para dos casos de uso: interacciones y eventos de aplicaciones móviles y cómo las campañas generan visitas web

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Eventos e interacciones de aplicaciones móviles

La dimensión [!UICONTROL Nombre de pantalla] se usa en este flujo de ejemplo para ver cómo utilizan los usuarios las distintas pantallas (escenas) de la aplicación. La pantalla principal devuelta es **[!UICONTROL luma: content: ios: en: home]**, que es la página principal de la aplicación:

![Un flujo que muestra el elemento añadido.](assets/flowapp.png)

Para explorar la interacción entre pantallas y tipos de eventos (como añadir al carro de compras, compras, etc.) en esta aplicación, arrastre y suelte la dimensión **[!UICONTROL Tipos de eventos]**:

* Sobre cualquier paso disponible en el flujo, para reemplazar esa dimensión:

  ![Un flujo que muestra la dimensión Página arrastrada a varias áreas.](assets/flowapp-replace.png)

* Fuera de la visualización de flujo actual, para añadir la dimensión:

  ![Un flujo que muestra la dimensión Página arrastrada al espacio en blanco al final.](assets/flowapp-add.png)

La siguiente visualización de flujo muestra el resultado de añadir la dimensión **[!UICONTROL Tipos de eventos]**. La visualización proporciona perspectivas sobre cómo los usuarios de aplicaciones móviles se mueven por varias pantallas de la aplicación antes de añadir productos al carro de compras, cerrar la aplicación, que se les presente una oferta y mucho más.

![Un valor de flujo que muestra los resultados de la dimensión Página en la parte superior de la lista.](assets/flowapp-result.png)

## Cómo impulsan las campañas las visitas a la web

Desea analizar qué campañas generan visitas al sitio web. Crea una visualización de flujo con **[!UICONTROL Nombre de campaña]** como dimensión

![Dimensión de nombre de campaña web de flujo](assets/flowweb.png)

Reemplace la última dimensión **[!UICONTROL Nombre de campaña]** por la dimensión **[!UICONTROL Nombre de página con formato]** y añada otra dimensión **[!UICONTROL Nombre de página con formato]** al final de la visualización del flujo.

![Nombre de campaña web de flujo y dimensión de página web](assets/flowweb-replace.png)

Puede pasar el puntero por encima de cualquiera de los flujos para ver más detalles. Por ejemplo, qué campañas han resultado en un cierre de compra del carro de compras.

![Desplazamiento sobre nombre de campaña web de flujo y dimensión de página web](assets/flowweb-hover.png)
