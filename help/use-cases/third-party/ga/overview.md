---
title: Migración de datos de Google Analytics
description: Conozca el flujo de trabajo general sobre cómo mover datos de Google Analytics a Adobe Experience Platform y ver informes en Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
source-git-commit: 8262539078c57e32bc3195ef669325fa4889bea0
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 79%

---

# Migración de datos de Google Analytics

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
