---
description: Descubra las diferencias entre las alertas en Customer Journey Analytics y Adobe Analytics
title: Comparación de funciones de alertas entre Customer Journey Analytics y Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
TQID: https://experienceleague.adobe.com/NEm3Mu7q6RDKbCyG-PJzOFPrjJF4Y-unHgyBXyKd1HM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
    internal-label: Alerts
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 4f3c4a214bb9676ced6fe3c9627c969413013790
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 23%
---
# Comparación de funciones de alertas entre Customer Journey Analytics y Adobe Analytics

El proceso de utilización de alertas en Customer Journey Analytics es casi idéntico al de las alertas en Adobe Analytics. Sin embargo, existen diferencias importantes. Las siguientes secciones describen las diferencias clave.

## Las alertas horarias pueden no ser prácticas para determinados tipos de datos

Como puede introducir varios tipos de datos en Adobe Experience Platform, no todos los datos que se pueden incluir en una alerta son prácticos para una alerta por hora. Ciertos tipos de datos no se pueden ingerir de forma fiable y están disponibles dentro de las restricciones de una hora.

Para obtener más información, consulte [Los tiempos de ingesta de datos varían](#data-ingestion-times-vary).

## Los tiempos de ingesta de datos varían

El tiempo necesario antes de que los datos se completen y estén disponibles para la creación de informes en Customer Journey Analytics varía según la organización.

Esto se debe a las siguientes razones:

* Capacidad de Platform para albergar todo tipo de esquemas y tipos de datos

  A diferencia de Adobe Analytics (que informa solamente de datos web), [se pueden ingerir muchos tipos diferentes de datos en Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) para su registro en Customer Journey Analytics, y no todos los tipos de datos se pueden enviar secuencialmente y en tiempo real.

* Retraso en el envío de datos por lotes a conjuntos de datos de Platform

  Aunque es posible que algunos datos estén disponibles para generar informes antes, todos los [datos por lotes se incorporan a un conjunto de datos de Platform](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), que generalmente oscila entre 3 y 9 horas después del tiempo del evento de datos. Para que las alertas sean precisas, la ingesta de datos debe ser completa, con todos los datos por lotes disponibles en el conjunto de datos. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Por estos motivos, la ingesta de datos para los distintos tipos de datos de evento que se pueden introducir se completa solo después de algún retraso, normalmente en un intervalo de 3 a 9 horas después del tiempo de evento de datos. Para que las alertas sean precisas, los datos de evento de un intervalo de eventos determinado deben estar completos, lo que significa que Adobe ya no recibe datos de evento para el intervalo de eventos especificado.

Para tener en cuenta este retraso en el tiempo de ingesta, las alertas tienen un retraso predeterminado de 9 horas antes de enviarse.

Puede ajustar el retraso predeterminado de 9 horas a cualquier valor entre 0 y 24 horas. Sin embargo, si se reduce el retraso por debajo de 9 horas, puede indicar que está generando informes sobre datos incompletos, lo que da como resultado una información de alerta inexacta.

Para obtener más información sobre cómo ajustar la demora y los factores que debe tener en cuenta al hacerlo, consulte [Crear alertas](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Menos formas de crear alertas

En Analysis Workspace en Adobe Analytics, puede [crear alertas desde Analysis Workspace de varias formas](https://experienceleague.adobe.com/es/docs/analytics/components/alerts/alert-builder). En Customer Journey Analytics, solo puede [crear una alerta](alert-builder.md) en Analysis Workspace a partir de una selección en una tabla de forma libre.

Tanto Adobe Analytics como Customer Journey Analytics admiten la creación de alertas a través de [Alert Manager](alert-manager.md)
