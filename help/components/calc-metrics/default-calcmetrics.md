---
description: Adobe proporciona varias métricas calculadas que puede utilizar. Esta página enumera dichas métricas y los usos a los que están destinadas.
title: Métricas calculadas predeterminadas
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 60%

---

# Métricas calculadas predeterminadas

Customer Journey Analytics proporciona varias métricas calculadas para cubrir los casos de uso más comunes. Estas métricas calculadas están disponibles de forma predeterminada en Analysis Workspace.

A continuación se muestra una lista de cada métrica calculada proporcionada por Adobe, con su función deseada y la fórmula subyacente utilizada para calcularla:

>[!NOTE]
>
>Además de las métricas calculadas predeterminadas que se describen en esta página, también puede agregar métricas calculadas adicionales a una vista de datos.
>
>Puede:
> * Añada métricas calculadas predeterminadas para medios de streaming, como se describe en [Métricas calculadas](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Cree métricas calculadas personalizadas a partir de métricas existentes, tal como se describe en [Métricas calculadas y calculadas avanzadas (derivadas)](/help/components/calc-metrics/cm-adv-functions.md).



| Nombre de métrica calculada | Función | Fórmula |
|---------|----------|---------|
| Tasa de devoluciones | La proporción de visitas que contenían exactamente un evento en comparación con el número de visitas en esa página. Esto puede ayudarle a comprender qué elementos de dimensión tienen la tasa de salida hacia otro sitio más alta o a ver una tasa de salida hacia otro sitio total agregada a lo largo del tiempo. | `[Bounces] / [Entries]` |
| Ingresos/Visitante | Cantidad promedio de ingresos generados por cada visitante individual del sitio. | `[Revenue] / [Unique Visitors]` |
| Pedidos/Visitante | El número promedio de pedidos o transacciones generados por cada visitante individual del sitio | `[Orders] / [Unique Visitors]` |
| Ingresos / Visitas | Cantidad promedio de ingresos generados por una sola visita al sitio. | `[Revenue] / [Visits]` |
| Ingresos / Pedido | Cantidad media de ingresos generados por cada transacción o pedido completado en el sitio. | `[Revenue] / [Orders]` |
| Pedidos/Visitas | El porcentaje de visitas al sitio que genera una transacción completada. | `[Orders] / [Visits]` |
| Vistas de página/Visitas | Promedio de páginas que ve un usuario durante una sola visita al sitio. | `[Page Views] / [Visits]` |
| Visitas/Visitante | Media de visitas que realiza un visitante único al sitio. | `[Visits] / [Unique Visitors]` |
| Recargas / Vistas de página | Porcentaje de vistas de página que resultaron en una recarga o actualización de la página. | `[Reloads] / [Page Views]` |
| Tasa de salida hacia otro sitio ponderada | Función | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Asistencia para pedidos | Número de veces que un canal o fuente contribuyó al recorrido de un cliente hacia la realización de una compra, pero no resultó en la compra final. | `[Orders (Visit Participation)] - [Orders]` |
| Tasa de salida | Porcentaje de visitantes que abandonan el sitio después de ver una página en particular. | `[Exits] / [Visits]` |
| Tasa de entrada | Porcentaje de visitantes que entraron al sitio en una página determinada, comparado con el número total de sesiones en el sitio. | `[Entries] / [Visits]` |
| Promedio de tiempo en el sitio | Cantidad promedio de tiempo que un visitante pasa en el sitio antes de salir o navegar. | `[Average Time Spent on Site (Seconds)]` |
| Tiempo empleado/usuario (estado) | Cantidad de tiempo que el visitante promedio pasa en un estado determinado mientras está en el sitio | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Usuarios (móvil) | Número de usuarios de una aplicación móvil | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Usuarios de aplicación | Número de usuarios de una aplicación móvil | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Vistas de estado | Número de visualizaciones de los distintos estados o pantallas de la aplicación | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| Acciones | Número de acciones total que se llevan a cabo en la aplicación | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| Clics en vínculos de adquisición | Número de veces que las personas hacen clic en un vínculo diseñado para conducir el tráfico al sitio. | `[Campaign Click-throughs]` |
| Velocidad de página | Número de vistas de página adicionales que genera un fragmento de contenido. Esto puede ayudarle a determinar qué contenido genera participación adicional. | `[Page Views] / [Visits]` |
| Tasa de conversión | Porcentaje de visitantes que realizaron una acción deseada, como una compra. | `[Orders] / [Visits]` |
| Longitud promedio de la sesión (móvil) | Cantidad promedio de tiempo que los visitantes invierten en el sitio durante una sola sesión. | En blanco |
| Alcance del ID de Experience Cloud | Porcentaje de visitantes que tienen un ID de Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Velocidad del contenido | La velocidad a la que se crea y publica nuevo contenido en el sitio y la velocidad con la que genera la participación del usuario. | `[Page Views] / [Visits]` |
| Visitantes únicos/Visitantes únicos de ITP 2.1 | Porcentaje de visitantes únicos que utilizan un explorador afectado por las limitaciones de cookies de ITP 2.1. En otras palabras, los clientes que no utilizan una implementación de CNAME. (Esto se aplica a los clientes que configuran cookies a través de JavaScript del lado del cliente). | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| Visitantes únicos/Visitantes únicos que regresan después de 7 días | Porcentaje de visitantes únicos que regresan después de un período de 7 días o más. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| Vistas de página/Visitante único | Promedio de páginas vistas por cada visitante único del sitio. | `[Page Views] / [Unique Visitors]` |
| Visitas/Visitantes | Media de visitas que realiza un visitante único al sitio . | `[Visits] / [Unique Visitors]` |
| Visitantes únicos estimados (ITP 2.1) | Para los visitantes de ITP (usuarios en navegadores Safari), divida los visitantes únicos entre 2 o menos. Esta métrica calculada supone que se configuran cookies mediante JavaScript del lado del cliente (no utilizando una implementación CNAME). Las implementaciones que establecen cookies mediante JavaScript del lado del cliente se vieron afectadas a partir de ITP 2.1. Consulte [Prevención inteligente del seguimiento](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) para obtener más información. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| Vistas de página/Visitantes únicos estimados (ITP 2.1) | Número promedio de páginas vistas para Visitantes únicos estimados (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
