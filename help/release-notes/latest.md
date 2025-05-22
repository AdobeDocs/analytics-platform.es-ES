---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 13790d3857f1635f8efd5d98347fd02b9cbcc144
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 32%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (mayo de 2025)

**Última actualización:** jueves, 14 de mayo de 2025


Estas notas de la versión abarcan el periodo de lanzamiento del 22 de abril al 18 de junio de 2025. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition ayuda a las empresas B2B a alinear sus equipos de marketing, ventas y productos al proporcionar perspectivas de cuenta procesables que impulsan el crecimiento de los ingresos. Con la cuenta en el centro del modelo de datos, todo el análisis se centra en el recorrido de la cuenta. Al añadir una nueva capa de entidades (cuentas, oportunidades y grupos de compra) sobre los eventos basados en personas y tiempo, se crea una imagen completa del ciclo vital de ingresos y marketing B2B. [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | jueves, 18 de junio de 2025 |
| **Data Insights Agent** | Data Insights Agent, que forma parte del asistente de IA de Customer Journey Analytics, es un agente de conversación de IA generativo. Utiliza componentes de la vista de datos y los datos reales para responder de forma rápida y eficaz a preguntas centradas en los datos mediante la creación de visualizaciones relevantes en Analysis Workspace. [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | jueves, 28 de mayo de 2025 |
| **Agregar y ver comentarios en proyectos de Analysis Workspace** | Una nueva característica de [comentarios](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) en Analysis Workspace le permite compartir información y hacer preguntas en el contexto de un proyecto de Analysis Workspace. Esto puede agilizar los debates sobre los datos, manteniendo las conversaciones en el contexto de los datos que se están debatiendo. Puede <ul><li>Comente cualquier proyecto de Analysis Workspace al que tenga acceso</li><li>Comentar un punto específico en una visualización o hacer comentarios generales sobre un proyecto</li><li>Etiquete a otros usuarios para notificarles sus comentarios</li><li>Administrar comentarios existentes (editar, fijar, resolver, etc.)</li></ul>Los administradores de Customer Journey Analytics pueden [deshabilitar los comentarios en el nivel de organización](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Los propietarios del proyecto pueden [deshabilitar los comentarios en el nivel de proyecto](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | viernes, 29 de mayo de 2025 |
| **Aumento en los límites de exportación de tabla completa** | Adobe aumentó el número de columnas que puede usar con [exportación de tabla completa](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) de 5 dimensiones y 5 métricas a 10 dimensiones y 10 métricas. Esto se aplica a todos los niveles de Customer Journey Analytics. No hay cambios en los derechos del número de filas que se pueden exportar. |  | 30 de abril de 2025 |
| **Campos de XDM actualizados para la recopilación de datos de medios de streaming en Adobe Experience Platform** | Al recopilar datos de medios de streaming en Adobe Experience Platform, ya no se deben utilizar las rutas de campo XDM que se muestran en el encabezado de &quot;Ruta de campo XDM&quot; de la documentación de parámetros de medios de streaming. Estas rutas de campo se encuentran en las páginas siguientes y están marcadas como &quot;Obsoletas&quot;: [Parámetros de audio y vídeo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parámetros de publicidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/ad-parameters), [Parámetros de capítulo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parámetros de estado del reproductor](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/player-state-parameters) y [Parámetros de calidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/quality-parameters). <p>En su lugar, los clientes deben migrar a las rutas de campo `mediaReporting`, como se muestra en el encabezado de &quot;Ruta del campo XDM de creación de informes&quot; de la documentación de parámetros de medios de streaming a los que se hace referencia arriba.<p>Durante un periodo transitorio de tres meses, la ingesta de datos en las rutas de campo XDM obsoletas seguirá su curso. Sin embargo, a finales de julio de 2025, las rutas de campo obsoletas se eliminarán completamente y ya no serán visibles en la interfaz de usuario del esquema de Adobe Experience Platform, y los datos solo se enviarán mediante las rutas de campo `mediaReporting`.<p>Los clientes que hayan implementado el conector de origen de Analytics para recopilar datos de medios de streaming en Platform antes del 22 de abril de 2025 deben migrar sus configuraciones existentes para utilizar las nuevas rutas de campo. Esta migración deberá estar completada a finales de julio de 2025. Póngase en contacto con los servicios de Adobe Consulting o con el equipo de la cuenta para obtener ayuda sobre la migración. No se requiere ninguna acción para los clientes que implementen el conector de origen de Analytics después del 22 de abril de 2025.</p> |  | 22 de abril de 2025 |
| **Vinculación: recuperar ID persistentes y transitorios de IdentityMap XDM** | Esta función proporciona compatibilidad para utilizar identidades almacenadas en el identityMap de XDM en el proceso de vinculación. identityMap se puede utilizar para el ID persistente o transitorio para la vinculación basada en el campo y se puede utilizar para el ID persistente para la vinculación basada en gráficos.  Puede utilizar un espacio de nombres específico o la identidad principal desde el identityMap. Más información [aquí](https://experienceleague.adobe.com/es/docs/analytics-platform/using/stitching/fbs#identitymap) y [aquí](https://experienceleague.adobe.com/es/docs/analytics-platform/using/stitching/gbs#identitymap) |  | martes, 28 de abril de 2025 |
| **Métricas y dimensiones compartidas en vistas de datos** | Permite aplicar la configuración de dimensiones y métricas en varias vistas de datos. Los cambios realizados en una dimensión o métrica compartida se aplican a todas las instancias de esa dimensión o métrica en todas las vistas de datos aplicables. Esta interfaz permite a los administradores de Customer Journey Analytics administrar más fácilmente los componentes cuando se utilizan muchas vistas de datos. [Más información](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30 de abril de 2025 |
| **Dimensión de profundidad del evento** | Se agregó una nueva [dimensión de profundidad del evento](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) a la lista de componentes estándar requeridos para una vista de datos. |  | viernes, 08 de mayo de 2025 |
| **El panel izquierdo de Analysis Workspace ya no se abre y se cierra al pasar el ratón por encima** | El panel izquierdo de Analysis Workspace se utiliza para agregar elementos como componentes, paneles y visualizaciones al proyecto. La opción para abrir temporalmente el panel izquierdo pasando el puntero sobre uno de los iconos del extremo izquierdo ya no está disponible. En su lugar, simplemente haga clic en uno de estos iconos para mantener el panel abierto y, a continuación, haga clic en el mismo icono para cerrarlo. |  | viernes, 29 de mayo de 2025 |
| **Deshabilitar el archivo de manifiesto al exportar tablas completas** | Le permitirá deshabilitar el archivo de manifiesto que se incluye de forma predeterminada al exportar tablas completas desde Analysis Workspace. [Más información](/help/analysis-workspace/export/export-cloud.md) |  | miércoles, 20 de mayo de 2025 |


## Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**Audiencias**: AN-372343
**Registro de auditoría**: AN-378168
**Conexiones**: AN-373121; AN-372996
**Eliminación de datos**: AN-375450
**Campos derivados**: AN-373689; AN-377852
**Ubicaciones de exportación**: AN-374167
**Lienzo de Recorrido**: AN-373319
**Report Builder**: AN-369786
**Informes**: AN-377326; AN-378051
**Administrador de actividades de creación de informes**: AN-377148


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
