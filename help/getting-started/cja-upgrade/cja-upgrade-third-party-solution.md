---
title: Actualización de una solución de análisis de terceros a Customer Journey Analytics
description: Aprenda a actualizar de una solución de análisis de terceros a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
autotag-review: '2026-05-19T08:20:34.368Z'
TQID: 'https://experienceleague.adobe.com/fwYoa9oeIs2tujyDEWUj-GaAgpZQNBwup-YsHIe-TdU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 293
ht-degree: 89%

---

# Actualización de una solución de análisis de terceros a Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Un producto distinto de Adobe Analytics"
>abstract="Una implementación que recopila datos para un producto distinto de Adobe Analytics, como Google Analytics. Al seleccionar esta opción, se desactivan varias opciones de la guía de actualización que no se aplican cuando actualiza a Customer Journey Analytics desde un producto distinto de Adobe Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

El proceso recomendado para actualizar de una solución de análisis diferente de Adobe Analytics a Customer Journey Analytics es una nueva implementación del SDK web de Experience Platform, que es el método de recopilación de datos preferido para Customer Journey Analytics. Junto con Web SDK, Adobe también recomienda la ingesta de datos históricos de la solución de análisis de terceros en Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Utilice el siguiente proceso al pasar a Customer Journey Analytics desde una solución de análisis de terceros, como Google Analytics:

1. Siga los [pasos detallados para la actualización recomendada](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Estos pasos están destinados a organizaciones que actualizan desde Adobe Analytics. Al seguir estos pasos, debe comprenda lo siguiente:

   * Debe crear una secuencia de datos.

   * No puede migrar proyectos y componentes desde una solución que no sea de Adobe Analytics.

   * Según la solución de análisis, podría haber un conector de origen disponible para la ingesta de datos históricos. Para obtener más información, consulte [Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/home#analytics) en la [descripción general de los conectores de Source](https://experienceleague.adobe.com/es/docs/experience-platform/sources/home) en la documentación de Experience Platform.


Póngase en contacto con el representante de Adobe si necesita asesoramiento, ayuda o asistencia más específicos.

Si viene específicamente de Google Analytics 4, consulte [Transición de Google Analytics 4 a Customer Journey Analytics](../ga-to-cja/home.md) para obtener instrucciones centradas en los analistas sobre equivalentes de informes, diferencias de modelos de datos y comparaciones de métricas.

