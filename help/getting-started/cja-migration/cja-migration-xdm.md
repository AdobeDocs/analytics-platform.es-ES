---
title: Asignar datos al esquema XDM al migrar a un Customer Journey Analytics
description: Obtenga información sobre cómo asignar datos al esquema XDM al migrar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%

---

# Paso 4: Asignación de datos al esquema XDM al migrar a Customer Journey Analytics

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de migración más amplio. Asegúrese de que se han completado todos los pasos de migración anteriores.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de migración anteriores.

La información de esta página cubre el paso 4, como se indica en la tabla siguiente:

| Tarea de migración | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| **Paso 2: [Elija el método de migración.](/help/getting-started/cja-migration/cja-migration-method.md)** | Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| **Paso 3: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según el método de migración elegido en el paso 1. |
| <span class="preview">**Paso 4: [Asignación de datos al esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) se utilizan en Adobe Experience Platform para describir la estructura de los datos de una manera uniforme y reutilizable. Al definir los datos de forma coherente en todos los sistemas, resulta más fácil conservar el significado y, por lo tanto, obtener valor de los datos.<p>La mayoría de los métodos de migración requieren que cree un nuevo esquema XDM o que asigne el esquema de Adobe Analytics existente a XDM mediante la asignación de flujos de datos.</p></span> |
| **Paso 5: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 6: [Planificar la incorporación del usuario](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics. |
| **Paso 7: [Puerto del uso de API de informes](/help/getting-started/cja-migration/cja-migration-api.md)** | La API de informes de Customer Journey Analytics tiene el mismo formato, pero utiliza un punto de conexión diferente. Publique el uso de la API de informes desde la API de informes de Adobe Analytics a la API de informes de Customer Journey Analytics. |
| **Paso 8: [Reemplazar fuentes de datos y Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida cómo utilizará las opciones de exportación disponibles en Customer Journey Analytics para reemplazar las fuentes de datos y las funciones de Data Warehouse que utilizaba en Adobe Analytics. |
| **Paso 9: [Migrar proyectos y componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | El área Migración de componentes en Adobe Analytics le permite migrar proyectos y sus componentes asociados de Adobe Analytics a Customer Journey Analytics. |

{style="table-layout:auto"}

+++

La siguiente tabla muestra los métodos de implementación que requieren que asigne datos al esquema XDM:


| Método de migración | ¿Se requiere asignación XDM? | Más información |
|---------|----------|---------|
| **Nueva implementación del SDK web**<p>Los pasos básicos son:</p><ol><li>Creación de un esquema XDM para su organización</li><li>Implementación del SDK web</li><li>Envío de datos a Platform</li></ol> | No | No se requiere una asignación porque ya [configuración de un nuevo esquema XDM](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) como parte de la nueva implementación de. |
| **Migre su implementación de Adobe Analytics para utilizar el SDK web**<p>Los pasos básicos son:</p><ol><li>Mueva la implementación de Adobe Analytics existente al SDK web y compruebe que todo funciona allí.</li><li>Cree un esquema XDM para su organización a medida que tenga tiempo.</li><li>Utilice la asignación de flujo de datos para asignar todos los campos del objeto de datos al esquema XDM.</li><li>Envío de datos a Platform</li></ol> | Sí | Trabaje con su equipo de datos para identificar el diseño de esquema ideal de su organización para Customer Journey Analytics y, a continuación, determinar cómo asignará eVars y Props a XDM.</br>[Utilice la preparación de datos para asignar todos los campos del objeto de datos al esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Configure la implementación existente del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics**<p>Los pasos básicos son:</p><ol><li>Comience a enviar datos al Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Opcional) Cree un esquema XDM para su organización a medida que tenga tiempo.</li><li>Utilice la asignación de flujo de datos para asignar todos los campos del objeto de datos al esquema XDM.</li></ol> | Sí | Trabaje con su equipo de datos para identificar el diseño de esquema ideal de su organización para Customer Journey Analytics y, a continuación, determinar cómo asignará eVars y Props a XDM.</br>[Utilice la preparación de datos para asignar todos los campos del objeto de datos al esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Conector de origen de Analytics**</br> Si la implementación de Adobe Analytics es AppMeasurement para la extensión de Analytics, puede empezar a enviar datos a una vista de datos en Customer Journey Analytics.<p>Esta es la forma más sencilla de obtener datos para Customer Journey Analytics, pero es el método menos viable a largo plazo.</p> | No | No se requiere una asignación porque el conector de origen de Analytics utiliza el esquema de Adobe Analytics existente en lugar del esquema XDM. |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## A continuación, conserve los datos históricos

A continuación, elija el método que desea utilizar para [conservar datos históricos de Adobe Analytics](/help/getting-started/cja-migration/cja-migration-historical-data.md).
