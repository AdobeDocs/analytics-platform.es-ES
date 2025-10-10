---
title: Utilice exclusivamente el conector de origen de Analytics para actualizar a Customer Journey Analytics
description: Obtenga más información sobre cómo crear el conector de origen de Analytics y los campos de asignación
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 94%

---

# Alternativa de actualización: uso exclusivo del conector de origen de Analytics para actualizar a Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Uso exclusivo del conector de origen de Analytics"
>abstract="(No recomendado) Puede utilizar el conector de origen de Analytics como la única ruta de implementación para Customer Journey Analytics. <br><br>Esta opción ahorra tiempo de implementación al enviar datos rápidamente a Customer Journey Analytics. Sin embargo, incluye varias deficiencias, como una mayor latencia y dificultades para salir de Adobe Analytics en el futuro."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Aunque no se recomienda, puede utilizar el conector de origen de Analytics como la única ruta de implementación para Customer Journey Analytics. Sin embargo, debido a las desventajas inherentes asociadas a este tipo de actualización, Adobe recomienda utilizar el conector de origen de Analytics junto con una nueva implementación del SDK web de Experience Platform. Para obtener más información sobre la ruta de actualización recomendada, consulte [Ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

## Ventajas y desventajas

Utilice la información de la tabla siguiente para comprender las ventajas y desventajas de utilizar el conector de origen exclusivamente al actualizar a Customer Journey Analytics.

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>Ruta de actualización menos lenta y menos exigente. <p>Los datos se migran a Customer Journey Analytics de forma rápida y sencilla.</p></li></ul> | <ul><li>**Los datos no se envían a Edge Network**: <p>Como resultado se obtienen las siguientes desventajas:</p><ul><li>Nivel máximo de [latencia](/help/technotes/guardrails.md#latencies) en los informes en todas las rutas de actualización; no optimizado para los casos de uso de personalización en tiempo real.</li><li>Los datos no se pueden compartir con otras aplicaciones de Adobe Experience Platform; están restringidos únicamente a Customer Journey Analytics</li><li>Depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Dificultad para pasarse al SDK web en el futuro**: con el tiempo, es probable que desee tener acceso a las ventajas que proporciona el SDK web de Experience Platform. Para poder empezar a utilizar el SDK web de Experience Platform, debe realizar una nueva implementación.</li><li>**Utiliza el grupo de campos de evento de experiencia de Analytics en el esquema**: este grupo de campos añade muchos eventos de Adobe Analytics que no son necesarios en el esquema de Customer Journey Analytics.  Esto puede dar lugar a un esquema más complejo y desordenado de lo que sería necesario para Customer Journey Analytics.</li><li>**Requiere licencias tanto para Adobe Analytics como para Customer Journey Analytics**: el uso del conector de origen de Analytics requiere pagar tanto por Adobe Analytics como por Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

## Pasos básicos

Si decide utilizar el conector de origen de Analytics como la única ruta de implementación para Customer Journey Analytics, siga los pasos de implementación que se describen en [Ingesta y uso de datos mediante conectores de origen](/help/data-ingestion/sources.md).

