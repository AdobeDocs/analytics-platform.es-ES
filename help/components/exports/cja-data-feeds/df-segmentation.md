---
title: Segmentación en fuentes de datos
description: Obtenga información sobre cómo aplicar segmentos a fuentes de datos de Customer Journey Analytics y comprenda cómo los segmentos de intervalo de fechas interactúan con la ventana de informes de la fuente.
keywords: flujo de navegación;fuente de datos;fuente de datos;segmentación;segmentos;intervalo de fechas
feature: Components
hide: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: c7fc5df2a0fd7393b48bfe6bdfa7dccdfffde46c
workflow-type: tm+mt
source-wordcount: 357
ht-degree: 0%

---


# Segmentación en fuentes de datos

{{release-limited-testing}}

Las fuentes de datos en Customer Journey Analytics admiten la segmentación, lo que permite filtrar qué filas se incluyen en cada entrega de fuente. Puede aplicar segmentos en el nivel de vista de datos, de fuente o en ambos.

## Dónde se aplican los segmentos

Puede aplicar segmentos a una fuente de datos en dos lugares:

- **Vista de datos**: Un segmento configurado en la vista de datos que se aplica a todas las fuentes que usan esa vista de datos.
- **Fuente de datos**: Un segmento aplicado directamente a una fuente individual, además de cualquier segmento de vista de datos.

Cuando se configuran ambos, Customer Journey Analytics los combina; solo se incluyen en la salida de la fuente las filas que satisfacen ambos segmentos.

## Segmentos que incluyen un intervalo de fechas

Puede utilizar segmentos que incluyan intervalos de fechas dentro de una fuente de datos. Sin embargo, la ventana de creación de informes siempre se define mediante la entrega programada de la fuente (por hora o por día). Si un segmento contiene un intervalo de fechas, filtra filas dentro de la ventana de fuente de datos sin desplazar ni expandir la propia ventana.

En cambio, si se aplica un segmento que incluye un intervalo de fechas, la ventana de informes activa cambia para coincidir con el intervalo de fechas del segmento.

## Calificación de segmentos y el intervalo de fechas retrospectivo

Para los segmentos que utilizan un contenedor de persona o sesión, la calificación está determinada por la configuración **Intervalo de fechas de retrospectiva**, no solo por la ventana de envío. Si una persona se califica dentro del intervalo de fechas retrospectivas, se incluyen todos los eventos de esa persona en la ventana de envío. La configuración del contenedor determina el ámbito:

- **Contenedor de eventos**: solo se incluyen los eventos que coinciden con los criterios del segmento en la ventana de envío.
- **Contenedor de sesión**: se incluyen todos los eventos de las sesiones de calificación dentro de la ventana de entrega, donde la calificación de la sesión se evalúa dentro del intervalo de fechas retrospectivo.
- **Contenedor de persona**: todos los eventos de la ventana de envío se incluyen para cualquier persona que cumpla los requisitos durante el intervalo de fechas de retrospectiva.

Para obtener más información sobre el intervalo de fechas de retrospectiva y cómo afecta a la calificación de segmentos, consulte [Crear una fuente de datos](/help/components/exports/cja-data-feeds/create-feed.md).

