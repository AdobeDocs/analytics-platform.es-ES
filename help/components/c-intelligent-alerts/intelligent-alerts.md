---
description: Entienda cómo utilizar las alertas, que permiten un control granular sobre las notificaciones y la integración con la detección de anomalías.
title: Información general sobre alertas
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 96%

---

# Información general sobre alertas

Las alertas de Customer Journey Analytics permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos.

Según el paquete de Customer Journey Analytics, también puede utilizar alertas para activarlas en función de los umbrales de anomalías. Estas alertas (también conocidas como “Alertas inteligentes”) proporcionan controles granulares que se integran con [Detección de anomalías](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) y se activan cuando más los necesita.

Las alertas le permiten:

* Obtener una vista previa de la frecuencia con la que se activará una alerta
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados
* Crear alertas “apiladas” que capturan varias métricas en una sola alerta
* Generar alertas en función de anomalías (umbrales del 90 %, 95 %, 99 %, 99,75 % y 99,9 %; cambio de %; por encima/por debajo) (disponible solo para clientes de Customer Journey Analytics con un paquete Select, Prime o Ultimate)

El siguiente tutorial de vídeo proporciona información general básica sobre las alertas: [Alertas](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=es) (5:34)

## Explicación de cómo difieren las alertas

El proceso de utilización de alertas en Customer Journey Analytics es casi idéntico al de las alertas en Adobe Analytics. Sin embargo, existen diferencias importantes.

Para obtener más información, consulte [Comparación de características de alertas: Customer Journey Analytics y Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Retrospectiva de anomalías para alertas

>[!NOTE]
>
>El uso de alertas con detección de anomalías (también conocido como _alertas inteligentes_) solo está disponible para organizaciones con un paquete de Customer Journey Analytics Select, Prime o Ultimate.

Si una alerta utiliza la detección de anomalías, el periodo de prueba varía según la granularidad seleccionada para la alerta.

* Granularidad mensual: 15 meses + el mismo intervalo del año anterior
* Granularidad semanal: 15 semanas + el mismo intervalo del año anterior
* Granularidad diaria: 35 días + el mismo intervalo del año anterior
* Granularidad horaria: 336 horas

Consulte [Técnicas estadísticas utilizadas en la detección de anomalías](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) para obtener más información.

## Creación de alertas

Para obtener información sobre cómo crear alertas en Customer Journey Analytics, consulte [Crear alertas](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>El uso de datos con fecha y hora para crear alertas puede hacer que se activen incorrectamente. Adobe recomienda utilizar datos sin marca de hora para las alertas.

## Administración de alertas

Puede administrar las alertas existentes en el Administrador de alertas. Puede realizar varias tareas de administración de las alertas, como etiquetado, cambio de nombre, eliminación, etc.

Para obtener más información sobre cómo administrar las alertas existentes en Customer Journey Analytics, consulte [Administrar alertas](/help/components/c-intelligent-alerts/alert-manager.md).
