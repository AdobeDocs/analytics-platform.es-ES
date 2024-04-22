---
title: Conservar datos históricos al migrar a un Customer Journey Analytics
description: Obtenga información sobre cómo conservar datos históricos al migrar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Paso 5: Conservar los datos históricos al migrar a un Customer Journey Analytics

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de migración más amplio. Asegúrese de que se han completado todos los pasos de migración anteriores.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de migración anteriores.

La información de esta página cubre el paso 5, como se indica en la tabla siguiente:

| Tarea de migración | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| **Paso 2: [Elija el método de migración.](/help/getting-started/cja-migration/cja-migration-method.md)** | Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| **Paso 3: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según el método de migración elegido en el paso 1. |
| **Paso 4: [Asignación de datos al esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) se utilizan en Adobe Experience Platform para describir la estructura de los datos de una manera uniforme y reutilizable. Al definir los datos de forma coherente en todos los sistemas, resulta más fácil conservar el significado y, por lo tanto, obtener valor de los datos.<p>La mayoría de los métodos de migración requieren que cree un nuevo esquema XDM o que asigne el esquema de Adobe Analytics existente a XDM mediante la asignación de flujos de datos.</p> |
| <span class="preview">**Paso 5: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)**</span> | <span class="preview">La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo.</span> |
| **Paso 6: [Planificar la incorporación del usuario](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics. |
| **Paso 7: [Puerto del uso de API de informes](/help/getting-started/cja-migration/cja-migration-api.md)** | La API de informes de Customer Journey Analytics tiene el mismo formato, pero utiliza un punto de conexión diferente. Publique el uso de la API de informes desde la API de informes de Adobe Analytics a la API de informes de Customer Journey Analytics. |
| **Paso 8: [Reemplazar fuentes de datos y Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida cómo utilizará las opciones de exportación disponibles en Customer Journey Analytics para reemplazar las fuentes de datos y las funciones de Data Warehouse que utilizaba en Adobe Analytics. |
| **Paso 9: [Migrar proyectos y componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | El área Migración de componentes en Adobe Analytics le permite migrar proyectos y sus componentes asociados de Adobe Analytics a Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Elija una de las siguientes opciones para conservar los datos históricos al pasar de Adobe Analytics a Customer Journey Analytics:

## Uso del conector de origen de Analytics

Puede Utilizar el [Conector de origen de Analytics](/help/data-ingestion/analytics.md) para conservar los datos históricos. Independientemente del método de migración que elija (aunque migre mediante el SDK web), puede utilizar el conector de origen de Analytics para conservar los datos históricos de su entorno de Adobe Analytics.

Puede utilizar el conector de origen de Analytics para conservar los datos históricos de las siguientes maneras:

* Coloque los datos históricos en su propia ubicación dedicada, independiente de los datos actuales.

* Asignar datos históricos de una manera que le permita vincularlos a los nuevos datos. <!-- Possible? Explain -->

## Mantener la implementación de Adobe Analytics existente

Puede mantener su implementación de Adobe Analytics existente junto con la nueva implementación de Customer Journey Analytics para un periodo de tiempo específico (por ejemplo, 1 año). Al elegir esta opción, debe planificar la eliminación de la implementación de Adobe Analytics después de tener suficientes datos en Customer Journey Analytics.

Póngase en contacto con el representante de su cuenta de Adobe para determinar los precios de esta opción.

## A continuación, planifique la incorporación del usuario

[Planificar la incorporación del usuario al Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-onboarding.md). Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics.
