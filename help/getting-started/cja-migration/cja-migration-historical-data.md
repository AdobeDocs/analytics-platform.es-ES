---
title: Conservar datos históricos al migrar a un Customer Journey Analytics
description: Obtenga información sobre cómo conservar datos históricos al migrar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 2d35e49ca9afe37ed53d7c5da5aafd31dd2da632
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Paso 4: Conservar los datos históricos al migrar

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de migración más amplio. Asegúrese de que se han completado todos los pasos de migración anteriores.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de migración anteriores.

La información de esta página abarca el paso 4 del **migración**, como se indica en la tabla siguiente:

| Tarea de migración | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| **Paso 2: [Elija la ruta de migración](/help/getting-started/cja-migration/cja-migration-path.md)** | Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| **Paso 3: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según la ruta de migración elegida en el paso 2. |
| <span class="preview">**Paso 4: Conservar los datos históricos**</span> | <span class="preview">La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo.</span> |
| **Paso 5: [Realizar tareas de implementación adicionales](/help/getting-started/cja-getting-started.md)** | En este punto del proceso de migración, debe realizar varias tareas antes de que el entorno del Customer Journey Analytics esté listo para su uso.<p>Estas tareas adicionales se aplican a las migraciones desde Adobe Analytics, así como a las implementaciones de nuevos Customer Journey Analytics.</p><p>Estas tareas incluyen:</p><ul><li>Introducción de otros datos en Experience Platform</li><li>Creación de conexiones entre conjuntos de datos de Platform y el Customer Journey Analytics</li><li>Creación de vistas de datos</li><li>Transferencia del uso de API de informes</li><li>Contabilidad de fuentes de datos y Data Warehouse</li><li>Migración de proyectos y componentes</li><li>Planificación de la incorporación del usuario</li></ul> <p>Para obtener más información, consulte [Introducción al Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Elija una de las siguientes opciones para conservar los datos históricos al pasar de Adobe Analytics a Customer Journey Analytics:

>[!IMPORTANT]
>
>Al elegir cómo conservar los datos históricos, póngase en contacto con el representante de su cuenta de Adobe para determinar los precios.

## Uso del conector de origen de Analytics

Puede usar el complemento [Conector de origen de Analytics](/help/data-ingestion/analytics.md) para conservar los datos históricos. Independientemente de la ruta de migración que elija (aunque migre mediante el SDK web), puede utilizar el conector de origen de Analytics para conservar los datos históricos de su entorno de Adobe Analytics.

Puede utilizar el conector de origen de Analytics para conservar los datos históricos mediante la introducción de estos en su propia ubicación dedicada, independiente de los datos actuales.

El conector de origen de Analytics debe funcionar durante todo el tiempo que necesite acceso a los datos históricos.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Mantener la implementación de Adobe Analytics existente

Puede mantener su implementación de Adobe Analytics existente junto con la nueva implementación de Customer Journey Analytics para un periodo de tiempo específico (por ejemplo, 1 año). Al elegir esta opción, tenga en cuenta lo siguiente:

* Los datos no estarían disponibles en el Experience Platform.

* Debe planificar la eliminación de la implementación de Adobe Analytics después de tener suficientes datos en Customer Journey Analytics.

## A continuación, realice tareas de implementación adicionales

En este punto del proceso de migración, debe realizar varias tareas de implementación antes de que el entorno de Customer Journey Analytics esté listo para su uso.

Estas tareas adicionales se aplican a las migraciones desde Adobe Analytics, así como a las implementaciones de nuevos Customer Journey Analytics.

Estas tareas incluyen:

* Introducción de otros datos en Experience Platform

* Creación de conexiones entre conjuntos de datos de Platform y el Customer Journey Analytics

* Creación de vistas de datos

* Transferencia del uso de API de informes

* Contabilidad de fuentes de datos y casos de uso de Data Warehouse

* Migración de proyectos y componentes

* Planificación de la incorporación del usuario

Para obtener más información, comience por el Paso 2 en [Introducción al Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
