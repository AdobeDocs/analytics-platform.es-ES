---
description: Descubra cómo las alertas inteligentes difieren en Customer Journey Analytics de Adobe Analytics
title: Customer Journey Analytics de comparación de funciones de alertas inteligentes y Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: 74ad39f6ccc6436f7c8540b7d8b69b20b93d2b5c
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Comparación de funciones de alertas inteligentes: Customer Journey Analytics y Adobe Analytics

{{release-limited-testing}}

El proceso de utilización de las Alertas inteligentes en Customer Journey Analytics es casi idéntico al de las Alertas inteligentes en Adobe Analytics. Sin embargo, hay diferencias importantes.

Las siguientes secciones describen las diferencias clave.

## Las alertas horarias no están disponibles en el Customer Journey Analytics

Las alertas horarias no están disponibles en Customer Journey Analytics como lo están en Adobe Analytics. En Customer Journey Analytics, las alertas se pueden configurar para alertas diarias, semanales o mensuales.

Esto se debe a las distintas formas en que se pueden ingerir los datos en Adobe Experience Platform antes de notificarlos en Customer Journey Analytics. La integridad y disponibilidad de los datos no se pueden lograr de forma fiable en una hora, lo que hace que las alertas horarias no sean prácticas debido al alto potencial de datos incompletos. Para obtener más información, consulte [Los tiempos de ingesta de datos varían](#data-ingestion-times-vary-in-customer-journey-analytics).

## Los tiempos de ingesta de datos varían en el Customer Journey Analytics

El tiempo necesario antes de que los datos se completen y estén disponibles para su notificación en Customer Journey Analytics varía según la organización.

Esto se debe a las siguientes razones:

* Capacidad de Platform para albergar todo tipo de esquemas y tipos de datos

  A diferencia de Adobe Analytics (que informa solamente de datos web), [se pueden ingerir muchos tipos diferentes de datos en Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) para su registro en Customer Journey Analytics, y no todos los tipos de datos se pueden enviar secuencialmente y en tiempo real.

* Retraso en el envío de datos por lotes a conjuntos de datos de Platform

  Aunque es posible que algunos datos estén disponibles para generar informes antes, todos los [datos por lotes se incorporan a un conjunto de datos de Platform](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), que generalmente oscila entre 3 y 9 horas después del tiempo del evento de datos. Para que las alertas sean precisas, la ingesta de datos debe ser completa, con todos los datos por lotes disponibles en el conjunto de datos. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Por estos motivos, la ingesta de datos para los distintos tipos de datos de evento que se pueden introducir se completa solo después de algún retraso, normalmente en un intervalo de 3 a 9 horas después del tiempo de evento de datos. Para que las alertas sean precisas, los datos de evento de un intervalo de eventos determinado deben estar completos, lo que significa que el Adobe ya no recibe datos de evento para el intervalo de eventos especificado.

Para tener en cuenta este retraso en el tiempo de ingesta, las alertas tienen un retraso predeterminado de 9 horas antes de enviarse.

Puede ajustar el retraso predeterminado de 9 horas a cualquier valor entre 0 y 24 horas. Sin embargo, si se reduce el retraso por debajo de 9 horas, puede significar que está generando informes con datos incompletos, lo que da como resultado información de alerta inexacta.

Para obtener más información acerca de cómo ajustar la demora y los factores que debe tener en cuenta al hacerlo, vea <!--add link -->.

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->





