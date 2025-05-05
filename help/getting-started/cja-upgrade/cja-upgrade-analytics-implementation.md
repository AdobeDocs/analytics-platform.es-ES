---
title: Conozca su implementación de Adobe Analytics y cómo afecta a la actualización a Customer Journey Analytics
description: Más información sobre la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 81%

---

# Conozca su implementación de Adobe Analytics y cómo afecta a la actualización a Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (archivo JS manual)"
>abstract="Una implementación de JavaScript que carga AppMeasurement.js en una página y envía datos a Adobe mediante el objeto s (por ejemplo, s.eVar 1)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Extensión de Adobe Analytics (etiquetas)"
>abstract="Una implementación de etiquetas que carga la recopilación de datos de Adobe Experience Platform (anteriormente conocida como Launch). La etiqueta tiene instalada la extensión de Adobe Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="SDK web (alloy.js)"
>abstract="Una implementación de JavaScript que carga la biblioteca del SDK web (alloy.js) en una página y envía datos a Adobe mediante una carga útil JSON."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Extensión del SDK web (etiquetas)"
>abstract="Una implementación de etiquetas que carga la recopilación de datos de Adobe Experience Platform (anteriormente conocida como Launch). La etiqueta tiene instalada la extensión del SDK web."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="API de inserción de datos"
>abstract="Una implementación que utiliza la API de inserción de datos o la API de inserción de datos en lote."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="SDK móvil"
>abstract="Una implementación que utiliza el SDK móvil de Adobe Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-third-party"
>title="AppMeasurement con una herramienta de administración de etiquetas de terceros"
>abstract="Implementación que utiliza una herramienta de administración de etiquetas de terceros."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Implementación desconocida"
>abstract="Si no es usted la persona que administra la implementación, puede seleccionar temporalmente esta opción."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="Determine el tipo de implementación existente"
>abstract="Trabaje internamente dentro de su organización para determinar qué tipo de implementación utiliza actualmente para enviar datos a Adobe Analytics. A medida que actualice a Customer Journey Analytics, asóciese con la persona o el equipo que conozca esta información.<br><br>Después de determinar el tipo de implementación que utiliza su organización, modifique la respuesta en la guía de actualización de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics se puede implementar de varias formas. Al actualizar a Customer Journey Analytics, no todas las rutas de actualización están disponibles para todas las implementaciones de Adobe Analytics. Sin embargo, la ruta de actualización recomendada está disponible independientemente de cómo se implemente Adobe Analytics en su organización.

Utilice la información siguiente para obtener más información sobre la implementación actual de Adobe Analytics y las rutas de actualización disponibles para su organización.

Póngase en contacto con el representante de Adobe si necesita asesoramiento, ayuda o asistencia más específicos.

| Implementación existente de Adobe Analytics | Descripción | Rutas de actualización disponibles |
|---------|----------|----------|
| AppMeasurement | Históricamente, AppMeasurement para JavaScript ha sido un método común para implementar Adobe Analytics. <p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con AppMeasurement para JavaScript](https://experienceleague.adobe.com/es/docs/analytics/implementation/js/overview?lang=es).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de origen de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación del SDK web de Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrar Adobe Analytics a Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Extensión de Adobe Analytics (etiquetas) | <p>Las etiquetas en Adobe Experience Platform son una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.</p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con la extensión de Analytics](https://experienceleague.adobe.com/es/docs/analytics/implementation/launch/overview?lang=es).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de origen de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación del SDK web de Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrar Adobe Analytics a Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics. La red Edge de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada.  <p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/overview?lang=es).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de origen de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación del SDK web de Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Configure la implementación de Adobe Analytics Web SDK para enviar datos a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Extensión de SDK web de Adobe Experience Platform (etiquetas) | Experience Platform Web SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics para los datos web. La red Edge de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada.  <p>Para obtener más información acerca de este tipo de implementación, vea [Implementar Adobe Analytics mediante Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/web-sdk/overview?lang=es)</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de origen de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación del SDK web de Experience Platform](/help/data-ingestion/aepwebsdk.md)</li><li>[Configure la implementación de Adobe Analytics Web SDK para enviar datos a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK es el método que Adobe recomienda actualmente para implementar Adobe Analytics para datos móviles. La red Edge de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>El SDK móvil de Adobe Experience Platform ayuda a impulsar las soluciones y los servicios Experience Cloud de Adobe en sus aplicaciones móviles.  </p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/mobile-sdk/overview?lang=es)</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de origen de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación del SDK web de Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Configure la implementación de Adobe Analytics Web SDK para enviar datos a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| API de inserción de datos en lotes | La API de inserción masiva de datos (BDIA) es una función de Adobe Analytics que permite cargar datos de llamadas al servidor en lotes de archivos en lugar de usar bibliotecas del lado del cliente como AppMeasurement.  </p><p>Para obtener más información sobre este tipo de implementación, consulte [API de inserción de datos en lotes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recomendado) Nueva implementación de Experience Platform Web SDK para la recopilación continua de datos; el conector de origen de Analytics para los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nueva implementación del SDK web de Experience Platform](/help/data-ingestion/aepwebsdk.md)</li><li>[API del servidor de red Adobe Experience Platform Edge](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


