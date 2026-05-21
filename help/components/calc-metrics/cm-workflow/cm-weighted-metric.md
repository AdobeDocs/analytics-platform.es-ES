---
description: Muestra ejemplos de métricas calculadas.
title: Ejemplos de métricas calculadas
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
TQID: https://experienceleague.adobe.com/awAk0boIVigYBssgLcSz3t-5eExHhasCVDtwoa3v19k
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 252
ht-degree: 4%

---

# Ejemplos de métricas calculadas

Este artículo muestra ejemplos de cómo definir métricas calculadas más avanzadas.

## Porcentaje de rebote

Desea calcular la tasa de salida hacia otro sitio.

+++ Detalles

La definición de una devolución está sujeta a otra discusión, pero para este ejemplo, se define un segmento de Eventos rechazados en el que Inicio de sesión es igual a 1 y Fin de sesión es igual a 1. Utilice este segmento para definir la tasa de sesiones devueltas a las sesiones.


### Segmento

![Eventos de rebote](assets/example-bounce-bouncedevents.png)

### Métrica calculada

![Porcentaje de rebote](assets/example-bounce-rate.png)


### Campos derivados

También puede definir una [tasa de salida hacia otro sitio usando campos derivados](/help/data-views/derived-fields/derived-fields.md#bounces).

Los campos derivados forman parte de una vista de datos que tiene la ventaja de que no todos los usuarios pueden anular o modificar la definición de una métrica de Tasa de salida hacia otro sitio. Esa ventaja también introdujo una limitación. Los usuarios que no tienen acceso a una vista de datos no pueden utilizar campos derivados y tienen que recurrir a segmentos y métricas calculadas para definir una tasa de salida hacia otro sitio.

Consulte para obtener más información básica sobre cómo calcular las devoluciones y la tasa de devoluciones en Customer Journey Analytics, esta [publicación de blog](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446?profile.language=es).

+++


## Vistas de página condicionales

Desea definir una métrica calculada que calcule solamente las vistas de página de las páginas que se han visitado en más de 100 sesiones.

+++ Detalles 

![Vistas de página condicionales](assets/conditional-page-views.png)

+++

## Vistas de página de las principales sesiones del 30 %

Desea definir una métrica calculada que calcule solamente las vistas de página de las sesiones del 30 % principales.

+++ Detalles

![Vistas de página del 30 % principales](assets/top30-page-views.png)

+++
