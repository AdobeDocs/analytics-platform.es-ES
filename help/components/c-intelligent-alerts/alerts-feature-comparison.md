---
description: Descubra las diferencias entre las alertas en Customer Journey Analytics y Adobe Analytics
title: Comparación de funciones de alertas entre Customer Journey Analytics y Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 23%

---

# Comparación de características de alertas

El proceso de utilización de alertas en Customer Journey Analytics es casi idéntico al de las alertas en Adobe Analytics. Sin embargo, hay diferencias importantes. Las siguientes secciones describen las diferencias clave.

## Las alertas horarias no están disponibles

Las alertas por hora están **no** disponibles en Customer Journey Analytics, mientras que las alertas por hora están disponibles en Adobe Analytics. En Customer Journey Analytics, las alertas se pueden configurar para alertas diarias, semanales o mensuales.

Puede introducir datos en Adobe Experience Platform de varias formas. Como resultado, la integridad y disponibilidad de los datos no se pueden lograr de forma fiable dentro de las restricciones de una hora.  La flexibilidad de la ingesta de datos implica que las alertas horarias no son prácticas debido al alto potencial de datos incompletos. Para obtener más información, consulte [Los tiempos de ingesta de datos varían](#data-ingestion-times-vary-in-customer-journey-analytics).

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

## Crear una alerta a partir de Analysis Workspace no disponible

En Analysis Workspace en Adobe Analytics, puede crear alertas a partir de Analysis Workspace de cualquiera de las formas que se describen a continuación. En Customer Journey Analytics, las opciones para crear alertas desde Analysis Workspace aún no están disponibles. En su lugar, acceda al Generador de alertas, tal como se describe en [Crear alertas](/help/components/c-intelligent-alerts/alert-builder.md).

En Adobe Analytics, están disponibles las siguientes opciones:

* Seleccione uno o más elementos de línea en una tabla de forma libre, luego haga clic con el botón derecho y seleccione **[!UICONTROL Crear alerta a partir de la selección]**.

  De este modo, se rellena instantáneamente el Generador de alertas para crear una alerta con las métricas y los segmentos correctos.

* Abra un proyecto en Analysis Workspace y seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Crear alerta]**.

* Abra un proyecto en Analysis Workspace y, a continuación, utilice el acceso directo siguiente: **[!UICONTROL *ctrl *]**+**[!UICONTROL * shift *]** + **[!UICONTROL *a *]**(Windows) o&#x200B;**[!UICONTROL * cmd *]** + **[!UICONTROL *shift *]**+**[!UICONTROL * a *]** (macOS).
