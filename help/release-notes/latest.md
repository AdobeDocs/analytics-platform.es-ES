---
title: Notas de la versión actuales de Customer Journey Analytics
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 587265d7613f732af811a77a947b0ce96ccad9bf
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 39%

---

# Notas de la versión actuales de Customer Journey Analytics (julio de 2026)

**Última actualización**: 8 de julio de 2026

Estas notas de la versión abarcan el periodo de la versión de julio de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Análisis de subeventos** <br/>El análisis de subeventos le permite analizar los datos en un nivel más granular que el nivel de evento. En lugar de filtrar eventos completos, puede segmentar contenedores individuales dentro de un evento. <p>Por ejemplo, puede segmentar una categoría de producto específica sin incluir todos los demás productos comprados en el mismo pedido. También puede definir objetos o matrices que formen parte de los datos de evento como contenedores independientes dentro de una vista de datos.</p><p>(Vínculo a la documentación a continuación).</p> | 15 de julio de 2026 | Finales de julio de 2026 |
| **B2B edition: la compatibilidad con conjuntos de datos ad hoc y relacionales** <br/>Los conjuntos de datos ad hoc y relacionales ahora también se admiten en conexiones basadas en cuentas en Customer Journey Analytics B2B edition.<p>(Vínculo a la documentación a continuación).</p> | | 20 de julio de 2026 |
| **Content Analytics: datos de medios de pago** <br/>Los medios de pago ya están disponibles como un tercer canal para Content Analytics.<p>(Vínculo a la documentación a continuación).</p> | | 31 de julio de 2026 |
| **Actualización de la interfaz de uso de conexiones** <br/>En la interfaz de uso al administrar las conexiones, ahora puede ver los detalles de uso de cada módulo individual, como Customer Journey Analytics o Customer Journey Analytics B2B edition. <p>Además, ahora puede desglosar los informes de uso de cada uno de los módulos por mes.</p><p>(Vínculo a la documentación a continuación).</p> | | 31 de julio de 2026 |
| **Colaborador empresarial de CX: valide sus datos al migrar de Adobe Analytics a Customer Journey Analytics** <br/>Una nueva habilidad de colaborador empresarial de CX le permite validar los datos de su implementación de Customer Journey Analytics con los datos de su implementación de Adobe Analytics existente. <p>Esta aptitud compara automáticamente cada dimensión, métrica y tendencia según sea necesario. También puede comparar todos los grupos de informes de Adobe Analytics con todas las vistas de datos de Customer Journey Analytics. A continuación, la aptitud genera perspectivas y recomendaciones impulsadas por IA que puede implementar para facilitar la migración a Customer Journey Analytics.</p><p>(Vínculo a la documentación a continuación).</p> | | Finales de julio de 2026 |
| **Clasificaciones en línea**<br/>[ Las clasificaciones en línea](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md#inline-classifications) le permiten cambiar el nombre de filas o combinarlas en una tabla de forma libre. Y para crear un campo derivado a partir de las filas modificadas de una tabla. | | 20 de julio de 2026 |

### Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Componentes**:
**Conexiones**: AN-457065
**Content Analytics**:
**Análisis guiado**:
**Exportaciones**:
**Vistas de datos**: AN-453201
**Ingesta de datos**:
**Implementación**:
**Report Builder**: AN-457533, AN-453683
**Informes**: AN-457607, AN-447692, AN-451259, AN-455713
**Segmentación**:
**Informes programados**: AN-450715
**Dimensiones y métricas compartidas**:
**Análisis de audiencia**:
**Otro**: AN-457063

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

