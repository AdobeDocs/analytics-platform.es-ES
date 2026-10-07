---
title: Notas de la versión actuales de Customer Journey Analytics
description: Vea las notas de la versión más recientes de Customer Journey Analytics, incluidas las nuevas funciones, los problemas solucionados y las versiones pospuestas para el periodo actual.
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
source-git-commit: 0a83f4d08806b4d9b97265989f9d687011b232c3
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 28%
---
# Notas de la versión actuales de Customer Journey Analytics (octubre de 2026)

**Última actualización**: 7 de octubre de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de octubre de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Permiso de solo lectura para el servidor MCP de Customer Journey Analytics**<br/> Los administradores ahora pueden dar a los usuarios acceso de solo lectura al servidor MCP de Customer Journey Analytics. El nuevo elemento de permiso [!UICONTROL MCP de solo lectura] proporciona a los usuarios acceso a todas las herramientas de solo lectura, sin permitirles crear proyectos, segmentos o métricas calculadas.<p>Se cambió el nombre del elemento de permiso [!UICONTROL MCP Access] actual a [!UICONTROL MCP Full Access]. Los usuarios con este permiso mantienen el acceso a todas las herramientas, incluidas las que crean, cambian o eliminan componentes.</p><p>Para obtener más información, consulte [Servidor MCP de Customer Journey Analytics](https://developer.adobe.com/analytics-mcp/docs/cja/).</p> | | 6 de octubre de 2026 |
| **Analizar las experiencias de los clientes LLM en Analysis Workspace con Conversation Insights**<br/> Customer Journey Analytics ahora incorpora datos de chat no estructurados en Analysis Workspace, lo que le permite informar sobre la navegación basada en LLM y las experiencias de compra que ocurren en sus propiedades.<p>Con esta capacidad, puede:</p><ul><li>Recopile solicitudes, respuestas y metadatos de agentes de conversational agents (los agentes personalizados de su organización o Adobe Brand Concierge) mediante Web SDK.</li><li>Analice la intención, el tono y la opinión para que pueda comprender qué preguntan los clientes, cómo responde su agente y cómo se sienten los clientes respecto a sus interacciones.</li><li>Analice a escala utilizando el esquema, los conjuntos de datos y las vistas de datos existentes y, a continuación, obtenga perspectivas en Analysis Workspace.</li><li>Conecte las conversaciones a los resultados vinculando las interacciones de los agentes con sus recorridos de cliente más amplios, de modo que pueda medir el impacto real en la conversión, la participación y mucho más.</li></ul><p>Anteriormente, las experiencias con tecnología LLM eran difíciles de medir y casi imposibles de conectar con los recorridos de clientes existentes.</p><p>Para obtener más información, consulte [Perspectivas de conversación](/help/conversation-insights/overview.md).</p> | | 8 de octubre de 2026<p>(Originalmente planificado para el 22 de septiembre de 2026)</p> |
| **Generar automáticamente descripciones de componentes** <br/>Ahora puede generar automáticamente descripciones para dimensiones, métricas, métricas calculadas, segmentos e intervalos de fechas. Esto permite a los usuarios de Workspace comprender qué componentes utilizar, especialmente en organizaciones con bibliotecas de componentes grandes. <p>Puede generar una descripción para un solo componente o generar descripciones para muchos componentes al mismo tiempo.</p> <p>(Vínculo a la documentación a continuación).<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 de octubre de 2026 |
| **Integración de Adobe Brand Visibility**<br/> Conecte Adobe Brand Visibility con los datos de Customer Journey Analytics de su organización para que pueda medir cómo la detección impulsada por IA se traduce en participación real en el sitio web y resultados comerciales.<p>(Vínculo a la documentación a continuación).</p> | | Octubre de 2026 |


### Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Componentes**: AN-492523
**Conexiones**: AN-492236
**Content Analytics**:
**Análisis guiado**: AN-495592
**Exportaciones**: AN-495077, AN-494337, AN-486563, AN-469919, AN-462560, AN-462372
**Vistas de datos**: AN-492093, AN-467770, AN-455367, AN-444467
**Ingesta de datos**: AN-496439, AN-495339, AN-493456, AN-491984, AN-490515, AN-490479, AN-470065
**Implementación**:
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Informes**: AN-495661, AN-493562, AN-487058, AN-478768
**Segmentación**:
**Informes programados**: AN-491103, AN-468049
**Métricas y dimensiones compartidas**: AN-493722
**Análisis de audiencia**: AN-469101
**Otro**: AN-493865

## Funciones aplazadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Informes de población total**<br/> Ahora puede analizar y crear informes sobre entidades definidas en conjuntos de datos de búsqueda y perfil que existen en una conexión de Customer Journey Analytics. Que el análisis y los informes van más allá de la serie de eventos basada en el tiempo de conjuntos de datos de eventos. <p>Esta capacidad habilita nuevas clases de consultas, métricas y definiciones de audiencia que reflejan el ámbito completo de la base de clientes de una empresa.</p><p>(Vínculo a la documentación a continuación).</p> | | Por determinar<p>(Originalmente planificado para el 22 de septiembre de 2026)</p> |
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenidos multimedia transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenido en directo compatible con la carga de datos programada:</p><ul><li>Plataformas RÁPIDAS (TV gratuita compatible con anuncios)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para rastrear contenido en vivo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 de octubre de 2025 | Por determinar<p>(Originalmente planificado para el 29 de octubre de 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notas de la versión anteriores de Customer Journey Analytics de 2026](/help/release-notes/2026.md)
>* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
>* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
>* [Notas de la versión de CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
>* [Actualizaciones de documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)

