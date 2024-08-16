---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1be029f373ea5c161631a432bc275e5afd8dc761
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 79%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (agosto de 2024)

**Última actualización**: jueves, 14 de agosto de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 14 de agosto de 2024 a septiembre de 2024. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Fuentes de datos a nivel de resumen** | Permiten introducir datos de series temporales que no tienen un ID de persona. Estos datos de series temporales se pueden utilizar para admitir varios casos de uso, como:<ul><li>Presentar indicadores de rendimiento de alto nivel como parte de los datos de nivel de evento o junto a ellos. Esto puede incluir algo tan simple como una fecha y un solo valor de métrica o incluir varias dimensiones y métricas, como impresiones de publicidad, aperturas de correo electrónico, gastos en publicidad, coste del producto vendido, etc.</li><li>Cargar objetivos por hora o por día y, a continuación, colocarlos en métricas de nivel de evento. Esto ayuda a visualizar las tendencias de las métricas en comparación con los objetivos u objetivos de la organización.</li></ul><p>Para obtener más información, consulte [Datos de resumen](/help/data-views/summary-data.md).</p> | miércoles, 13 de agosto de 2024 | jueves, 21 de agosto de 2024 |
| **Los púbicos se publican en una nueva sección “Públicos” en Experience Platform** | Los públicos publicados desde Customer Journey Analytics están ahora disponibles en la nueva sección “Públicos” de Experience Platform.<p>Anteriormente, los públicos publicados desde Customer Journey Analytics estaban disponibles en Experience Platform en la sección “Segmentos”.</p><p>Esta mejora ofrece las siguientes ventajas:</p><ul><li>Los públicos ya no tienen un retraso de 1 hora antes de aparecer en Experience Platform; están disponibles segundos tras su publicación.</li><li>Los públicos se pueden ordenar en Experience Platform mediante la columna “Origen”, que muestra la aplicación desde la que se publicó originalmente el público.</li><li>Las opciones de filtro y ordenación de Experience Platform le permiten encontrar más rápidamente los públicos relevantes.</li></ul> <p>Para obtener más información, consulte [Usar audiencias de Customer Journey Analytics en Experience Platform](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform) en el artículo [Crear y publicar audiencias](/help/components/audiences/publish.md).</p> | 14 de agosto de 2024 | 22 de agosto de 2024 |
| **Alertas inteligentes** | Las alertas inteligentes en Customer Journey Analytics le permiten recibir notificaciones inmediatamente cuando se producen eventos anormales en los datos.<p>Puede definir alertas para que se activen en función de umbrales de anomalías, porcentajes modificados o puntos de datos específicos. Las alertas proporcionan controles granulares que se integran con la Detección de anomalías y se activan cuando más los necesita.</p><p>El proceso de utilización de las Alertas inteligentes en Customer Journey Analytics es casi idéntico al de las Alertas inteligentes en Adobe Analytics. Una diferencia clave es que las alertas horarias no están disponibles en Customer Journey Analytics. Esta diferencia se debe a que la ingesta de datos para los distintos tipos de datos de evento que se pueden introducir se completa solo después de un retraso, que generalmente oscila entre 3 y 9 horas después del tiempo de evento de datos.</p><p>(Vínculos a la documentación actualizada a continuación)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | Por determinar |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-354359; AN-351646; AN-346873; AN-352504; AN-353755; AN-354199; AN-354268; AN-354791; AN-354598; AN-354462; AN-354547;

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | | |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión del complemento de recopilación de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
