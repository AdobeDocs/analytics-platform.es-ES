---
title: Actualización de una solución de análisis de terceros a Customer Journey Analytics
description: Obtenga información sobre la actualización de una solución de análisis de terceros a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 87df2fb92f238ce051ac5f6cc90e218737279471
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 20%

---

# Actualización de una solución de análisis de terceros a Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Un producto de análisis de terceros"
>abstract="Una implementación que recopila datos para un producto de análisis de terceros, como Google Analytics. Al seleccionar esta opción, se desactivan varias opciones del cuestionario que no se aplican cuando se actualiza Customer Journey Analytics desde un producto de análisis de terceros."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use la información de esta página para responder preguntas en la [lista de comprobación de actualización de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

El proceso recomendado para actualizar desde una solución de análisis de terceros a Customer Journey Analytics es una nueva implementación de Experience Platform Web SDK, que es el método de recopilación de datos preferido para Customer Journey Analytics. Junto con Web SDK, Adobe también recomienda la ingesta de datos históricos de la solución de análisis de terceros en Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Utilice el siguiente proceso al pasar a Customer Journey Analytics desde una solución de análisis de terceros, como Google Analytics:

1. ...


Póngase en contacto con el representante del Adobe si necesita asesoramiento, ayuda o asistencia más específicos.

| Solución de análisis existente | Descripción | Rutas de actualización disponibles |
|---------|----------|----------|
| AppMeasurement | Históricamente, AppMeasurement para JavaScript ha sido un método común para implementar Adobe Analytics.<p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con AppMeasurement para JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migración de Adobe Analytics al SDK web</li><li>[Conector de Source de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Extensión de Adobe Analytics (etiquetas) | <p>Las etiquetas en Adobe Experience Platform son una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.</p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con la extensión de Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migración de Adobe Analytics al SDK web</li><li>[Conector de Source de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics. Adobe Experience Platform Edge Network le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configuración de la implementación de Adobe Analytics Web SDK para enviar datos a Platform</li></ul> |
| Extensión de Experience Platform Web SDK (etiquetas) | Experience Platform Web SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics para los datos web. Adobe Experience Platform Edge Network le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>Para obtener más información acerca de este tipo de implementación, vea [Implementar Adobe Analytics mediante Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Configuración de la implementación de Adobe Analytics Web SDK para enviar datos a Platform</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics para datos móviles. Adobe Experience Platform Edge Network le permite enviar datos destinados a varios productos a una ubicación centralizada.<p>Adobe Experience Platform Mobile SDK ayuda a impulsar las soluciones y los servicios Experience Cloud de Adobe en sus aplicaciones móviles. </p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configuración de la implementación de Adobe Analytics Web SDK para enviar datos a Platform</li></ul> |
| API de inserción de datos en lotes | La API de inserción masiva de datos (BDIA) es una función de Adobe Analytics que permite cargar datos de llamadas al servidor en lotes de archivos en lugar de utilizar bibliotecas del lado del cliente como AppMeasurement. </p><p>Para obtener más información sobre este tipo de implementación, consulte [API de inserción de datos en lotes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[API de servidor de Adobe Experience Platform Edge Network y Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
