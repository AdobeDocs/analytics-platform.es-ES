---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 299337b6b0ea12224a7da6c15dcc582e8562c088
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 94%

---

# Notas actuales de la versión de Customer Journey Analytics (octubre de 2025)

**Última actualización**: 14 de octubre de 2025

Estas notas de la versión cubren el período comprendido entre octubre y principios de noviembre de 2025. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Criterios de filtro incluidos en las visualizaciones de líneas y los minigráficos** | Cualquier criterio de filtro de búsqueda que aplique a un filtro de tabla de forma libre ahora se incluye siempre en los minigráficos. Además, puede incluir criterios de filtro de búsqueda en cualquier visualización de línea conectada.<p>Puede configurar las visualizaciones de líneas para que incluyan los criterios de filtro de búsqueda si selecciona el minigráfico en el encabezado de columna de métrica de la tabla conectada.</p><p>Anteriormente, los criterios de filtro de búsqueda no se incluían en los minigráficos ni en las visualizaciones de líneas conectadas.</p><p>Para obtener más información, consulte [Ver datos de tendencias de una tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).</p> | | 15 de octubre de 2025 |
| **Narración de datos: genere presentaciones de diapositivas a partir de informes de Workspace** | Ahora puede generar automáticamente una presentación de diapositivas (en formato .pptx) basada en un informe de Analysis Workspace. Workspace detecta la información clave del informe y la convierte en diapositivas preparadas para las partes interesadas.<p>Esta función reduce el tiempo y el esfuerzo necesarios para sacar a la luz los hallazgos, crear narrativas ejecutivas y comunicar el impacto empresarial.</p><p>Para obtener más información, vea [Contar historias de datos: generar presentaciones de diapositivas a partir de informes de Workspace](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 de octubre de 2025 | Enero de 2026 |
| **Informes en tiempo real** | Los [informes en tiempo real en Customer Journey Analytics](/help/components/real-time/real-time.md) muestran y actualizan los datos y las visualizaciones en uno o varios paneles de Analysis Workspace en tiempo real. | 18 de septiembre de 2025 (originalmente programado para su lanzamiento el 15 de agosto de 2025) | 22 de octubre de 2025 |
| **Compatibilidad con Data Mirror** | Con la compatibilidad con los esquemas basados en modelos y la funcionalidad de captura de datos modificados (CDC) para conectores de origen específicos en Experience Platform, Customer Journey Analytics podrá admitir la funcionalidad de [duplicación de datos](/help/data-mirror/data-mirror.md) de soluciones de almacenamiento de datos como [!DNL Snowflake], [!DNL Azure Databricks] y [!DNL Google BigQuery].<p>Póngase en contacto con el equipo de cuentas de Adobe para acceder a Beta.</p> | Lanzamiento de la versión beta: 24 de septiembre de 2025. | Por determinar |
| **Identificación en conexiones** | Simplifica la vinculación de Customer Journey Analytics. En lugar de duplicar un conjunto de datos y aplicar la vinculación en el conjunto de datos duplicado, la vinculación ahora se realiza al ingerir datos en Customer Journey Analytics, lo que elimina el requisito de conjuntos de datos y esquemas duplicados. <p>Además, en lugar de tener que solicitar la vinculación a través del servicio de atención al cliente, ahora puede [iniciar la vinculación desde una interfaz de usuario de Conexiones actualizada](/help/stitching/use-stitching-ui.md).</p><p> *Las fechas de versiones comunicadas anteriormente se retrasan debido a los esfuerzos adicionales necesarios. Las nuevas fechas de lanzamiento coinciden con la temporada de vacaciones, lo que añade restricciones de lanzamiento adicionales. Ahora se planea un despliegue gradual para garantizar la estabilidad y minimizar las interrupciones durante el período de vacaciones.*</p> | 28 de octubre de 2025 | sábado, 30 de enero de 2026 |
| **Servicios de medios de streaming: compatibilidad con datos de programación** | Ahora puede cargar datos programados de contenidos anteriores de medios de streaming en directo para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |
| **Conector de origen de Analytics: busque grupos de informes en Experience Platform** | Si tiene un número elevado de grupos de informes, ahora puede [buscar el grupo de informes](/help/data-ingestion/analytics.md#set-up-an-adobe-analytics-source-connector) al que desee conectarse dentro del flujo de trabajo del conector de Source de Analytics. | | 30 de octubre de 2025 |
| **Medios de streaming: campos XDM actualizados para recopilar datos de medios de streaming en Adobe Experience Platform** | Al recopilar datos de medios de streaming en Adobe Experience Platform, ya no se deben utilizar las rutas de campo XDM que se muestran en el encabezado de &quot;Ruta de campo XDM&quot; de la documentación de parámetros de medios de streaming. En su lugar, los clientes que implementaron el conector de origen de Analytics para recopilar datos de medios de streaming en Platform antes del 9 de mayo de 2025 deben migrar sus configuraciones existentes a las rutas de campo de creación de informes de medios, como se muestra en el encabezado de “Ruta de campo XDM de creación de informes” de la documentación de parámetros de medios de streaming.<p> Estas rutas de campo se encuentran en las páginas siguientes y están marcadas como “Obsoletas”: [Parámetros de audio y vídeo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parámetros de anuncios](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/ad-parameters), [Parámetros de capítulos](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parámetros de estado del reproductor](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/player-state-parameters) y [Parámetros de calidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/quality-parameters). (No se requiere ninguna acción para los clientes que implementan el conector de origen de Analytics después del 9 de mayo de 2025 y que ya solo utilizan rutas XDM de creación de informes de medios).</p><p>La ingesta de datos en las rutas de campo XDM obsoletas seguirá hasta finales de octubre de 2025. Después de ese tiempo, las rutas de campo obsoletas se eliminarán por completo y ya no serán visibles en la interfaz de usuario de Adobe Experience Platform Schema, y los datos solo se enviarán utilizando las rutas de campo mediaReporting.</p><p>Para obtener más información, consulte [Migrar una implementación del conector de origen de Analytics a campos actualizados de medios de streaming XDM](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Póngase en contacto con los servicios de Adobe Consulting o con el equipo de la cuenta para obtener ayuda sobre la migración. </p> |  | Octubre de 2025 |

## Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-400507, AN-400265, AN-399209, AN-397146, AN-394992, AN-390795
**Componentes**:
**Content Analytics**:
**Exportaciones**: AN-399012, AN-388578
**Análisis guiado**:
**Implementación**: AN-397551, AN-397550, AN-397190, AN-396127
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**Informes**:
**Segmentación**:
**Informes programados**:
**Métricas y dimensiones compartidas**:
**Otros**:


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
