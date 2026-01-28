---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 94dffc915f624309bca4709ba9140b64b3e3aa41
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 46%

---

# Notas de la versión actuales de Customer Journey Analytics (enero de 2026)

**Última actualización**: jueves, 14 de enero de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de enero de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analizar audiencias de conjuntos de datos de perfil de Experience Platform en Customer Journey Analytics** | Ahora puede introducir datos de pertenencia a audiencias de conjuntos de datos de perfil de Experience Platform en una conexión de Customer Journey Analytics. Las audiencias están disponibles como nuevas dimensiones para su uso en Analysis Workspace.<p>Esto es posible gracias a la nueva capacidad de Customer Journey Analytics para introducir mapas de objetos XDM, lo que permite introducir ID de audiencia de perfil.</p><p>Anteriormente, solo se podían ingerir mapas XDM simples en Customer Journey Analytics.</p><p>Además de poder agregar datos de audiencia como dimensiones a cualquier proyecto en Analysis Workspace, también están disponibles las siguientes plantillas nuevas de Workspace:</p><ul><li>Información general de Audience Analytics</li><li>Información general de directiva de consentimiento</li></ul><p>Para obtener más información, vea [Resumen del análisis de audiencia](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html?lang=es).</p> | 22 de octubre de 2025 | miércoles, 27 de enero de 2026 <p> (Originalmente planificado para el 22 de enero de 2026)</p> |
| **Narración de datos: genere presentaciones de diapositivas a partir de informes de Workspace** | Ahora puede generar automáticamente una presentación de diapositivas (en formato .pptx) basada en un informe de Analysis Workspace. Workspace detecta la información clave del informe y la convierte en diapositivas preparadas para las partes interesadas.<p>Esta función reduce el tiempo y el esfuerzo necesarios para sacar a la luz los hallazgos, crear narrativas ejecutivas y comunicar el impacto empresarial.</p><p>Para obtener más información, vea [Contar historias de datos: generar presentaciones de diapositivas a partir de informes de Workspace](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 de octubre de 2025 | jueves, 28 de enero de 2026 |
| **Incluir varias columnas de dimensión en una tabla de forma libre** | Ahora puede incluir hasta 5 columnas de dimensión en una tabla de forma libre, lo que le permite ver varios elementos de dimensión en paralelo. Cada fila de elementos de dimensión se comporta como un solo elemento de dimensión concatenado.<p>Puede aplicar filtros, clasificaciones, desgloses y mucho más a las tablas de forma libre con varias columnas de dimensión para crear un análisis más profundo y personalizado.</p><p>Anteriormente, solo se podía incluir 1 columna de dimensión en una tabla de forma libre.</p><p>Para obtener más información, vea [Incluir varias columnas de dimensión en una tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | jueves, 28 de enero de 2026 | jueves, 18 de febrero de 2026 |
| **Ordenar tablas por varias columnas** | Ahora puede ordenar los datos de una tabla de forma libre por varias columnas en Analysis Workspace, ya sean dimensiones o métricas.<p>Al ordenar los datos de varias columnas, los datos se ordenan según la prioridad asignada a cada columna. La numeración de prioridad se muestra junto al icono de ordenación.</p><p>Para obtener más información, vea [Ordenar tablas por varias columnas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables-by-multiple-columns-advanced-sorting) en [Filtrar y ordenar tablas improvisadas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | jueves, 28 de enero de 2026 | jueves, 18 de febrero de 2026 |
| **Combinar orígenes de datos de varias organizaciones de IMS** | Ahora puede utilizar el conector de Source de Analytics para combinar varias fuentes de datos de varias organizaciones IMS. Esto permite a las organizaciones tener una vista combinada de los datos de sus clientes, incluso cuando esos datos de clientes se distribuyen entre varias organizaciones de IMS. <p>**Nota:** Esta configuración solo está disponible al enviar una solicitud al Servicio de atención al cliente de Adobe.</p>  <p>(Vínculo a la documentación a continuación).</p> |  | sábado, 30 de enero de 2026 |
| **Identificación en conexiones** | El proceso de vinculación en Customer Journey Analytics ahora es más sencillo. En lugar de duplicar un conjunto de datos y aplicar la vinculación en el conjunto de datos duplicado, la vinculación ahora se realiza al ingerir datos en Customer Journey Analytics, lo que elimina el requisito de conjuntos de datos y esquemas duplicados. <p>Además, ahora puede [iniciar la vinculación a través de una interfaz de conexiones actualizada](/help/stitching/use-stitching-ui.md), en lugar de tener que solicitar la vinculación a través del Servicio de atención al cliente de Adobe.</p><p> *Las fechas de versiones comunicadas anteriormente se pospusieron debido a los esfuerzos adicionales necesarios y a la temporada de vacaciones. Ahora se planea un despliegue gradual para garantizar la estabilidad y minimizar las interrupciones durante el período de vacaciones.*</p> | 28 de octubre de 2025 | sábado, 30 de enero de 2026 |
| **Compatibilidad con Data Mirror** | Con la compatibilidad con los esquemas basados en modelos y la funcionalidad de captura de datos modificados (CDC) para conectores de origen específicos en Experience Platform, Customer Journey Analytics podrá admitir la funcionalidad de [duplicación de datos](/help/data-mirror/data-mirror.md) de soluciones de almacenamiento de datos como [!DNL Snowflake], [!DNL Azure Databricks] y [!DNL Google BigQuery].<p>Póngase en contacto con el equipo de cuentas de Adobe para acceder a Beta.</p> | Lanzamiento de la versión beta: 24 de septiembre de 2025. | Por determinar |
| **Servicios de medios de streaming: compatibilidad con datos de programación** | Ahora puede cargar datos programados de contenidos anteriores de medios de streaming en directo para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |

## Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422027, AN-421134, AN-420187, AN-406271, AN-405997, AN-406188, AN-405983, AN-405796, AN-404893, AN-404871, AN-404842, AN-404713, AN-405033, AN-404502, AN-404353, AN-404352, AN-404048, AN-403241, AN-402523, AN-400795, AN-396149, AN-390990, AN-390646, AN-383484, AN-376980, AN-371729 347570 404835 AN-
**Componentes**:
**Content Analytics**:
**Análisis guiado**: AN-421274
**Exportaciones**:
**Vistas de datos**: AN-421891, AN-404627
**Implementación**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Informes**:
**Segmentación**:
**Informes programados**: AN-423087, AN-422686
**Métricas y dimensiones compartidas**:
**Otros**: AN-422946, AN-422775, AN-422273, AN-422100, AN-420045, AN-404891, AN-390912


## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A |  |  |

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
