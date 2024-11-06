---
title: Comprenda su implementación de Adobe Analytics y cómo afecta a su actualización a Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 21%

---

# Comprenda su implementación de Adobe Analytics y cómo afecta a su actualización a Customer Journey Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Existen varias formas de actualizar a Customer Journey Analytics, pero no todas las rutas de actualización están disponibles para cada tipo de implementación de Adobe Analytics. Sin embargo, la ruta de actualización recomendada está disponible independientemente de cómo se implemente Adobe Analytics en su organización.

Utilice la información siguiente para comprender mejor qué rutas de actualización están disponibles para su organización.

Póngase en contacto con el representante del Adobe si necesita asesoramiento, ayuda o asistencia más específicos.

| Implementación existente de Adobe Analytics | Descripción | Rutas de actualización disponibles |
|---------|----------|----------|
| AppMeasurement | Históricamente, el AppMeasurement para JavaScript ha sido un método común para implementar Adobe Analytics.<p>Para obtener más información acerca de este tipo de implementación, vea [Implementar Adobe Analytics con AppMeasurement para JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Nueva implementación del SDK web de Experience Platform</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| Extensión de Adobe Analytics (etiquetas) | <p>Las etiquetas en Adobe Experience Platform son una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.</p><p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con la extensión de Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Nueva implementación del SDK web de Experience Platform</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| SDK web (alloy.js) | El SDK web de Experience Platform es el método que recomienda actualmente Adobe para implementar Adobe Analytics. El Edge Network de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con el Edge Network de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Configuración de la implementación del SDK web de Adobe Analytics para enviar datos a Platform</li></ul> |
| Extensión de SDK web (etiquetas) | El SDK web de Experience Platform es el método que recomienda actualmente Adobe para implementar Adobe Analytics. El Edge Network de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada. <p>Para obtener más información sobre este tipo de implementación, consulte [Implementar Adobe Analytics con el Edge Network de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recomendado) Nueva implementación del SDK web de Experience Platform con el conector Source de Analytics</li><li>Configuración de la implementación del SDK web de Adobe Analytics para enviar datos a Platform</li></ul> |

{style="table-layout:auto"}

