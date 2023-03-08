---
description: Adobe proporciona varias métricas calculadas que puede utilizar. Esta página enumera dichas métricas y los usos a los que están destinadas.
title: Métricas calculadas predeterminadas
feature: Calculated Metrics
source-git-commit: 5d6942af4ac3f999c5e7fd7d6ba74a5fe7a26a9d
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 4%

---

# Métricas calculadas predeterminadas

Customer Journey Analytics proporciona varias métricas calculadas para cubrir los casos de uso más comunes. Estas métricas calculadas están disponibles de forma predeterminada en Analysis Workspace.

A continuación se muestra una lista de cada métrica calculada proporcionada por Adobe, con su función deseada y la fórmula subyacente utilizada para calcularla:

>[!NOTE]
>
>Además de las métricas calculadas predeterminadas que se describen en esta página, también puede agregar métricas calculadas adicionales a un grupo de informes.
>
>Puede:
> * Añada métricas calculadas predeterminadas para medios de streaming, como se describe en [Métricas calculadas](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Cree métricas calculadas personalizadas a partir de métricas existentes, tal como se describe en [Métricas calculadas y calculadas avanzadas (derivadas)](/help/components/calc-metrics/cm-adv-functions.md).



| Nombre de métrica calculada | Función | Fórmula |
|---------|----------|---------|
| Tasa de devoluciones | La proporción de visitas que contenían exactamente una visita en comparación con el número de visitas en esa página. Esto puede ayudarle a comprender qué elementos de dimensión tienen la tasa de salida hacia otro sitio más alta o a ver una tasa de salida hacia otro sitio total agregada a lo largo del tiempo. | `[Bounces] / [Entries]` |
| Ingresos/Visitante | Cantidad promedio de ingresos generados por cada visitante individual del sitio. | `[Revenue] / [Unique Visitors]` |
| Pedidos/Visitante | Número promedio de pedidos o transacciones generados por cada visitante individual del sitio | `[Orders] / [Unique Visitors]` |
| Ingresos / Visitas | Cantidad promedio de ingresos generados por una sola visita al sitio. | `[Revenue] / [Visits]` |
| Ingresos / Pedido | Cantidad media de ingresos generados por cada transacción o pedido completado en la dirección. | `[Revenue] / [Orders]` |
| Pedidos/Visitas | Porcentaje de visitas al sitio que resultan en una transacción completada. | `[Orders] / [Visits]` |
| Vistas de página/Visitas | Promedio de páginas que un usuario ve durante una sola visita al sitio. | `[Page Views] / [Visits]` |
| Visitas/Visitante | Número promedio de visitas que un visitante único realiza al sitio. | `[Visits] / [Unique Visitors]` |
| Recargas / Vistas de página | Porcentaje de vistas de página que resultaron en una recarga o actualización de la página. | `[Reloads] / [Page Views]` |
| Tasa de salida hacia otro sitio ponderada | Función | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Asistencia para pedidos | El número de veces que un canal o fuente contribuyó al recorrido de un cliente para realizar una compra, pero no resultó en la compra final. | `[Orders (Visit Participation)] - [Orders]` |
| Tasa de salida | El porcentaje de visitantes que abandonan el sitio después de ver una página en particular. | `[Exits] / [Visits]` |
| Tasa de entrada | El porcentaje de visitantes que entraron al sitio en una página determinada, comparado con la cantidad total de sesiones en el sitio. | `[Entries] / [Visits]` |
| Promedio de tiempo en el sitio | Cantidad promedio de tiempo que un visitante pasa en el sitio antes de salir o navegar. | `[Average Time Spent on Site (Seconds)]` |
| Tiempo empleado/usuario (estado) | Período de tiempo que el visitante promedio pasa en un estado determinado mientras está en el sitio | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Usuarios (móvil) | Número total de usuarios de una aplicación móvil | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Usuarios de aplicación | Número total de usuarios de una aplicación móvil | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Vistas de estado | Número de vistas a los diferentes estados o pantallas de la aplicación | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| Acciones | Número total de acciones realizadas en la aplicación | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| Clics en vínculos de adquisición | La cantidad de veces que las personas hacen clic en un vínculo diseñado para dirigir el tráfico al sitio. | `[Campaign Click-throughs]` |
| Velocidad de página | Número de vistas de página adicionales que genera un fragmento de contenido. Esto puede ayudarle a determinar qué contenido genera participación adicional. | `[Page Views] / [Visits]` |
| Tasa de conversión | El porcentaje de visitantes que realizaron una acción deseada, como una compra. | `[Orders] / [Visits]` |
| Longitud promedio de la sesión (móvil) | Promedio de tiempo que los visitantes pasan en el sitio durante una sola sesión. | En blanco |
| Cobertura de ID de Experience Cloud | El porcentaje de visitantes que tienen un ID de Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Velocidad del contenido | La velocidad a la que se crea y publica contenido nuevo en el sitio y la velocidad con la que genera la participación del usuario. | `[Page Views] / [Visits]` |
| Visitantes únicos/Visitantes únicos de ITP 2.1 | El porcentaje de visitantes únicos que utilizan un explorador afectado por las limitaciones de cookies de ITP 2.1. Es decir, los clientes que no utilizan una implementación CNAME. (Esto se aplica a los clientes que configuran cookies mediante JavaScript del lado del cliente). | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| Visitantes únicos/Visitantes únicos que regresan después de 7 días | El porcentaje de visitantes únicos que regresan después de un período de 7 días o más. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| Vistas de página/Visitante único | Promedio de páginas vistas para cada visitante único del sitio. | `[Page Views] / [Unique Visitors]` |
| Visitas/Visitantes | Número promedio de visitas que un visitante único realiza al sitio | `[Visits] / [Unique Visitors]` |
| Visitantes únicos estimados (ITP 2.1) | Para los visitantes de ITP (usuarios en navegadores Safari), divida los visitantes únicos entre 2 o menos. Esta métrica calculada supone que se configuran cookies mediante JavaScript del lado del cliente (no utilizando una implementación CNAME). Las implementaciones que establecen cookies mediante JavaScript del lado del cliente se vieron afectadas a partir de ITP 2.1. Consulte [Prevención inteligente del seguimiento](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) para obtener más información. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| Vistas de página/Visitantes únicos estimados (ITP 2.1) | Número promedio de páginas vistas para Visitantes únicos estimados (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
