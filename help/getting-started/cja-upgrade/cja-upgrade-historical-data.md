---
title: Conservar datos históricos al actualizar a Customer Journey Analytics
description: Obtenga información sobre cómo conservar datos históricos al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 55%

---

# Paso 4: Conservar los datos históricos al actualizar

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de actualización más amplio. Asegúrese de que todos los pasos de actualización anteriores estén completos.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de actualización anteriores.

La información de esta página cubre el paso 4 del proceso de actualización, como se indica en la tabla siguiente:

| Actualizar tarea | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la actualización](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Conozca las ventajas de actualizar a Customer Journey Analytics y el proceso de actualización básico. |
| **Paso 2: [Elija la ruta de actualización](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Hay varios métodos disponibles para actualizar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, en función del entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| **Paso 3: [Enviar datos a Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según la ruta de actualización elegida en el paso 2. |
| <span class="preview">**Paso 4: Conservar los datos históricos**</span> | <span class="preview">La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo.</span> |
| **Paso 5: [Realizar tareas de implementación adicionales](/help/getting-started/cja-getting-started.md)** | En este punto del proceso de actualización, debe realizar varias tareas antes de que el entorno del Customer Journey Analytics esté listo para su uso.<p>Estas tareas adicionales se aplican a las actualizaciones desde Adobe Analytics, así como a las nuevas implementaciones de Customer Journey Analytics.</p><p>Esta tareas son:</p><ul><li>Incorporación de datos a Experience Platform</li><li>Creación de conexiones entre conjuntos de datos de Platform y Customer Journey Analytics</li><li>Creación de vistas de datos </li><li>Transferencia del uso de API de informes</li><li>Contabilidad de fuentes de datos y Data Warehouse</li><li>Migración de proyectos y componentes</li><li>Planificación de la incorporación del usuario</li></ul> <p>Para obtener más información, consulte [Introducción a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Elija una de las siguientes opciones para conservar los datos históricos al pasar de Adobe Analytics a Customer Journey Analytics:

>[!IMPORTANT]
>
>Cuando decida cómo conservar los datos históricos, póngase en contacto con el representante de su cuenta de Adobe para determinar los precios.

## Uso del conector de origen de Analytics

Puede usar el [conector de origen de Analytics](/help/data-ingestion/analytics.md) para conservar los datos históricos. Independientemente de la ruta de actualización que elija (aunque actualice mediante el SDK web), puede utilizar el conector de Source de Analytics para conservar los datos históricos del entorno de Adobe Analytics.

Puede utilizar el conector de origen de Analytics para conservar los datos históricos llevándolos a su propia ubicación dedicada, independiente de los datos actuales.

El conector de origen de Analytics debe funcionar durante todo el tiempo que necesite acceder a los datos históricos.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Mantener la implementación de Adobe Analytics existente

Puede mantener su implementación de Adobe Analytics existente junto con la nueva implementación de Customer Journey Analytics durante un lapso de tiempo específico (por ejemplo, un año). Al elegir esta opción, tenga en cuenta lo siguiente:

* Los datos no estarían disponibles en Experience Platform.

* Debe planificar el desmantelamiento de la implementación de Adobe Analytics una vez que disponga de datos suficientes en Customer Journey Analytics.

## A continuación, realice tareas de implementación adicionales

En este punto del proceso de actualización, debe realizar varias tareas de implementación antes de que el entorno de Customer Journey Analytics esté listo para su uso.

Estas tareas adicionales se aplican a las actualizaciones desde Adobe Analytics, así como a las nuevas implementaciones de Customer Journey Analytics.

Esta tareas son:

* Incorporación de datos a Experience Platform

* Creación de conexiones entre conjuntos de datos de Platform y Customer Journey Analytics

* Creación de vistas de datos 

* Transferencia del uso de API de informes

* Contabilidad de fuentes de datos y casos de uso de Data Warehouse

* Migración de proyectos y componentes

* Planificación de la incorporación del usuario

Para obtener más información, comience por el Paso 2 en [Introducción al Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
