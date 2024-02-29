---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fd12f9b90c3240d10bf2fd5e22a2983b844051b5
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 80%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (febrero de 2024)

**Última actualización**: miércoles, 27 de febrero de 2024

Estas notas de la versión abarcan el período de lanzamiento del final del 14 de febrero de 2024 al 11 de marzo de 2024. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Previsión de series temporales** | La [previsión](../analysis-workspace/c-forecast/forecasting.md) es una nueva función de Analysis Workspace que se utiliza para realizar una previsión de una métrica estándar o calculada con cualquier granularidad de tiempo admitida (por hora, diario, semanal, mensual y anual) para tablas de forma libre y gráficos de líneas. | 31 de enero de 2024 | 21 de febrero de 2024 |
| **Sistema de informes de Media Analytics: promedio de público por minuto (AMA)** | El panel Promedio de público por minuto ya está disponible en CJA. Los clientes de Media Analytics pueden utilizar el panel Promedio de público por minuto para comprender mejor el consumo medio de su contenido. La audiencia media por minuto permite comparar la programación de cualquier género o duración. Además, los clientes pueden comparar o anexar esta audiencia media por minuto digital a métricas de minuto promedio de televisión lineal. Este panel proporciona más flexibilidad para medir el promedio de público en periodos de tiempo personalizados, así como cuando la clasificación de duración se ha actualizado después del hecho. |  | Marzo de 2024 |
| **Métricas de recuento de filas para datos de búsqueda y perfil** | Las métricas de recuento de filas para conjuntos de datos, configuradas como parte de una conexión, ahora incluyen registros añadidos, omitidos o eliminados de los conjuntos de datos de perfil y búsqueda. |  | 14 de febrero de 2024 |
| **Detección de bots Experience Edge** | [Detección de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=es) permite identificar eventos generados por SDK web, SDK móvil y API de servidor como si fueran generados por arañas de web y bots conocidos. | | martes, 29 de abril de 2024 |
| **Métricas de uso** | La interfaz de métricas de uso muestra el uso de filas ingeridas y notificables en todas las conexiones. Esta interfaz permite determinar si el uso del Customer Journey Analytics cumple con lo acordado contractualmente. | 20 de febrero de 2024 | Principios de marzo de 2024 |
| **Adobe Product Analytics: compartir con cualquiera** | Le permite compartir un vínculo de solo lectura a proyectos de Adobe Product Analytics con personas que no tienen acceso a Product Analytics. |  | miércoles, 05 de marzo de 2024 |
| **Adobe Product Analytics: Aplicar métricas calculadas** | Ahora puede acceder a las métricas calculadas creadas en Analysis Workspace o en el generador de métricas calculadas en la vista Tendencias: uso, lo que le permite establecer tendencias y comparar métricas a lo largo del tiempo. |  | 16 de febrero de 2024 |
| **Vínculos actualizados en las IU de Vistas de datos y Conexiones** | A principios de marzo, Adobe tiene previsto actualizar los siguientes vínculos en la interfaz de usuario del producto de Customer Journey Analytics. Actualice sus marcadores según corresponda.<ul><li>**página Vistas de datos, Administrador de vistas de datos**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Crear nueva vista de datos**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Editar vista de datos**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Nuevo vínculo](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Administrador de conexiones**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Información de conexiones**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Editar conexión**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Crear nueva conexión**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |  | Marzo de 2024 |

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
