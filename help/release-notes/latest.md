---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 017bf3cb720ed153476d17db92e0eeca156e6b61
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 91%

---

# Notas de la versión actuales de Customer Journey Analytics (septiembre de 2025)

**Última actualización**: miércoles, 23 de septiembre de 2025


Estas notas de la versión cubren el periodo comprendido entre septiembre y principios de octubre de 2025. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Actualizaciones en la interfaz de uso** | La [interfaz de uso](/help/connections/manage-connections.md#usage) ahora añade información sobre el volumen de datos principales y el tamaño de fila promedio.<p>Para obtener más información, consulte [Administrar conexiones](/help/connections/manage-connections.md#usage).</p> | | 4 de septiembre de 2025 |
| **Mejoras al migrar proyectos y componentes a Customer Journey Analytics** | Las siguientes mejoras ya están disponibles al migrar proyectos y componentes de Adobe Analytics a Customer Journey Analytics:<ul><li>Migre varios proyectos al mismo tiempo.<br/>Puede migrar hasta 20 proyectos al mismo tiempo.<br/>Anteriormente, solo se podía migrar un proyecto a la vez.</li><li>Actualice las asignaciones para dimensiones y métricas que ya estaban asignadas con una migración de proyecto anterior.<br/>Ahora puede actualizar estas asignaciones cada vez que migre un proyecto, incluso si las mismas dimensiones y métricas se asignaron anteriormente con una migración anterior.<br/>Anteriormente, cualquier asignación que eligiera era permanente para todas las migraciones futuras de proyectos.</li><li>Mayor rendimiento para organizaciones con un gran número de proyectos.</li></ul><p>Esta función está disponible en la interfaz de Adobe Analytics. Para obtener más información, consulte [Migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/component-migration).</p> | 15 de septiembre de 2025 | 18 de septiembre de 2025 |
| **El límite de claves de búsqueda aumentó hasta mil millones** | El número máximo de claves únicas para un conjunto de datos de consulta ahora es de hasta mil millones, según el derecho de uso de Customer Journey Analytics. <p>Anteriormente, el número máximo era de 10 millones para todos los derechos de uso.<p>Para obtener más información, consulte [Mecanismos de protección](/help/technotes/guardrails.md).</p> | | viernes, 25 de septiembre de 2025 |
| **Compatibilidad con esquemas ad hoc y basados en modelos** | [Los esquemas ad hoc](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/tutorials/ad-hoc) y basados en modelos se utilizan en los flujos de trabajo de ingesta de datos y duplicación de datos para Experience Platform. |  | miércoles, 23 de septiembre de 2025 (Originalmente planificado para su lanzamiento el 28 de agosto de 2025) |
| **Creación de informes en tiempo real** | La creación de informes en tiempo real en Customer Journey Analytics muestra y actualiza datos y visualizaciones en uno o varios paneles de Analysis Workspace en tiempo real.<br/><br/>(Vínculo a la documentación a continuación). | 18 de septiembre de 2025 (originalmente programado para su lanzamiento el 15 de agosto de 2025) | jueves, 01 de octubre de 2025 |
| **Compatibilidad con Data Mirror** | Con compatibilidad con esquemas basados en modelos y la funcionalidad de captura de datos de cambio (CDC) para conectores de origen específicos en Experience Platform, Customer Journey Analytics podrá admitir la funcionalidad de reflejo de datos de soluciones de Data Warehouse como [!DNL Snowflake], [!DNL Azure Databrick]s y [!DNL Google BigQuery].<p>Póngase en contacto con el equipo de cuentas de Adobe para acceder a Beta.</p><p>(Vínculo a la documentación a continuación).</p> | Versión de Beta, a partir del 24 de septiembre de 2025 | Por determinar |
| **Medios de streaming: campos XDM actualizados para recopilar datos de medios de streaming en Adobe Experience Platform** | Al recopilar datos de medios de streaming en Adobe Experience Platform, ya no se deben utilizar las rutas de campo XDM que se muestran en el encabezado de &quot;Ruta de campo XDM&quot; de la documentación de parámetros de medios de streaming. En su lugar, los clientes que implementaron el conector de origen de Analytics para recopilar datos de medios de streaming en Platform antes del 9 de mayo de 2025 deben migrar sus configuraciones existentes a las rutas de campo de creación de informes de medios, como se muestra en el encabezado de “Ruta de campo XDM de creación de informes” de la documentación de parámetros de medios de streaming.<p> Estas rutas de campo se encuentran en las páginas siguientes y están marcadas como “Obsoletas”: [Parámetros de audio y vídeo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parámetros de anuncios](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/ad-parameters), [Parámetros de capítulos](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parámetros de estado del reproductor](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/player-state-parameters) y [Parámetros de calidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/quality-parameters). (No se requiere ninguna acción para los clientes que implementan el conector de origen de Analytics después del 9 de mayo de 2025 y que ya solo utilizan rutas XDM de creación de informes de medios).</p><p>La ingesta de datos en las rutas de campo XDM obsoletas seguirá hasta finales de octubre de 2025. Después de ese tiempo, las rutas de campo obsoletas se eliminarán por completo y ya no serán visibles en la interfaz de usuario de Adobe Experience Platform Schema, y los datos solo se enviarán utilizando las rutas de campo mediaReporting.</p><p>Para obtener más información, consulte [Migrar una implementación del conector de origen de Analytics a campos actualizados de medios de streaming XDM](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Póngase en contacto con los servicios de Adobe Consulting o con el equipo de la cuenta para obtener ayuda sobre la migración. </p> |  | Octubre de 2025 |
| **Identificación en conexiones** | Simplifica la vinculación de Customer Journey Analytics. En lugar de duplicar un conjunto de datos y aplicar la vinculación en el conjunto de datos duplicado, la vinculación ahora se realiza al ingerir datos en Customer Journey Analytics, lo que elimina el requisito de conjuntos de datos y esquemas duplicados. <p>Además, en lugar de tener que solicitar la vinculación a través del servicio de atención al cliente, ahora puede iniciar la vinculación desde la interfaz de usuario de Conexiones actualizada.</p><p> *Las fechas de versiones comunicadas anteriormente se retrasan debido a los esfuerzos adicionales necesarios. Las nuevas fechas de lanzamiento coinciden con la temporada de vacaciones, lo que añade restricciones de lanzamiento adicionales. Ahora se planea un despliegue gradual para garantizar la estabilidad y minimizar las interrupciones durante el período de vacaciones.*</p> <p>(Vínculo a la documentación a continuación).</p> | Finales de octubre de 2025 | Finales de enero de 2025 |

## Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Componentes**: AN-393810
**Análisis de contenido**:
**Análisis guiado**:
**Plataforma**:
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Sistema de informes**: AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-393304
**Segmentación**:
**Informes programados**: AN-391150, AN-390474
**Métricas y dimensiones compartidas**:
**Otros**: AN-387858


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
