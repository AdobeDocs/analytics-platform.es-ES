---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 29c124da55842bcb9085059a9008f7a7d6baf44e
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 47%

---

# Notas de la versión actuales de Adobe Customer Journey Analytics (febrero de 2024)

**Última actualización**: jueves, 14 de febrero de 2024

Estas notas de la versión abarcan el período de lanzamiento del final del jueves, 14 de febrero de 2024 al martes, 11 de marzo de 2024. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Previsión de series temporales** | [Previsión](../analysis-workspace/c-forecast/forecasting.md) es una nueva función de Analysis Workspace que se utiliza para prever una métrica estándar o calculada con cualquier granularidad de tiempo admitida (por hora, diario, semanal, mensual y anual) para tablas improvisada y gráficos de líneas. | 31 de enero de 2024 | 21 de febrero de 2024 |
| **Informes de Media Analytics: Audiencia media por minuto (AMA)** | El panel Audiencia media por minuto ya está disponible en CJA. Los clientes de Media Analytics pueden usar el panel Audiencia media por minuto de medios para comprender mejor el consumo promedio de su contenido. La audiencia media por minuto permite comparar la programación de cualquier género o duración. Además, los clientes pueden comparar o anexar esta audiencia media por minuto digital a métricas de minuto promedio de televisión lineal. Este panel proporciona más flexibilidad para medir la audiencia promedio en períodos de tiempo personalizados, así como cuando la clasificación de duración se ha actualizado después del hecho. |  | sábado, 16 de febrero de 2024 |
| **Métricas de recuento de filas para datos de búsqueda y perfil** | Las métricas de recuento de filas para conjuntos de datos, configuradas como parte de una conexión, ahora incluyen registros añadidos, omitidos o eliminados de los conjuntos de datos de perfil y búsqueda. |  | jueves, 14 de febrero de 2024 |
| **Detección de bots Experience Edge** | [Detección de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) permite identificar eventos generados por SDK web, SDK móvil y API de servidor como generados por arañas de web y bots conocidos. | | 21 de febrero de 2024 |
| **Métricas de uso** | La interfaz de métricas de uso muestra el uso de filas ingeridas y notificables en todas las conexiones. Esta interfaz le permite determinar si el uso del Customer Journey Analytics cumple con lo acordado contractualmente. | miércoles, 20 de febrero de 2024 | Principios de marzo de 2024 |
| **Adobe Product Analytics: Compartir con cualquiera** | Permite compartir un vínculo de solo lectura a proyectos de Adobe Product Analytics con personas que no tienen acceso a Product Analytics. |  | 21 de febrero de 2024 |
| **Adobe Product Analytics: Aplicar métricas calculadas** | Ahora puede acceder a las métricas calculadas creadas en Analysis Workspace o en el Creador de métricas calculadas en la vista Tendencias: Uso, lo que le permite realizar tendencias y comparar métricas a lo largo del tiempo. |  | sábado, 16 de febrero de 2024 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-333172; AN-336887; AN-337402; AN-337593; AN-338482; AN-338684; AN-339883; AN-340200

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| Adiciones de miembros de objeto de API de Adobe | 17 de enero de 2024 | Adobe puede añadir miembros de solicitud y respuesta opcionales (pares de nombre/valor) a objetos de API existentes sin previo aviso ni cambios en las versiones. Estas adiciones deben ser cambios importantes para la implementación. Adobe recomienda que se consulte la documentación de la API de cualquier herramienta de terceros que se integre con nuestras API para que dichas adiciones se ignoren en el procesamiento si no se comprenden. Adobe no quitará los parámetros ni añadirá los parámetros necesarios sin antes proporcionar una notificación estándar mediante las notas de la versión. |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
