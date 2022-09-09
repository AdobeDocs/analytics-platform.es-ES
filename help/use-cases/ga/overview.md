---
title: Migración de datos de Google Analytics a Customer Journey Analytics
description: Conozca el flujo de trabajo general sobre cómo mover datos de Google Analytics a Adobe Experience Platform y ver informes en Customer Journey Analytics.
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Migración de datos de Google Analytics a Customer Journey Analytics

Si es nuevo en Customer Journey Analytics, es posible que su organización tenga datos existentes en otra plataforma de Analytics, como Google Analytics. Puede seguir estos pasos generales para mover esos datos a Adobe Experience Platform, lo que le permite ver los informes en Customer Journey Analytics.

Los flujos de trabajo se proporcionan tanto para los datos históricos como para la recopilación de datos actuales. Puede seguir uno o ambos flujos de trabajo, según las necesidades de datos de su organización.

## Incorporar datos históricos de Google Analytics a Adobe Experience Platform

La ingesta de datos históricos (de relleno) implica la exportación de datos de Google y la importación de esos datos en Adobe Experience Platform. Consulte [Ingesta de datos de Google Analytics en Adobe Experience Platform](backfill.md).

Una vez que haya introducido correctamente los datos históricos en Platform, puede: [Configurar la transmisión de datos actuales](streaming.md), o empiece a informar inmediatamente sobre los datos rellenados en CJA de [Creación de una conexión](/help/connections/create-connection.md).

## Configurar una implementación de Google Analytics existente para Adobe Experience Platform {#configure}

La ingesta de datos actuales (de flujo continuo) implica el envío de datos a Adobe Experience Edge, que después reenvía esos datos a Adobe Experience Platform. Consulte [Configuración de datos de Google Analytics de flujo continuo en Adobe Experience Platform](streaming.md).

## Configuración de una conexión y una vista de datos en CJA

Una vez que ingrese correctamente los datos históricos o configure la recopilación de datos en Adobe Experience Platform, puede [Crear una conexión](/help/connections/create-connection.md) para permitir que el Customer Journey Analytics haga referencia a esos datos.

Utilice la conexión para crear una o más [Vistas de datos](/help/data-views/create-dataview.md) para usar en Analysis Workspace.

## Crear informes

Después de configurar dimensiones y métricas dentro de una vista de datos, puede empezar a usar Analysis Workspace para generar los informes deseados. Consulte [Informar sobre los datos de los Google Analytics en Customer Journey Analytics](report.md).
