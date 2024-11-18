---
title: Comprenda su implementación de Adobe Analytics y cómo afecta a su actualización a Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 19%

---

# Comprenda su implementación de Adobe Analytics y cómo afecta a su actualización a Customer Journey Analytics

>[!NOTE]
> 
>Use la información de esta página para responder preguntas en la [lista de comprobación de actualización de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Adobe Analytics se puede implementar de varias formas. Al actualizar a Customer Journey Analytics, no todas las rutas de actualización están disponibles para todas las implementaciones de Adobe Analytics. Sin embargo, la ruta de actualización recomendada está disponible independientemente de cómo se implemente Adobe Analytics en su organización.

Utilice la información siguiente para obtener más información sobre la implementación actual de Adobe Analytics y las rutas de actualización disponibles para su organización.

Póngase en contacto con el representante del Adobe si necesita asesoramiento, ayuda o asistencia más específicos.

| Implementación existente de Adobe Analytics | Descripción | Rutas de actualización disponibles |
|---------|----------|----------|
| AppMeasurement | Históricamente, el AppMeasurement para JavaScript ha sido un método común para implementar Adobe Analytics.<p>Para obtener más información acerca de este tipo de implementación, vea [Implementar Adobe Analytics con AppMeasurement para JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Nueva implementación del SDK web de Experience Platform</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| Extensión de Adobe Analytics (etiquetas) | <p>Las etiquetas en Adobe Experience Platform son una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.</p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con la extensión de Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Nueva implementación del SDK web de Experience Platform</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| SDK web de Experience Platform (alloy.js) | El SDK web de Experience Platform es el método que recomienda actualmente Adobe para implementar Adobe Analytics. El Edge Network de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con el Edge Network de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Configuración de la implementación del SDK web de Adobe Analytics para enviar datos a Platform</li></ul> |
| Extensión de SDK web de Experience Platform (etiquetas) | El SDK web de Experience Platform es el método que recomienda actualmente Adobe para implementar Adobe Analytics para datos web. El Edge Network de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Configuración de la implementación del SDK web de Adobe Analytics para enviar datos a Platform</li></ul> |
| Experience Platform Mobile SDK | El SDK de Experience Platform Mobile es el método que recomienda actualmente Adobe para implementar Adobe Analytics para datos móviles. El Edge Network de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada.<p>El SDK de Adobe Experience Platform Mobile ayuda a impulsar las soluciones y los servicios de Experience Cloud de Adobe en sus aplicaciones móviles. </p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics mediante el SDK para móviles de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Configuración de la implementación del SDK web de Adobe Analytics para enviar datos a Platform</li></ul> |

{style="table-layout:auto"}
