---
title: Comparación de productos de Customer Journey Analytics
description: Compare los atributos del cliente de las herramientas de creación de informes y exportación de Recorrido Analytics, como Analysis Workspace, Report Builder, Full Table Export, Fuentes de datos, API y MCP.
keywords: flujo de navegación;fuente de datos;fuente de datos;fuente de datos;comparación de productos;Analysis Workspace;Report Builder;Exportación de tabla completa
feature: Components
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 44%

---


# Comparación de productos de Analytics

Utilice esta página para comparar las herramientas de creación de informes y exportación de Customer Journey Analytics en atributos clave para ayudarle a elegir la herramienta adecuada para sus necesidades de análisis o exportación de datos.

| Nombre del producto y vínculo de ayuda | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Exportación de tablas completas](/help/analysis-workspace/export/export-cloud.md) | [Archivos de fuentes de datos](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP | Extensión de BI | Compañero |
|---|---|---|---|---|---|---|---|---|
| **Método de acceso** | Explorador | Microsoft Excel | Explorador | Configurar mediante el explorador | Herramientas de API de RESTful | Herramientas compatibles con MCP | Herramientas de BI | Herramientas compatibles con MCP |
| **Granularidad de los datos** | Agregado | Agregado | Agregado | Evento | Agregado | Agregado | Agregado | Agregado |
| **Experience Cloud ID (ECID) disponible** | No | No | No | Sí | No | No | No | No |
| **Marca de tiempo disponible** | No | No | No | Sí | No | No | No | No |
| **Nivel de procesamiento** | Procesamiento completo | Procesamiento completo, con informe en tiempo real independiente | Procesamiento completo | Procesamiento completo | Procesamiento completo | Procesamiento completo | Procesamiento completo | Procesamiento completo |
| **Donde se aplica el filtrado de bots** | Dentro del [flujo de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/bot-detection) o dentro de [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Dentro del [flujo de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/bot-detection) o dentro de [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Dentro del [flujo de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/bot-detection) o dentro de [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Dentro del [flujo de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/bot-detection) o dentro de [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) |  |  | Dentro del [flujo de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/bot-detection) o dentro de [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | |
| **Límite de fila visible (antes de la paginación)** | 400 | 50,000 | Límite de 3 millones, 30 millones, 150 millones o 300 millones, según el nivel | Depende del nivel | 50,000 | 50,000 | 50,000 | 50,000 |
| **Vistas de datos múltiples** | Sí, un proyecto puede contener datos de varias vistas de datos | Sí, un proyecto puede contener datos de varias vistas de datos | No, una exportación solo puede contener datos de una vista de datos | No, una exportación solo puede contener datos de una vista de datos | No, cada consulta solo puede hacer referencia a una vista de datos | No, cada consulta solo puede hacer referencia a una vista de datos | No, cada consulta solo puede hacer referencia a una vista de datos | Sí, si el usuario lo solicita |
| **Número de columnas de dimensión** | Hasta 5 | ? | Hasta 10 | Ilimitado | Hasta 5 | ? | ? | ? |
| **Número de columnas de métricas** | ? | ? | Hasta 10 | Ilimitado | ? | ? | ? | ? |
| **Segmentación** <br> [Más información](/help/components/segments/seg-overview.md) | Sí | Sí | Sí | Sí, con [limitaciones](/help/components/exports/cja-data-feeds/df-segmentation.md) | Sí | Sí | Sí | Sí |
| **Métricas calculadas** <br> [Más información](/help/components/calc-metrics/calc-metr-overview.md) | Sí | Sí | Sí, con [limitaciones](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | No | Sí | Sí | Sí | Sí |
| **Campos derivados** <br> [Más información](/help/data-views/derived-fields/derived-fields.md) | Sí | Sí | Sí | Sí | Sí | Sí | Sí | Sí |
| **Atribución** <br> [Más información](/help/analysis-workspace/attribution/overview.md) | Sí | Limitado | Sí, con [limitaciones](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) | No | Sí | Sí | Sí | Sí |
| **Envío programado** | Sí | Sí | Sí | Sí | — | — | — | — |
| **Destinos de envío** | Correo electrónico | Correo electrónico | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — | — | — |

{style="table-layout:auto"}
