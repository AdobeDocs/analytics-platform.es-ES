---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8cdfe0db0aabba05fbebe7d9215182e0fca31d66
workflow-type: tm+mt
source-wordcount: 615
ht-degree: 44%

---

# Notas de la versión actuales de Customer Journey Analytics (junio de 2026)

**Última actualización**: 25 de junio de 2026

Estas notas de la versión abarcan el período de la versión de junio de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Data Mirror** <br/>[Data Mirror](/help/data-mirror/data-mirror.md) es una funcionalidad de Experience Platform que habilita la ingesta de cambios a nivel de fila (captura de datos de cambio) desde soluciones de Data Warehouse externas ([!DNL Snowflake], [!DNL Azure Databricks] y [!DNL Google BigQuery]) a Customer Journey Analytics mediante esquemas relacionales. Conserva las relaciones de datos, fuerza la exclusividad y admite el control de versiones sin requerir procesos de extracción, transformación y carga (ETL) en sentido ascendente. | 25 de marzo de 2026 | 17 de junio de 2026 |
| **Valide los datos en el Asistente de IA** <br/>Puede usar el Asistente de IA para [validar la calidad de los datos de los conjuntos de datos de Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/experience-cloud-ai/experience-cloud-ai/agents/data-validation). Con la tecnología de Agent Orchestrator, la capacidad de validación de datos puede realizar validaciones estadísticas y semánticas de conjuntos de datos, analizar campos de conjuntos de datos, identificar problemas de calidad de datos y devolver resúmenes de lenguajes naturales con perspectivas procesables. | | 22 de junio de 2026 |

### Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-456858, AN-455865, AN-455706, AN-455592, AN-455484, AN-455180, AN-454999, AN-454170, AN-454145, AN-453793, AN-452921, AN-452009, AN-451958, AN-451643, AN-451600, AN-451525, AN-451477, AN-451262, AN-451161, AN-450772, AN-443594, AN-434416, AN-, AN-, AN-, AN-
**Componentes**:
**Conexiones**: AN-457065, AN-453705
**Content Analytics**: AN-451203, AN-447596
**Análisis guiado**:
**Exportaciones**: AN-452006, AN-451989, AN-440567
**Vistas de datos**: AN-451198
**Implementación**:
**Report Builder**: AN-440912, AN-457586, AN-457533, AN-455713, AN-455623, AN-455063, AN-454512, AN-454053, AN-453977, AN-453781, AN-453683, AN-451974, AN-451735, AN-451731, AN-451190, AN-449813, AN-447173, AN-447139, AN-446184, AN-445794, AN-445354, AN-442819, AN-, AN-, AN-, AN-
**Informes**: AN-454589, AN-454517, AN-453982, AN-451822, AN-451497, AN-451463, AN-451259, AN-451215, AN-450661, AN-447699, AN-448375, AN-447692
**Segmentación**:
**Informes programados**: AN-451980, AN-451882, AN-450715
**Dimensiones y métricas compartidas**:
**Análisis de audiencia**: AN-449656, AN-450400
**Otros**: AN-457063, AN-454140, AN-453937, AN-453825, AN-452959, AN-452934, AN-452296, AN-451781, AN-450974

## Funciones aplazadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenido de medios de streaming transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data) | 29 de octubre de 2025 | Por determinar<p>(Originalmente planificado para el 29 de octubre de 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notas de la versión anteriores de Customer Journey Analytics de 2026](/help/release-notes/2026.md)
>* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
>* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
>* [Notas de la versión de CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
>* [Actualizaciones de documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
