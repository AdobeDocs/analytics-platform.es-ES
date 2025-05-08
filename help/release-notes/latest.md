---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7930ca9a124f4a82cbe0fb08e8766f04109ccd87
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 70%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (abril de 2025)

**Última actualización**: jueves, 30 de abril de 2025

Estas notas de la versión cubren el período comprendido entre el 27 de marzo y 15 de mayo de 2025. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Dimensión de profundidad del evento** | Se agrega una nueva dimensión Profundidad de evento a la lista de [componentes estándar necesarios](/help/data-views/component-reference.md#required-standard-components) para una vista de datos. |  | viernes, 08 de mayo de 2025 |
| **Aumento en los límites de exportación de tabla completa** | El número de columnas que puede utilizar con la exportación de tabla completa se incrementa de 5 dimensiones y 5 métricas a 10 dimensiones y 10 métricas. Este aumento se aplica a todos los niveles de Customer Journey Analytics. No hay cambios en los derechos del número de filas que se pueden exportar. |  | 30 de abril de 2025 |
| **Actualizaciones del elemento de línea &quot;Sin valor&quot; en dimensiones numéricas** | Para las dimensiones numéricas, esta actualización le permite<ul><li>Utilice el elemento de dimensión &quot;Sin valor&quot; en un segmento.</li><li>Realizar un desglose en un informe sobre el elemento de línea &quot;Sin valor&quot;.</li></ul> [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | | 27 de marzo de 2025 |
| **Adobe Product Analytics** | Adobe Content Analytics le permite investigar rápida y fácilmente grandes volúmenes de datos de contenido para descubrir tendencias, detectar anomalías, identificar la fatiga del contenido y obtener información de la exposición al contenido.<p>De forma predeterminada, puede ahorrar tiempo con las plantillas de creación de informes generadas previamente y nuevas funciones como el Inspector de recursos. Esta función le permite no solo visualizar el recurso en línea con los datos, sino también abrir cada recurso para obtener detalles resumidos, entre ellos, ellos el rendimiento, ubicaciones, atributos y mucho más.<p>Puede investigar este nuevo conjunto de datos de contenido dentro del contexto del recorrido completo del cliente para responder a preguntas comerciales importantes, evaluar el rendimiento del contenido, mejorar la segmentación, identificar oportunidades de optimización y definir nuevos públicos para la activación.<p>El análisis de contenido es un complemento de Customer Journey Analytics. [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/content-analytics/content-analytics) |  | 27 de marzo de 2025 |
| **Recopilación de medios: actualizaciones del conector de origen de Adobe para el nuevo XDM de creación de informes de medios** | El conector de origen de Analytics asigna automáticamente los datos de medios de streaming en Adobe Analytics a los mismos campos utilizados por el SDK web. Actualmente, los datos se asignan a las ubicaciones antigua y nueva, pero en el futuro solo se utilizará la nueva ubicación. [Más información](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 31 de marzo de 2025 |
| **Campos de XDM actualizados para la recopilación de datos de medios de streaming en Adobe Experience Platform** | Al recopilar datos de medios de streaming en Adobe Experience Platform, ya no se deben utilizar las rutas de campo XDM que se muestran en el encabezado de &quot;Ruta de campo XDM&quot; de la documentación de parámetros de medios de streaming. Estas rutas de campo se encuentran en las páginas siguientes y están marcadas como &quot;Obsoletas&quot;: [Parámetros de audio y vídeo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parámetros de publicidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/ad-parameters), [Parámetros de capítulo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parámetros de estado del reproductor](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/player-state-parameters) y [Parámetros de calidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/quality-parameters). <p>En su lugar, los clientes deben migrar a las rutas de campo `mediaReporting`, como se muestra en el encabezado de &quot;Ruta del campo XDM de creación de informes&quot; de la documentación de parámetros de medios de streaming a los que se hace referencia arriba.<p>Durante un periodo transitorio de tres meses, la ingesta de datos en las rutas de campo XDM obsoletas seguirá su curso. Sin embargo, a finales de julio de 2025, las rutas de campo obsoletas se eliminarán completamente y ya no serán visibles en la interfaz de usuario del esquema de Adobe Experience Platform, y los datos solo se enviarán mediante las rutas de campo `mediaReporting`.<p>Los clientes que hayan implementado el conector de origen de Analytics para recopilar datos de medios de streaming en Platform antes del 22 de abril de 2025 deben migrar sus configuraciones existentes para utilizar las nuevas rutas de campo. Esta migración deberá estar completada a finales de julio de 2025. Póngase en contacto con los servicios de Adobe Consulting o con el equipo de la cuenta para obtener ayuda sobre la migración. No se requiere ninguna acción para los clientes que implementen el conector de origen de Analytics después del 22 de abril de 2025.</p> |  | 22 de abril de 2025 |
| **Cambio de terminología: &quot;Filtros&quot; a &quot;Segmentos&quot;** | Anteriormente, Adobe Customer Journey Analytics se refería a los segmentos como &quot;filtros&quot;. Esta terminología se ha adaptado a Adobe Analytics. Los &quot;filtros&quot; ahora se denominan &quot;segmentos&quot;. (Obviamente, los filtros de búsqueda aún se denominan &quot;filtros&quot;). Se han actualizado la interfaz de usuario y la documentación. | | 16 de abril de 2025 |
| **Vinculación: recuperar ID persistentes y transitorios de IdentityMap XDM** | Esta función proporciona compatibilidad para utilizar identidades almacenadas en el identityMap de XDM en el proceso de vinculación. identityMap se puede utilizar para el ID persistente o transitorio para la vinculación basada en el campo y se puede utilizar para el ID persistente para la vinculación basada en gráficos.  Puede utilizar un espacio de nombres específico o la identidad principal desde el identityMap. Más información [aquí](https://experienceleague.adobe.com/es/docs/analytics-platform/using/stitching/fbs#identitymap) y [aquí](https://experienceleague.adobe.com/es/docs/analytics-platform/using/stitching/gbs#identitymap) |  | martes, 28 de abril de 2025 |
| **Métricas y dimensiones compartidas en vistas de datos** | Permite aplicar la configuración de dimensiones y métricas en varias vistas de datos. Los cambios realizados en una dimensión o métrica compartida se aplican a todas las instancias de esa dimensión o métrica en todas las vistas de datos aplicables. Esta interfaz permite a los administradores de Customer Journey Analytics administrar más fácilmente los componentes cuando se utilizan muchas vistas de datos. [Más información](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30 de abril de 2025 |


## Correcciones en Customer Journey Analytics

**Admin Console**: AN-370228
**Analysis Workspace**: AN-371933; AN-371933; AN-371979
**Públicos**: AN-373032
**Configuración de componentes**: AN-367400
**Campos derivados**: AN-370614; AN-370959
**Ubicaciones de exportación**: AN-371670
**Exportación de tablas completas**: AN-360492; AN-369204; AN-370755;AN-372294; AN-372363; AN-372754; AN-373040; AN-373081; AN-373168
**Lienzo de recorrido**: AN-373294
**Aplicación móvil**: AN-363169; AN-368496; AN-371766
**Uso del producto**: AN-369501
**Sistema de informes**: AN-369085; AN-371094; AN-372580


## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | | |

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
