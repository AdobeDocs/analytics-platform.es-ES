---
title: Customer Journey Analytics Export full table
description: Describe cómo utilizar la funcionalidad Exportar tabla completa para validar los datos o utilizar los datos para inteligencia artificial o aprendizaje automático.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: ee004948-3025-434b-a90b-8aa185800820
autotag-review: '2026-05-19T09:39:35.989Z'
TQID: 'https://experienceleague.adobe.com/5lP3PKpCpxkeyH34327gieZ48KFkEai4DF2SC0H4E2U'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 4%
---
# Exportar tabla completa

Este artículo describe cómo se puede usar la funcionalidad [!DNL Export full table] para implementar el siguiente [caso de uso de exportación de datos](overview.md):

* Validación de datos
* Preparación para AI/ML

## Introducción

Exportar datos mediante [!DNL Customer Journey Analytics Full Table Export] le permite exportar datos de sus tablas improvisadas en Customer Journey Analytics Analysis Workspace.

![extensión de BI](../assets/export-full-table.png)

## Más información

Para exportar todo el contenido de cualquier tabla de forma libre que cree en Analysis Workspace directamente a destinos de nube designados, utilice la funcionalidad Exportar tabla completa.

Exportar tabla completa admite hasta 10 dimensiones y 10 métricas por informe, e incluye métricas calculadas y segmentación. Según el nivel de licencia, puede exportar 3 millones, 30 millones, 150 millones o 300 millones de filas por exportación, lo que supera el límite de 50 000 filas de otros métodos de exportación. Los destinos admitidos son Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 y Snowflake. Vea [Ventajas de la exportación de tabla completa](/help/analysis-workspace/export/export-cloud.md#advantages) para obtener más información.

Para obtener más información, consulte la documentación detallada sobre [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md).
