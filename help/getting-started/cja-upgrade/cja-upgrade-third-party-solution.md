---
title: Actualización de una solución de análisis de terceros a Customer Journey Analytics
description: Obtenga información sobre la actualización de una solución de análisis de terceros a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 32%

---

# Actualización de una solución de análisis de terceros a Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Un producto distinto de Adobe Analytics"
>abstract="Una implementación que recopila datos para un producto distinto de Adobe Analytics, como Google Analytics. Al seleccionar esta opción, se desactivan varias opciones de la guía de actualización que no se aplican cuando actualiza a Customer Journey Analytics desde un producto distinto de Adobe Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

El proceso recomendado para actualizar desde una solución de análisis distinta de Adobe Analytics a Customer Journey Analytics es una nueva implementación de Experience Platform Web SDK, que es el método de recopilación de datos preferido para Customer Journey Analytics. Junto con Web SDK, Adobe también recomienda la ingesta de datos históricos de la solución de análisis de terceros en Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Utilice el siguiente proceso al pasar a Customer Journey Analytics desde una solución de análisis de terceros, como Google Analytics:

1. Siga los [pasos detallados para la actualización recomendada](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Estos pasos están destinados a organizaciones que actualizan desde Adobe Analytics. Al seguir estos pasos, debe comprender lo siguiente:

   * Debe crear una secuencia de datos.

   * No puede migrar proyectos y componentes desde una solución que no sea de Adobe Analytics.

   * Según la solución de análisis, podría haber un conector de origen disponible para la ingesta de datos históricos. Para obtener más información, consulte [Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics) en la [descripción general de los conectores de Source](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) en la documentación de Experience Platform.


Póngase en contacto con el representante del Adobe si necesita asesoramiento, ayuda o asistencia más específicos.

