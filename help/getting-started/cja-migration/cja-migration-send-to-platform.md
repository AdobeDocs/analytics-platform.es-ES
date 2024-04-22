---
title: Envío de datos a Adobe Experience Platform al migrar a Customer Journey Analytics
description: Envío de datos a Adobe Experience Platform al migrar a Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 1%

---

# Paso 3: Envío de datos a Adobe Experience Platform al migrar a Customer Journey Analytics

+++La información de esta página forma parte de un proceso de migración más amplio. Expanda esta sección para ver dónde encaja esta información dentro del proceso de migración. </br></br>Debe completar todos los pasos de migración anteriores antes de continuar con la información de esta página.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de migración anteriores.

La información de esta página cubre el paso 3, como se indica en la tabla siguiente:

| Tarea de migración | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| **Paso 2: [Elija el método de migración.](/help/getting-started/cja-migration/cja-migration-method.md)** | Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| <span class="preview">**Paso 3: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">El proceso de envío de datos a Adobe Experience Platform difiere según el método de migración elegido en el paso 1.</span> |
| **Paso 4: [Planificar la asignación de datos al esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) se utilizan en Adobe Experience Platform para describir la estructura de los datos de una manera uniforme y reutilizable. Al definir los datos de forma coherente en todos los sistemas, resulta más fácil conservar el significado y, por lo tanto, obtener valor de los datos.<p>La mayoría de los métodos de migración requieren que cree un nuevo esquema XDM o que asigne el esquema de Adobe Analytics existente a XDM mediante la asignación de flujos de datos.</p> |
| **Paso 5: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 6: [Planificar la incorporación del usuario](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics. |
| **Paso 7: [Puerto del uso de API de informes](/help/getting-started/cja-migration/cja-migration-api.md)** | La API de informes de Customer Journey Analytics tiene el mismo formato, pero utiliza un punto de conexión diferente. Publique el uso de la API de informes desde la API de informes de Adobe Analytics a la API de informes de Customer Journey Analytics. |
| **Paso 8: [Reemplazar fuentes de datos y Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida cómo utilizará las opciones de exportación disponibles en Customer Journey Analytics para reemplazar las fuentes de datos y las funciones de Data Warehouse que utilizaba en Adobe Analytics. |
| **Paso 9: [Migrar proyectos y componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | El área Migración de componentes en Adobe Analytics le permite migrar proyectos y sus componentes asociados de Adobe Analytics a Customer Journey Analytics. |

{style="table-layout:auto"}

+++


Después de usted [elija el método de migración](#step-2-choose-your-customer-journey-analytics-migration-method) para que esto sea lo mejor para su organización, puede empezar a enviar datos a Adobe Experience Platform para que estén disponibles en Customer Journey Analytics.

A continuación, se muestra el proceso para enviar datos al Experience Platform para cada método de migración. Siga los vínculos de la tabla siguiente para obtener información más detallada.

| Método de migración | Proceso para enviar datos a Platform |
|---------|----------|
| Nueva implementación del SDK web | [Ingesta de datos mediante el SDK web de Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md) |
| Migre su implementación de Adobe Analytics para utilizar el SDK web | Si utiliza la extensión de etiqueta de Analytics: [Migración de la extensión de etiqueta de Adobe Analytics a la extensión de etiqueta del SDK web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)<p>O</p><p>Si utiliza el AppMeasurement: [Migración del AppMeasurement al SDK web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| Configure la implementación existente del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics | [Configuración de una secuencia de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream) in [Ingesta de datos mediante el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) |
| Conector de origen de Analytics | [Ingesta y uso de datos de Adobe Analytics tradicional](/help/data-ingestion/analytics.md) |

## A continuación, asigne datos al esquema XDM

Después de enviar datos a Experience Platform siguiendo los vínculos de la tabla anterior, es posible que tenga que hacer lo siguiente [asignación de datos al esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md), según el método de implementación elegido.

Los siguientes métodos de implementación requieren que asigne datos al esquema XDM:

* Migración de la extensión de etiqueta de Adobe Analytics a la extensión de etiqueta del SDK web

* Configure la implementación existente del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics

Alternativamente, si elige realizar una nueva implementación del SDK web, no se requiere una asignación porque ya ha [configuración de un nuevo esquema XDM](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) como parte de la nueva implementación de.

Si eligió utilizar el conector de origen de Analytics para la migración, no se requiere una asignación porque el conector de origen de Analytics utiliza el mismo esquema de Adobe Analytics en lugar del esquema XDM.
