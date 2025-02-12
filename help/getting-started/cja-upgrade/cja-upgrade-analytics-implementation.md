---
title: Comprenda su implementación de Adobe Analytics y cómo afecta a su actualización a Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 12%

---

# Comprenda su implementación de Adobe Analytics y cómo afecta a su actualización a Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (archivo JS manual)"
>abstract="Implementación de JavaScript que carga AppMeasurement.js en una página y envía datos a Adobe mediante el objeto s (por ejemplo, s.eVar1)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Extensión de Adobe Analytics (etiquetas)"
>abstract="Implementación de etiquetas que carga la recopilación de datos de Adobe Experience Platform (anteriormente conocida como Launch). La etiqueta tiene instalada la extensión de Adobe Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="SDK web (alloy.js)"
>abstract="Implementación de JavaScript que carga la biblioteca SDK web (alloy.js) en una página y envía datos a Adobe mediante una carga útil JSON."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Extensión de Web SDK (etiquetas)"
>abstract="Implementación de etiquetas que carga la recopilación de datos de Adobe Experience Platform (anteriormente conocida como Launch). La etiqueta tiene instalada la extensión Web SDK."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="API de inserción de datos"
>abstract="Implementación que utiliza la API de inserción de datos o la API de inserción de datos en lote."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="SDK móvil"
>abstract="Implementación que utiliza Adobe Experience Platform Mobile SDK."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Implementación desconocida"
>abstract="Si no es usted la persona que administra la implementación, puede seleccionar temporalmente esta opción."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use la información de esta página para responder preguntas en la [lista de comprobación de actualización de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Adobe Analytics se puede implementar de varias formas. Al actualizar a Customer Journey Analytics, no todas las rutas de actualización están disponibles para todas las implementaciones de Adobe Analytics. Sin embargo, la ruta de actualización recomendada está disponible independientemente de cómo se implemente Adobe Analytics en su organización.

Utilice la información siguiente para obtener más información sobre la implementación actual de Adobe Analytics y las rutas de actualización disponibles para su organización.

Póngase en contacto con el representante del Adobe si necesita asesoramiento, ayuda o asistencia más específicos.

| Implementación existente de Adobe Analytics | Descripción | Rutas de actualización disponibles |
|---------|----------|----------|
| AppMeasurement | Históricamente, AppMeasurement para JavaScript ha sido un método común para implementar Adobe Analytics.<p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con AppMeasurement para JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migración de Adobe Analytics al SDK web</li><li>[Conector de Source de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Extensión de Adobe Analytics (etiquetas) | <p>Las etiquetas en Adobe Experience Platform son una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.</p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con la extensión de Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migración de Adobe Analytics al SDK web</li><li>[Conector de Source de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics. Adobe Experience Platform Edge Network le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configuración de la implementación de Adobe Analytics Web SDK para enviar datos a Platform</li></ul> |
| Extensión de Experience Platform Web SDK (etiquetas) | Experience Platform Web SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics para los datos web. Adobe Experience Platform Edge Network le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>Para obtener más información acerca de este tipo de implementación, vea [Implementar Adobe Analytics mediante Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Configuración de la implementación de Adobe Analytics Web SDK para enviar datos a Platform</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics para datos móviles. Adobe Experience Platform Edge Network le permite enviar datos destinados a varios productos a una ubicación centralizada.<p>Adobe Experience Platform Mobile SDK ayuda a impulsar las soluciones y los servicios Experience Cloud de Adobe en sus aplicaciones móviles. </p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configuración de la implementación de Adobe Analytics Web SDK para enviar datos a Platform</li></ul> |
| API de inserción de datos en lotes | La API de inserción masiva de datos (BDIA) es una función de Adobe Analytics que permite cargar datos de llamadas al servidor en lotes de archivos en lugar de utilizar bibliotecas del lado del cliente como AppMeasurement. </p><p>Para obtener más información sobre este tipo de implementación, consulte [API de inserción de datos en lotes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de Source de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación de Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[API de servidor de Adobe Experience Platform Edge Network y Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
