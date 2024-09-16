---
description: El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.
title: Resumen de las alertas inteligentes
feature: Workspace Basics
role: User, Admin
source-git-commit: 640624ab017d8fc0e7b942c2f00c71cf255c4296
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 52%

---

# Resumen de las alertas inteligentes

>[!NOTE]
>
>Las alertas inteligentes están disponibles para todos los clientes. Sin embargo, para utilizar la detección de anomalías en las alertas inteligentes, debe tener Customer Journey Analytics Select, Prime o Ultimate.

Las alertas inteligentes (o simplemente &quot;alertas&quot;) de Customer Journey Analytics le permiten recibir notificaciones cuando se producen eventos anormales en los datos.

Puede definir alertas para que se activen en función de umbrales de anomalías, porcentajes modificados o puntos de datos específicos. Las alertas proporcionan controles granulares que se integran con [Detección de anomalías](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) y se activan cuando más los necesita.

Las alertas inteligentes le permiten:

* Generar alertas en función de anomalías (umbrales del 90 %, 95 %, 99 %, 99,75 % y 99,9 %; cambio de %; por encima/por debajo)
* Obtener una vista previa de la frecuencia con la que se activará una alerta
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados
* Crear alertas “apiladas” que capturan varias métricas en una sola alerta

El siguiente tutorial de vídeo proporciona información general básica sobre las alertas: [Alertas inteligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=es) (5:34)

## Explicación de cómo difieren las alertas en el Customer Journey Analytics de Adobe Analytics

El proceso de utilización de las Alertas inteligentes en Customer Journey Analytics es casi idéntico al de las Alertas inteligentes en Adobe Analytics. Sin embargo, hay diferencias importantes.

Para obtener más información, vea [Comparación de características de alertas inteligentes: Customer Journey Analytics y Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Retrospectiva de anomalías para alertas

Si una alerta utiliza la detección de anomalías, el periodo de prueba varía según la granularidad seleccionada para la alerta.

* Granularidad mensual: 15 meses + el mismo intervalo del año anterior
* Granularidad semanal: 15 semanas + el mismo intervalo del año anterior
* Granularidad diaria: 35 días + el mismo intervalo del año anterior
* Granularidad horaria: 336 horas

Para obtener más información, consulte [Técnicas estadísticas utilizadas en la detección de anomalías](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Creación de alertas

Para obtener información sobre cómo crear alertas en Customer Journey Analytics, consulte [Crear alertas](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>El uso de datos con fecha y hora para crear alertas puede hacer que se activen incorrectamente. Adobe recomienda utilizar datos sin marca de hora para las alertas inteligentes.

## Administración de alertas

Puede administrar las alertas existentes en el Administrador de alertas. Puede realizar varias tareas de administración en las alertas, como etiquetado, cambio de nombre, eliminación, etc.

Para obtener más información sobre cómo administrar las alertas existentes en Customer Journey Analytics, consulte [Administrar alertas](/help/components/c-intelligent-alerts/alert-manager.md).

