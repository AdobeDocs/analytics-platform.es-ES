---
title: Extensión de BI de Customer Journey Analytics
description: Describe cómo usar la extensión de BI para introducir datos digitales en sus propias herramientas de BI o en el lago de datos para usarlos con conjuntos de datos adicionales.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 669a1305-3e37-4ca2-8178-a89a27958e5d
autotag-review: '2026-05-19T08:00:39.048Z'
TQID: 'https://experienceleague.adobe.com/BgO7hQlR2J3o-nD38ZIg2ILUTwDKGfSXu-i-bEo5SJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 25%
---
# Extensión de BI

Este artículo describe cómo se puede usar [!DNL Customer Journey Analytics BI extension] para implementar el siguiente [caso de uso de exportación de datos](overview.md):

* Herramientas de Data Lake, Data Warehouse o BI

## Introducción

La exportación de datos mediante [!DNL Customer Journey Analytics BI extension] le permite exportar datos desde las vistas de datos de Customer Journey Analytics.

![extensión de BI](../assets/bi-extension.png)

## Más información

[!DNL Customer Journey Analytics BI extension] habilita el acceso SQL a las [vistas de datos](/help/data-views/data-views.md) que ha definido en Customer Journey Analytics. Sus ingenieros y analistas de datos están más familiarizados con Power BI, Tableau u otras herramientas de inteligencia empresarial y visualización (también denominadas herramientas de BI). Ahora pueden crear informes y paneles de control basados en las mismas vistas de datos que utilizan los usuarios de Customer Journey Analytics al crear sus proyectos de Analysis Workspace.

La extensión de BI devuelve datos agregados, no filas de nivel de evento sin procesar. De forma predeterminada, cada consulta devuelve 50 filas para un intervalo de fechas de 30 días, pero puede anular el límite de filas a un máximo de 50 000 filas y el intervalo de fechas a su propio intervalo personalizado. Vea [Valores predeterminados y limitaciones](../../data-views/bi-extension.md#defaults-and-limitations) para obtener más información.

Para obtener más información, consulte la documentación detallada sobre la [extensión de BI](../../data-views/bi-extension.md).
