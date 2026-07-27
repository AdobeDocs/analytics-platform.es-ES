---
title: Segmentación en fuentes de datos de Customer Journey Analytics
description: Obtenga información sobre cómo aplicar segmentos a fuentes de datos de Customer Journey Analytics y comprenda cómo los segmentos de intervalo de fechas interactúan con la ventana de informes de la fuente.
keywords: flujo de navegación;fuente de datos;fuente de datos;segmentación;segmentos;intervalo de fechas
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: f36723dab5500f728dd9ec267d97305aff604149
workflow-type: tm+mt
source-wordcount: 659
ht-degree: 2%

---


# Segmentación en fuentes de datos

{{release-limited-testing}}

Las fuentes de datos en Customer Journey Analytics admiten la segmentación, lo que permite filtrar qué filas se incluyen en cada entrega de fuente. Puede aplicar segmentos en el nivel de vista de datos, de fuente o en ambos.

## Dónde se aplican los segmentos

Puede aplicar segmentos a una fuente de datos en dos lugares:

- **Vista de datos**: Un segmento configurado en la vista de datos que se aplica a todas las fuentes que usan esa vista de datos.
- **Fuente de datos**: Un segmento aplicado directamente a una fuente individual, además de cualquier segmento de vista de datos.

Cuando se configuran ambos, Customer Journey Analytics los combina; solo se incluyen en la salida de la fuente las filas que satisfacen ambos segmentos.

## Segmentos de intervalo de fecha

Los segmentos que hacen referencia a intervalos de fechas son compatibles con las fuentes de datos. Sin embargo, el comportamiento difiere del de Analysis Workspace de una manera importante: las condiciones de **intervalo de fechas de un segmento no anulan el intervalo de fechas de la fuente que genera el informe.**

En Analysis Workspace, al aplicar un segmento de intervalo de fechas, la ventana de informes activa cambia para coincidir con el intervalo de fechas del segmento. En las fuentes de datos, la ventana de creación de informes siempre se define mediante la entrega programada de la fuente (por hora o por día). Un segmento con una condición de intervalo de fechas filtra filas dentro de esa ventana; no desplaza ni expande la propia ventana.

Este diseño es intencional. Si se permite que los segmentos de intervalo de fechas anulen la ventana de informes, una fuente por hora podría ofrecer una ventana de datos mucho más grande de lo esperado, lo que produciría una duplicación de datos o un volumen de salida excesivo.

### Ejemplos

**Ejemplo 1 — Segmento que incluye eventos de una fecha específica**

Supongamos que aplica un segmento que devuelve solo eventos del 1 de julio y ejecuta la fuente para el 22 de julio:

- La ventana de entrega de fuentes permanece el 22 de julio.
- El segmento filtra todas las filas, ya que ningún evento de la ventana del 22 de julio coincide con los criterios del 1 de julio. La fuente se ejecuta, pero no envía filas.
- Si ejecuta un relleno para el 1 de julio, el segmento se comporta como se espera: solo se incluyen los eventos que coinciden con los criterios del 1 de julio.

**Ejemplo 2 — Segmento que excluye eventos de una fecha específica**

Supongamos que aplica un segmento que excluye todos los eventos con un pedido el 1 de julio y ejecuta la fuente para el 22 de julio:

- El segmento se aplica a los datos del 22 de julio. Como no hay eventos del 1 de julio en la ventana del 22 de julio, no se excluye nada y se entregan todas las filas.
- Si ejecuta un relleno para el 1 de julio, el segmento excluye las filas relevantes según lo esperado.

## Segmentos con varias condiciones

Para los segmentos que combinan condiciones de intervalo de fechas con otros criterios, Customer Journey Analytics evalúa la parte del intervalo de fechas únicamente como un filtro de fila, no como una anulación de la ventana de creación de informes. Todas las condiciones del segmento se respetan dentro de la ventana de envío de la fuente.

## Calificación de segmentos y el intervalo de fechas retrospectivo

Para los segmentos que utilizan un contenedor de persona o sesión, la calificación está determinada por la configuración **Intervalo de fechas de retrospectiva**, no solo por la ventana de envío. Si una persona se califica dentro del intervalo de fechas retrospectivas, se incluyen todos los eventos de esa persona en la ventana de envío. La configuración del contenedor determina el ámbito:

- **Contenedor de eventos**: solo se incluyen los eventos que coinciden con los criterios del segmento en la ventana de envío.
- **Contenedor de sesión**: se incluyen todos los eventos de las sesiones de calificación dentro de la ventana de entrega, donde la calificación de la sesión se evalúa dentro del intervalo de fechas retrospectivo.
- **Contenedor de persona**: todos los eventos de la ventana de envío se incluyen para cualquier persona que cumpla los requisitos durante el intervalo de fechas de retrospectiva.

Para obtener más información sobre el intervalo de fechas de retrospectiva y cómo afecta a la calificación de segmentos, consulte [Crear una fuente de datos](/help/components/exports/cja-data-feeds/create-feed.md).

## Comparación con Analysis Workspace

| Comportamiento | Analysis Workspace | Fuentes de datos |
|---|---|---|
| El segmento de intervalo de fechas anula la ventana de informes | Sí | No |
| Filas de filtros de segmentos dentro de la ventana de informes | Sí | Sí |
| Se aplica el segmento de vista de datos | Sí | Sí |
| Segmento adicional aplicado directamente al envío | No | Sí |

{style="table-layout:auto"}
