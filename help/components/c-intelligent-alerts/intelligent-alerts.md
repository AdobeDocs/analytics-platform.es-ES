---
description: Entienda cómo utilizar las alertas, que permiten un control granular sobre las notificaciones y la integración con la detección de anomalías.
title: Información general sobre alertas
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 58%

---

# Información general sobre alertas

Las alertas de Customer Journey Analytics permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos.

Según el paquete de Customer Journey Analytics, también puede utilizar alertas para activarlas en función de los umbrales de anomalías. Estas alertas (también conocidas como *Alertas inteligentes*) proporcionan controles granulares que se integran con la [Detección de anomalías](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) y se activan cuando más las necesita.

* Vista previa de la frecuencia con la que déclencheur una alerta.
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados.
* Crear *alertas apiladas* que capturan varias métricas en una sola alerta.
* Generar alertas basadas en:
   * Anomalías en métricas que existen, que están por encima o por debajo de los valores de umbral esperados.

     [Detección de anomalías](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) crea un valor esperado más un límite superior e inferior usando datos históricos. Si el valor real de la métrica va por encima o por debajo del límite inferior definido como valor de umbral, ese evento se considera una anomalía en el nivel de confianza de umbral y no almacena en déclencheur la alerta. Un umbral más alto (por ejemplo, 99 % o 99,9 %) implica una banda más ancha, lo que resulta en menos alertas causadas por anomalías más extremas. Un umbral más bajo (por ejemplo, 90 %) implica una banda más estrecha, lo que da como resultado más alertas causadas por anomalías menos extremas.
   * Cambios en las métricas según un porcentaje específico.
   * Métricas que están por encima, por debajo o iguales a un valor específico. (disponible solo para clientes de Adobe Analytics con un paquete Select, Prime o Ultimate)

Este [tutorial en vídeo](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/data-science/intelligent-alerts) proporciona información general básica sobre las alertas.



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
