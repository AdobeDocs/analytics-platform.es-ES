---
title: Envío de datos a Adobe Experience Platform al migrar a Customer Journey Analytics
description: Envío de datos a Adobe Experience Platform al migrar a Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 1c789264a9867279f58a3ad139207fec8db29c1b
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Paso 3: Envío de datos a Adobe Experience Platform al migrar

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de migración más amplio. Asegúrese de que se han completado todos los pasos de migración anteriores.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de migración anteriores.

La información de esta página cubre el paso 3 de la migración, como se indica en la tabla siguiente:

| Tarea de migración | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| **Paso 2: [Elija la ruta de migración](/help/getting-started/cja-migration/cja-migration-path.md)** | Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| <span class="preview">**Paso 3: Envío de datos a Adobe Experience Platform**</span> | <span class="preview">El proceso de envío de datos a Adobe Experience Platform difiere según la ruta de migración elegida en el paso 2.</span> |
| **Paso 4: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 5: [Realizar tareas de implementación adicionales](/help/getting-started/cja-getting-started.md)** | En este punto del proceso de migración, debe realizar varias tareas antes de que el entorno del Customer Journey Analytics esté listo para su uso.<p>Estas tareas adicionales se aplican a las migraciones desde Adobe Analytics, así como a las implementaciones de nuevos Customer Journey Analytics.</p><p>Estas tareas incluyen:</p><ul><li>Introducción de otros datos en Experience Platform</li><li>Creación de conexiones entre conjuntos de datos de Platform y el Customer Journey Analytics</li><li>Creación de vistas de datos</li><li>Transferencia del uso de API de informes</li><li>Contabilidad de fuentes de datos y Data Warehouse</li><li>Migración de proyectos y componentes</li><li>Planificación de la incorporación del usuario</li></ul> <p>Para obtener más información, consulte [Introducción al Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++


Después de usted [elija la ruta de migración](#step-2-choose-your-customer-journey-analytics-migration-method) para que esto sea lo mejor para su organización, puede empezar a enviar datos a Adobe Experience Platform para que estén disponibles en Customer Journey Analytics.

A continuación, se muestra el proceso para enviar datos al Experience Platform para cada ruta de migración. Siga los vínculos de la tabla para obtener información detallada sobre la configuración.

| Ruta de migración | Proceso para enviar datos a Platform | Información adicional |
|---------|----------|----------|
| Nueva implementación del SDK web de Experience Platform | <ol><li>Cree un esquema XDM para su organización.<p>Trabaje con su equipo de datos para identificar el diseño de esquema ideal de su organización para Customer Journey Analytics.</p></li><li>Implemente el SDK web de Experience Platform.</li><li>Envíe datos a Platform.</li></ol><p>Para obtener información detallada sobre cada uno de estos pasos, consulte [Ingesta de datos mediante el SDK web de Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md). | Como se trata de una nueva implementación del SDK web de Experience Platform, no es necesaria la asignación de esquemas, ya que debe crearlo como uno de los primeros pasos durante la implementación. |
| Migre su implementación de Adobe Analytics para utilizar el SDK web | <ol><li>Mueva la implementación de Adobe Analytics existente al SDK web de Experience Platform y, a continuación, compruebe que todo funciona en Adobe Analytics.<p>Para obtener información sobre cómo hacerlo, utilice los siguientes recursos, en función de si la implementación actual es la extensión de etiquetas o el AppMeasurement de Analytics:</p><ul><li>Si utiliza la extensión de etiquetas de Analytics, consulte [Migración de la extensión de etiqueta de Adobe Analytics a la extensión de etiqueta del SDK web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Si utiliza AppMeasurement, consulte [Migración del AppMeasurement al SDK web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Creación de un esquema XDM para su organización](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Trabaje con su equipo de datos para identificar el diseño de esquema ideal de su organización para Customer Journey Analytics.</p></li><li>[Utilice la preparación de datos para asignar todos los campos del objeto de datos al esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>Comience a enviar datos a Platform mediante [configuración de una secuencia de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configure la implementación existente del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics | <ol><li>Comience a enviar datos a Platform mediante [configuración de una secuencia de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).<p>Dado que la implementación de Adobe Analytics ya está utilizando el SDK web de Experience Platform, puede ignorar las demás secciones de [Ingesta de datos mediante el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</li><li>(Opcional) [Creación de un esquema XDM para su organización](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Trabaje con su equipo de datos para identificar el diseño de esquema ideal de su organización para Customer Journey Analytics.</p><p>Nota: Para obtener más información sobre las ventajas de crear un esquema XDM, consulte [Elija su esquema](/help/getting-started/cja-migration/cja-migration-path.md#choose-your-schema).</li><li>(Condicional) Si ha creado un esquema XDM, [Utilice la preparación de datos para asignar todos los campos del objeto de datos al esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |
| Uso del conector de origen de Analytics | [Ingesta y uso de datos de Adobe Analytics tradicional](/help/data-ingestion/analytics.md) | Los datos de Adobe Analytics se asignan automáticamente al esquema XDM al utilizar el conector de origen de Analytics. No se requiere una asignación adicional. |

## A continuación, conserve los datos históricos

A continuación, decida cómo lo hará [conservar datos históricos de Adobe Analytics](/help/getting-started/cja-migration/cja-migration-historical-data.md).
