---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9a1bb816b40881d979549ac1ceabc5d6ab7e99c6
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 78%

---

# Notas de la versión actual de Adobe Customer Journey Analytics (abril de 2026)

**Última actualización**: 22 de abril de 2026

Estas notas de la versión abarcan el período de abril de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Compatibilidad con el idioma italiano**<br/> La configuración regional del italiano (it-IT) ahora es compatible con Analysis Workspace en Customer Journey Analytics. <p>Customer Journey Analytics es compatible con todos los idiomas admitidos en la interfaz de usuario de Experience Platform, tal como se describe en [Compatibilidad con exploradores e idiomas para la interfaz de usuario de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>Puede [cambiar el idioma predeterminado](https://experienceleague.adobe.com/es/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) en Experience Platform.</p> | | 8 de abril de 2026 |
| **Validación de datos en Adobe Engineering Agent** <br/>Hay nuevas capacidades de validación de datos disponibles en Data Engineering Agent. Estas capacidades ayudan a los equipos a evaluar rápidamente la calidad de los datos directamente en Adobe Experience Platform, antes de que los datos se analicen en Customer Journey Analytics. <p>Las capacidades de validación de datos permiten realizar la validación bajo demanda, a nivel de campo y a nivel de conjunto de datos, combinando resúmenes estadísticos con la detección inteligente de valores no válidos o anómalos. </p><p>El uso de capacidades de validación de datos reduce el esfuerzo manual del control de calidad y acelera la incorporación de datos de confianza y las transformaciones en los flujos de trabajo de ingeniería de datos.</p><p>(Vínculo a la documentación a continuación).<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/es/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Mayo de 2026 <p>(Originalmente planificado para su lanzamiento el 31 de marzo de 2026)</p> |
| **Servidores MCP para Customer Journey Analytics** <br/>Los servidores MCP (Model Context Protocol) de Analytics le permiten conectar un cliente MCP compatible a Adobe Customer Journey Analytics. Una vez conectado, el cliente de MCP puede invocar herramientas específicas del producto para recuperar datos, ejecutar consultas o realizar operaciones admitidas como parte de un flujo de trabajo LLM o agéntico. Para obtener más información, consulte [Servidores MCP de Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Si ha utilizado estos servidores MCP durante el período beta, tenga en cuenta que hay diferentes direcciones URL entre los extremos beta y de producción. Asegúrese de que todos los flujos de trabajo agénticos creados durante el periodo beta se actualicen para utilizar los extremos de producción antes del 31 de mayo.</p> | | jueves, 29 de abril de 2026 |
| **Compatibilidad de Content Analytics con experiencias nativas de aplicaciones móviles**<br/> Las organizaciones pueden ampliar su análisis del rendimiento del contenido a aplicaciones de iOS y Android, capturando recursos de imagen y elementos de experiencia granulares para comprender qué contenido en la aplicación impulsa la participación del usuario y los resultados empresariales.<p>Las perspectivas están disponibles para todos los clientes de Adobe Content Analytics.</p> | viernes, 30 de abril de 2026 | Por determinar |
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenidos multimedia transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |
| **Sistema de informes de API en varias dimensiones**<br/> Informe en varias dimensiones en una única solicitud de API y realice búsquedas a nivel de dimensión. [Más información](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | Marzo de 2026 |
| **Ordenación de API en varias columnas**<br/> Ordene varios objetos de dimensiones y métricas en una solicitud de API. Combine dimensiones y métricas en la misma definición de ordenación. [Más información](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | Marzo de 2026 |

## Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Componentes**:
**Conexiones**: AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**Análisis guiado**:
**Exportaciones**:
**Vistas de datos**: AN-442809, AN-434824, AN-434210, AN-424000
**Implementación**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Sistema de informes**: AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentación**:
**Informes programados**:
**Métricas y dimensiones compartidas**:
**Otros**: AN-423359, AN-406242, AN-397985

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
