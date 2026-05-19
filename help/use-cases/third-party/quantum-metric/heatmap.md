---
title: Uso de mapas de calor de métricas cuánticas con Customer Journey Analytics
description: Comprenda mejor la participación a nivel de página y optimice las páginas en función del comportamiento del consumidor mediante los datos del mapa de calor de la métrica cuántica.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
autotag-review: '2026-05-19T09:50:41.180Z'
TQID: 'https://experienceleague.adobe.com/EvPGghY3E7eoiJb6TcWnaOhneS6oQJj4bcwU3K2v3Ng'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 1%

---

# Uso de mapas de calor de métricas cuánticas con Customer Journey Analytics

La vinculación de la asignación de calor de métricas cuánticas a datos de CJA le permite comprender mejor la participación a nivel de página y optimizar las páginas en función del comportamiento de los consumidores. Workspace se puede utilizar para comprender los flujos de usuarios consumidores y ver qué rutas siguen los consumidores de una página a otra. A continuación, puede hacer clic en las URL de la página con hipervínculos para crear un mapa de calor visual de cómo los usuarios interactúan con el contenido. Al vincular la asignación de calor de métrica cuántica a CJA, ahora puede asociar interacciones a nivel de página con resultados empresariales, llevando el análisis al siguiente nivel.

La tabla muestra todas las sesiones de ese segmento y puede hacer clic en cualquiera de ellas para explorarlas más en QM.  Obtenga más información acerca de la reproducción de la sesión de métricas cuánticas en https://www.quantummetric.com/platform/session-replay

## Requisitos previos

Debe tener derecho al paquete **Operaciones de experiencia de usuario** de Quantum Metric para acceder a las capacidades de mapa de calor de Quantum Metric.

## Paso 1: Configuración de vínculos en Analysis Workspace

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Workspace]** en el menú superior.
1. Seleccione un proyecto existente o cree un proyecto.
1. Crear [tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Arrastre la dimensión URL de la página al lienzo de Workspace.
1. Haga clic con el botón secundario en el encabezado de columna de dimensión y, a continuación, seleccione **[!UICONTROL Crear hipervínculos para todos los elementos de dimensión]**.
1. Seleccione **[!UICONTROL Crear una dirección URL personalizada]**.
1. Pegue la siguiente estructura de URL:

   ```
   $value?qm-visible=true
   ```

1. Haga clic en **[!UICONTROL Crear]**.
1. Pruebe uno de los vínculos para ver si se abre en la dirección URL con la extensión de métrica cuántica visible. Estos vínculos se abren en una nueva pestaña para que el proyecto de Workspace permanezca abierto.

![Mapa de calor](assets/heatmap.png)

## Paso 2: Ver los mapas de calor haciendo clic en los vínculos de Customer Journey Analytics

Una vez que haya encontrado una página que desea explorar en la asignación de calor, puede aplicarla al panel deseado. La tabla devuelve una URL que permite explorar mapas de calor, profundidad de desplazamiento y zonas clave para la interacción mediante la métrica cuántica. Consulte [Descripción general del producto del mapa de calor de la métrica cuántica](https://www.quantummetric.com/platform/interaction-heatmaps) para obtener más información. También puede ponerse en contacto con el representante de atención al cliente de la métrica cuántica o enviar una solicitud a través del [Portal de solicitudes de clientes de la métrica cuántica](https://community.quantummetric.com/s/public-support-page).
