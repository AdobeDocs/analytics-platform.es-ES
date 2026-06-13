---
title: Migración de datos de Google Analytics
description: Conozca el flujo de trabajo general sobre cómo mover datos de Google Analytics a Adobe Experience Platform y ver informes en Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 70%

---

# Migración de datos de Google Analytics

>[!BEGINSHADEBOX]

Esta guía cubre la migración de datos para administradores de. Si eres un analista que busca tus informes de GA4 en Customer Journey Analytics, consulta [Transición de Google Analytics 4 a Customer Journey Analytics](/help/getting-started/ga-to-cja/home.md) e [informes de GA4 en Customer Journey Analytics](/help/getting-started/ga-to-cja/reports.md).

>[!ENDSHADEBOX]

Si es su primera vez en Customer Journey Analytics, es posible que su organización tenga datos existentes en otra plataforma de Analytics, como Google Analytics. Puede seguir estos pasos generales para mover esos datos a Adobe Experience Platform, lo que le permite ver los informes en Customer Journey Analytics.

Los flujos de trabajo se proporcionan tanto para los datos históricos como para la recopilación de datos actuales. Puede seguir uno o ambos flujos de trabajo, según las necesidades de datos de su organización.

## Incorporación de datos históricos de Google Analytics a Adobe Experience Platform

La ingesta de datos históricos (de relleno) implica la exportación de datos de Google y su importación en Adobe Experience Platform. Consulte [Ingesta de datos de Google Analytics en Adobe Experience Platform](backfill.md).

Una vez que haya introducido correctamente los datos históricos en Platform, puede [Configurar la transmisión de datos actuales](streaming.md) o empezar a generar informes inmediatamente sobre los datos rellenados en Customer Journey Analytics [Creando una conexión](/help/connections/create-connection.md).

## Configuración de una implementación de Google Analytics existente para Adobe Experience Platform {#configure}

La ingesta de datos actuales (de streaming) implica el envío de datos al Edge Network de Adobe Experience Platform, que luego reenvía esos datos a Adobe Experience Platform. Consulte [Configuración del streaming de datos de Google Analytics a Adobe Experience Platform](streaming.md).

## Configuración de una conexión y una vista de datos en Customer Journey Analytics

Una vez que introduzca correctamente los datos históricos o configure la recopilación de datos en Adobe Experience Platform, puede [Crear una conexión](/help/connections/create-connection.md) para permitir que Customer Journey Analytics haga referencia a esos datos.

Utilice la conexión para crear una o más [Vistas de datos](/help/data-views/create-dataview.md) para usar en Analysis Workspace.

## Creación de informes

Después de configurar dimensiones y métricas dentro de una vista de datos, puede empezar a usar Analysis Workspace para generar los informes deseados. Consulte [Informe sobre los datos de Google Analytics en Customer Journey Analytics](report.md).
