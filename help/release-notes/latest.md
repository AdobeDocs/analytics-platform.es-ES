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
source-git-commit: 034186edab4bcd66073236e070a37ee9317830e4
workflow-type: tm+mt
source-wordcount: 779
ht-degree: 36%

---

# Notas de la versión actuales de Customer Journey Analytics (agosto de 2026)

**Última actualización**: 4 de agosto de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de agosto de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Mejoras en el lienzo de Recorrido**<br> Ya están disponibles las siguientes mejoras en el lienzo de Recorrido:<ul><li>Compare el recorrido con un lapso de tiempo anterior. Compare el recorrido actual con el recorrido 4 semanas antes, 2 trimestres antes, 1 año antes o con un intervalo de fechas personalizado.</li><li>Para un nodo seleccionado, mostrar los elementos de dimensión principales que aparecen después del nodo seleccionado en cualquier punto del recorrido. Utilícelo cuando el nodo seleccionado sea el evento clave del análisis y desee ver lo que hacen las personas en cualquier momento posterior.<p>Anteriormente, solo se podían mostrar los nodos primarios inmediatos antes o después del nodo seleccionado. </p></li><li>Cambie la forma y el estilo de las flechas entre los nodos. Arrastre las flechas entre los nodos para cambiar la forma (curvitura) de la flecha y haga clic con el botón secundario del mouse (ratón) en una flecha para cambiar su estilo a cualquiera de las siguientes opciones: sólido, discontinuo, punteado, discontinuo-punto o animado.</li></ul><p></p>Para obtener más información, consulte [Configuración de una visualización de lienzo de recorridos](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). |  | 18 de agosto de 2026 |
| **Compatibilidad con etiquetas de uso de datos adicionales**<br> Customer Journey Analytics ahora admite las siguientes etiquetas de uso de datos adicionales para elementos dentro de un conjunto de datos:<ul><li>C2: Restringir la exportación de datos de terceros (disponible ahora)</li><li>C3 - Restringir la combinación de datos directamente identificables (disponible ahora)</li><li>C9: Restringir la ciencia de datos (lanzamiento previsto para agosto)</li></ul><p>Para obtener más información, vea [Etiquetas, directivas y acciones de marketing](/help/data-views/data-governance.md).</p> | | Agosto de 2026 |
| **Filtrado e informes de directivas de consentimiento**<br> Ahora puede informar sobre los visitantes que coinciden con las directivas de consentimiento de Adobe Experience Platform. (Las dimensiones y métricas de la política de consentimiento se agregan a las vistas de datos de la conexión).<p>Además, puede excluir a los visitantes que no consientan antes de que sus datos se introduzcan en Customer Journey Analytics.</p><p>Para obtener más información, consulte Información general sobre creación de informes y filtrado de consentimiento.</p> | | Agosto de 2026 |
| **Planificador de migración: de Adobe Analytics a Customer Journey Analytics**<br> El Planificador de migración proporciona un asistente de migración que automatiza algunas de las tareas más complejas y que requieren más tiempo asociadas con una actualización de Adobe Analytics a Customer Journey Analytics, incluida la creación de esquemas XDM y la migración de AppMeasurement o la extensión de Analytics (etiquetas) a Experience Platform Web SDK. <p>(Vínculo a la documentación a continuación).</p> | | Finales de agosto o septiembre de 2026 |
| **B2B: vinculación de persona a cuenta**<br> Ahora puede usar la vinculación de identidad para vincular la información de cuenta a cada evento del conjunto de datos. Dado que cuenta es el contenedor de informes más alto de Customer Journey Analytics B2B edition, los eventos que no incluyen un ID de cuenta se pierden durante la ingesta.</li></ul><p>(Vínculo a la documentación a continuación).</p> | | Finales de agosto o septiembre de 2026 |
| **Guía de primeras llamadas de la API de informes de CJA**<br> La guía de primeras llamadas de la API de Adobe Customer Journey Analytics proporciona instrucciones y ejemplos para configurar solicitudes de informes básicas. | | 10 de agosto de 2026 |
| **Guía de tendencias de fecha de API de informes de CJA**<br> La guía de tendencias de fecha de API de Adobe Customer Journey Analytics proporciona instrucciones y ejemplos para configurar solicitudes de informes básicas. | | 17 de agosto de 2026 |

### Correcciones en Customer Journey Analytics

**Analysis Workspace**:
**Componentes**:
**Conexiones**:
**Content Analytics**:
**Análisis guiado**:
**Exportaciones**:
**Vistas de datos**:
**Ingesta de datos**:
**Implementación**:
**Report Builder**:
**Sistema de informes**:
**Segmentación**:
**Informes programados**:
**Dimensiones y métricas compartidas**:
**Análisis de audiencia**:
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

