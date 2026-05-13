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
source-git-commit: d7802b43351f5aa4777f32d8c736d5137860dd44
workflow-type: tm+mt
source-wordcount: 891
ht-degree: 41%

---

# Notas de la versión actuales de Customer Journey Analytics (mayo de 2026)

**Última actualización**: 13 de mayo de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de mayo de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Colecciones Postman de API de CJA** <br/>Hay disponible una colección Postman descargable para llamar a los extremos de API de CJA.<p>Para obtener más información, consulte [analytics-cja-postman-collections repositorio de Github](https://github.com/AdobeDocs/analytics-cja-postman-collections).  </p> | | 1 de mayo de 2026 |
| **Servidores MCP para Customer Journey Analytics** <br/>Los servidores MCP (Model Context Protocol) de Analytics le permiten conectar un cliente MCP compatible a Adobe Customer Journey Analytics. Una vez conectado, el cliente de MCP puede invocar herramientas específicas del producto para recuperar datos, ejecutar consultas o realizar operaciones admitidas como parte de un flujo de trabajo LLM o agéntico. Para obtener más información, consulte [Servidores MCP de Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Si ha utilizado estos servidores MCP durante el período beta, tenga en cuenta que hay diferentes direcciones URL entre los extremos beta y de producción. Asegúrese de que todos los flujos de trabajo agénticos creados durante el periodo beta se actualicen para utilizar los extremos de producción antes del 31 de mayo.</p> | | 5 de mayo de 2026 |
| **Compatibilidad de Content Analytics con experiencias nativas de aplicaciones móviles**<br/> Las organizaciones pueden ampliar su análisis del rendimiento del contenido a aplicaciones de iOS y Android, capturando recursos de imagen y elementos de experiencia granulares para comprender qué contenido en la aplicación impulsa la participación del usuario y los resultados empresariales.<p> La [documentación](/help/content-analytics/content-analytics.md) se ha actualizado para describir la configuración y las capacidades del canal móvil. La información sobre la extensión [Content Analytics Mobile SDK](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) está disponible en [Adobe Developer](https://developer.adobe.com/).</p><p>Las perspectivas están disponibles para todos los clientes de Adobe Content Analytics.</p> | | 6 de mayo de 2026 |
| **Validación de datos en Adobe Engineering Agent** <br/>Hay nuevas capacidades de validación de datos disponibles en Data Engineering Agent. Estas capacidades ayudan a los equipos a evaluar rápidamente la calidad de los datos directamente en Adobe Experience Platform, antes de que los datos se analicen en Customer Journey Analytics. <p>Las capacidades de validación de datos permiten realizar la validación bajo demanda, a nivel de campo y a nivel de conjunto de datos, combinando resúmenes estadísticos con la detección inteligente de valores no válidos o anómalos. </p><p>El uso de capacidades de validación de datos reduce el esfuerzo manual del control de calidad y acelera la incorporación de datos de confianza y las transformaciones en los flujos de trabajo de ingeniería de datos.</p><p>(Vínculo a la documentación a continuación).<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/es/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 19 de mayo de 2026 <p>(Originalmente planificado para su lanzamiento el 31 de marzo de 2026)</p> |
| **Content Analytics: las miniaturas y vistas previas de visualización de línea** <br/>[Las miniaturas y vistas previas](/help/content-analytics/report/report.md) ya están disponibles para los recursos y experiencias en las visualizaciones de línea para Content Analytics. |  | 20 de mayo de 2026 |
| **Data Insights Agent en Agent Orchestrator** <br/> Además de estar disponible en el carril derecho de Customer Journey Analytics, Data Insights Agent ya está disponible como parte de Agent Orchestrator. Esto significa que ahora puede obtener perspectivas que dependen de los datos y las capacidades de Customer Journey Analytics mientras trabaja en otras aplicaciones de Experience Platform, como Journey Optimizer.<p>En Customer Journey Analytics, Data Insights Agent incluye las siguientes mejoras:</p><ul><li>Una experiencia de usuario más coherente con Agent Orchestrator</li><li>Párrafos de resumen explicativos</li><li>Respuestas a las preguntas de &quot;por qué&quot; mediante el análisis de las causas básicas</li><li>Tablas en línea</li><li>¡Y mucho más!&lt;/l></ul><p>(Vínculo a la documentación a continuación).</p> | | Finales de mayo de 2026 |
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenidos multimedia transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |

{style="table-layout:auto"}


## Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Componentes**:
**Conexiones**: AN-449652, AN-444560, AN-442824, AN-440937, AN-440092, AN-439823, AN-429781
**Content Analytics**:
**Análisis guiado**:
**Exportaciones**: AN-438953, AN-437115
**Vistas de datos**: AN-442809
**Implementación**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Informes**: AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242
**Segmentación**:
**Informes programados**:
**Métricas y dimensiones compartidas**:
**Otros**: AN-449159, AN-444661, AN-443900, AN-397985

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
