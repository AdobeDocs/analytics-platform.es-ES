---
title: Utilice el conector de origen de Analytics exclusivamente para actualizar a Customer Journey Analytics
description: Obtenga información sobre cómo crear el conector de origen de Analytics y asignar campos
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 701e3d3ce535318e3d3debcdcd591615ea9ca4a1
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 24%

---

# Utilice el conector de origen de Analytics exclusivamente para actualizar a Customer Journey Analytics

>[!NOTE]
> 
>Use la información de esta página para responder preguntas en la [lista de comprobación de actualización de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Aunque no se recomienda, puede utilizar el conector de origen de Analytics como única ruta de implementación para Customer Journey Analytics. Sin embargo, debido a las desventajas inherentes asociadas con este tipo de actualización, Adobe recomienda utilizar el conector de origen de Analytics junto con una nueva implementación de Experience Platform Web SDK. Para obtener más información sobre esta ruta de actualización recomendada, consulte [Ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Utilice la información de la tabla siguiente para comprender las ventajas y desventajas de utilizar el conector de origen exclusivamente.

Si decide usar el conector de origen de Analytics como la única ruta de implementación para Customer Journey Analytics, siga los pasos de implementación descritos en [Ingesta y uso de datos mediante conectores de origen](/help/data-ingestion/sources.md).

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>Ruta de actualización menos laboriosa y exigente. <p>Los datos se migran al Customer Journey Analytics de forma rápida y sencilla.</p></li></ul> | <ul><li>**Los datos no se envían a Edge Network**: <p>Como resultado se obtienen las siguientes desventajas:</p><ul><li>Nivel máximo de [latencia](/help/technotes/guardrails.md#latencies) en los informes en todas las rutas de actualización; no optimizado para casos de uso de personalización en tiempo real.</li><li>Los datos no se pueden compartir con otras aplicaciones de Adobe Experience Platform; están restringidos únicamente a Customer Journey Analytics</li><li>Depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Dificultad para pasar a Web SDK en el futuro**: En algún momento, es probable que desee tener acceso a las ventajas que proporciona Web SDK de Experience Platform. Para empezar a utilizar Experience Platform Web SDK, debe realizar una nueva implementación.</li><li>**Utiliza el grupo de campos de evento de experiencia de Analytics en el esquema**: este grupo de campos añade muchos eventos de Adobe Analytics que no son necesarios en el esquema de Customer Journey Analytics.  Esto puede dar lugar a un esquema más complejo y desordenado de lo que sería necesario para Customer Journey Analytics.</li><li>**Requiere licencias tanto para Adobe Analytics como para Customer Journey Analytics**: El uso del conector de origen de Analytics requiere que pague tanto por Adobe Analytics como por Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}
