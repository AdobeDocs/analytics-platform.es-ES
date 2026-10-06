---
title: Notas de la versión actuales de Customer Journey Analytics
description: Vea las notas de la versión más recientes de Customer Journey Analytics, incluidas las nuevas funciones, los problemas solucionados y las versiones pospuestas para el periodo actual.
hold: true
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 4f62a406436915d581ab30f26b82544388957782
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 29%
---
# Notas de la versión actuales de Customer Journey Analytics (septiembre de 2026)

**Última actualización**: 9 de septiembre de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de septiembre de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Analizar las experiencias de los clientes LLM en Analysis Workspace con Conversation Insights**<br/> Customer Journey Analytics ahora incorpora datos de chat no estructurados en Analysis Workspace, lo que le permite informar sobre la navegación basada en LLM y las experiencias de compra que ocurren en sus propiedades.<p>Con esta capacidad, puede:</p><ul><li>Recopile solicitudes, respuestas y metadatos de agentes de conversational agents (los agentes personalizados de su organización o Adobe Brand Concierge) mediante Web SDK.</li><li>Analice la intención, el tono y la opinión para que pueda comprender qué preguntan los clientes, cómo responde su agente y cómo se sienten los clientes respecto a sus interacciones.</li><li>Analice a escala utilizando el esquema, los conjuntos de datos y las vistas de datos existentes y, a continuación, obtenga perspectivas en Analysis Workspace.</li><li>Conecte las conversaciones a los resultados vinculando las interacciones de los agentes con sus recorridos de cliente más amplios, de modo que pueda medir el impacto real en la conversión, la participación y mucho más.</li></ul><p>Anteriormente, las experiencias con tecnología LLM eran difíciles de medir y casi imposibles de conectar con los recorridos de clientes existentes.</p><p>Para obtener más información, consulte [Información sobre la conversación](/help/conversation-insights/overview.md)</p> | | 8 de octubre de 2026<p>(Originalmente planificado para el 22 de septiembre de 2026)</p> |
| **Generar automáticamente descripciones de componentes** <br/>Ahora puede generar automáticamente descripciones para dimensiones, métricas, métricas calculadas, segmentos e intervalos de fechas. Esto permite a los usuarios de Workspace comprender qué componentes utilizar, especialmente en organizaciones con bibliotecas de componentes grandes. <p>Puede generar una descripción para un solo componente o generar descripciones para muchos componentes al mismo tiempo.</p> <p>(Vínculo a la documentación a continuación).<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 de octubre de 2026 |
| **Integración de Adobe Brand Visibility**<br/> Conecte Adobe Brand Visibility con los datos de Adobe Analytics de su organización para que pueda medir cómo la detección impulsada por IA se traduce en participación real en el sitio web y resultados comerciales.<p>(Vínculo a la documentación a continuación).</p> | | Octubre de 2026</p> |


### Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801, AN-488821, AN-488452, AN-486517, AN-478930, AN-468325
**Componentes**:
**Conexiones**: AN-451458, AN-365942
**Content Analytics**:
**Análisis guiado**: AN-485600
**Exportaciones**: AN-489161, AN-467131, AN-464746, AN-469034, AN-447252, AN-437803, AN-394444
**Vistas de datos**: AN-478732, AN-468836, AN-467851, AN-487651, AN-423592
**Ingesta de datos**: AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433, AN-490288, AN-487500, AN-390916, AN-342311
**Implementación**:
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695, AN-492330, AN-490564, AN-468293, AN-460921
**Informes**: AN-479145, AN-469095, AN-468070, AN-467786, AN-456684, AN-465257, AN-422685, AN-406114, AN-356706, AN-322733
**Segmentación**: AN-486561, AN-278260
**Informes programados**: AN-479157
**Dimensiones y métricas compartidas**:
**Análisis de audiencia**: AN-468237, AN-462553
**Otros**: AN-469601, AN-462817, AN-362308, AN-349757, AN-326432, AN-326345, AN-324341, AN-309317

## Funciones aplazadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Informes de población total**<br/> Ahora puede analizar y crear informes sobre entidades definidas en conjuntos de datos de búsqueda y perfil que existen en una conexión de Customer Journey Analytics. Que el análisis y los informes van más allá de la serie de eventos basada en el tiempo de conjuntos de datos de eventos. <p>Esta capacidad habilita nuevas clases de consultas, métricas y definiciones de audiencia que reflejan el ámbito completo de la base de clientes de una empresa.</p><p>(Vínculo a la documentación a continuación).</p> | | Por determinar<p>(Originalmente planificado para el 22 de septiembre de 2026)</p> |
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenidos multimedia transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenido en directo compatible con la carga de datos programada:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para rastrear contenido en vivo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 de octubre de 2025 | Por determinar<p>(Originalmente planificado para el 29 de octubre de 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notas de la versión anteriores de Customer Journey Analytics de 2026](/help/release-notes/2026.md)
>* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
>* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
>* [Notas de la versión de CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
>* [Actualizaciones de documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)

