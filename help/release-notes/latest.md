---
title: Notas de la versión actuales de Customer Journey Analytics
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
hold: true
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 278d35000551d8a2a149683bfe073a5085b593bd
workflow-type: tm+mt
source-wordcount: 1144
ht-degree: 23%

---

# Notas de la versión actuales de Customer Journey Analytics (septiembre de 2026)

**Última actualización**: 8 de septiembre de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de septiembre de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Complemento de servidor MCP de Customer Journey Analytics**<br/> Use nuevos complementos de servidor MCP de Customer Journey Analytics para ChatGPT y Claude para acceder rápidamente a sus datos. <p>Para obtener más información, consulte la [guía del complemento ChatGPT](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt) y la [guía del conector Claude](https://developer.adobe.com/analytics-mcp/docs/guides/claude).</p> | 1 de septiembre de 2026 | 1 de septiembre de 2026 |
| **Compatibilidad con etiquetas de uso de datos adicionales**<br> Customer Journey Analytics ahora admite las siguientes etiquetas de uso de datos adicionales para elementos dentro de un conjunto de datos:<ul><li>C2: Restringir la exportación de datos de terceros (disponible ahora)</li><li>C3 - Restringir la combinación de datos directamente identificables (disponible ahora)</li><li>C9: Restringir la ciencia de datos (cuya publicación está prevista en agosto o septiembre)</li></ul><p>Para obtener más información, vea [Etiquetas, directivas y acciones de marketing](/help/data-views/data-governance.md).</p> | | 3 de septiembre de 2026 |
| **Limitar segmentos al intervalo de fechas del informe**<br/> Los datos de un informe de Workspace pueden extenderse más allá del intervalo de fechas del informe cuando un segmento incluye componentes de intervalo de fechas.<p>Ahora hay disponible una nueva opción que le permite limitar los resultados al intervalo de fechas de la creación de informes independientemente de cualquier componente de fecha incluido en el segmento. <p>Esta opción está disponible al crear o modificar un segmento cuyo contenedor de nivel superior sea Persona.</p><p>Para obtener más información, consulte [Generar segmentos](/help/components/segments/seg-builder.md#components).</p> | 26 de agosto de 2026 | 9 de septiembre de 2026 |
| **Filtrado e informes de directivas de consentimiento**<br> Ahora puede informar sobre los visitantes que coinciden con las directivas de consentimiento de Adobe Experience Platform. (Las dimensiones y métricas de la política de consentimiento se agregan a las vistas de datos de la conexión).<p>Además, puede excluir a los visitantes que no consientan antes de que sus datos se introduzcan en Customer Journey Analytics.</p><p>(Vínculo a la documentación a continuación).<!--For more information, see Consent reporting and filtering overview.--></p> | | Septiembre de 2026 |
| **Limitar segmentos al intervalo de fechas del informe**<br/> Los datos de un informe de Workspace pueden extenderse más allá del intervalo de fechas del informe cuando un segmento incluye componentes de intervalo de fechas.<p>Ahora hay disponible una nueva opción que le permite limitar los resultados al intervalo de fechas de la creación de informes independientemente de cualquier componente de fecha incluido en el segmento. <p>Esta opción está disponible al crear o modificar un segmento cuyo contenedor de nivel superior sea Persona.</p><p>Para obtener más información, consulte [Generar segmentos](/help/components/segments/seg-builder.md#components).</p> | 26 de agosto de 2026 | 9 de septiembre de 2026 |
| **Analizar las experiencias de los clientes LLM en Analysis Workspace con Conversation Insights**<br/> Customer Journey Analytics ahora incorpora datos de chat no estructurados en Analysis Workspace, lo que le permite informar sobre la navegación basada en LLM y las experiencias de compra que ocurren en sus propiedades.<p>Con esta capacidad, puede:</p><ul><li>Recopile solicitudes, respuestas y metadatos de agentes de conversational agents (los agentes personalizados de su organización o Adobe Brand Concierge) mediante Web SDK.</li><li>Analice la intención, el tono y la opinión para que pueda comprender qué preguntan los clientes, cómo responde su agente y cómo se sienten los clientes respecto a sus interacciones.</li><li>Analice a escala utilizando el esquema, los conjuntos de datos y las vistas de datos existentes y, a continuación, obtenga perspectivas en Analysis Workspace.</li><li>Conecte las conversaciones a los resultados vinculando las interacciones de los agentes con sus recorridos de cliente más amplios, de modo que pueda medir el impacto real en la conversión, la participación y mucho más.</li></ul><p>Anteriormente, las experiencias con tecnología LLM eran difíciles de medir y casi imposibles de conectar con los recorridos de clientes existentes.</p><p>(Vínculo a la documentación a continuación).</p> | | 22 de septiembre de 2026 |
| **Informes de población total**<br/> Ahora puede analizar y crear informes sobre entidades definidas en conjuntos de datos de búsqueda y perfil que existen en una conexión de Customer Journey Analytics. Ese análisis y la creación de informes van más allá de la serie de eventos basada en el tiempo de conjuntos de datos de eventos. <p>Esta capacidad habilita nuevas clases de consultas, métricas y definiciones de audiencia que reflejan el ámbito completo de la base de clientes de una empresa.</p><p>(Vínculo a la documentación a continuación).</p> | | 22 de septiembre de 2026 |
| **Alertas por hora**<br/> Ahora puede establecer la granularidad horaria de una alerta en Por hora.<p>Las alertas horarias están destinadas a los datos que llegan en una hora determinada. Si los datos tienen una latencia superior a una hora, una granularidad más larga garantiza que la alerta evalúe los datos completos. Consulte con un ingeniero de datos si no está seguro de cuánto tiempo tardan los datos en llegar.</p> | | Septiembre de 2026 |
| **La entrega de alertas se ajusta estrictamente a la demora configurada**<br/> Las alertas se entregan ahora al final de la ventana de demora establecida, independientemente de si los datos se han completado o se siguen recibiendo para el intervalo de eventos especificado. Los datos que llegan después de la ventana de retraso no se incluyen en la alerta.<p>Anteriormente, las alertas incluían una comprobación de procesamiento en segundo plano que esperaba los datos que llegaban tarde, incluso si eso significaba que las alertas se entregaban después de la ventana de retraso configurada.</p> | | Septiembre de 2026 |
| **Integración de Adobe Brand Visibility**<br/> Conecte Adobe Brand Visibility con los datos de Customer Journey Analytics de su organización para que pueda medir cómo la detección impulsada por IA se traduce en participación real en el sitio web y resultados comerciales.<p>(Vínculo a la documentación a continuación).</p> | | Septiembre de 2026 |

### Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373
**Componentes**:
**Conexiones**: AN-451458
**Content Analytics**:
**Análisis guiado**: AN-485600
**Exportaciones**: AN-489161, AN-467131, AN-464746
**Vistas de datos**: AN-478732, AN-468836, AN-467851
**Ingesta de datos**: AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433
**Implementación**:
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695
**Informes**: AN-479145, AN-469095, AN-468070, AN-467786, AN-456684
**Segmentación**: AN-486561
**Informes programados**:
**Dimensiones y métricas compartidas**:
**Análisis de audiencia**: AN-468237, AN-462553
**Otros**:

## Funciones aplazadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenido de medios de streaming transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para rastrear contenido en vivo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 de octubre de 2025 | Por determinar<p>(Originalmente planificado para el 29 de octubre de 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notas de la versión anteriores de Customer Journey Analytics de 2026](/help/release-notes/2026.md)
>* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
>* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
>* [Notas de la versión de CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
>* [Actualizaciones de documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)

