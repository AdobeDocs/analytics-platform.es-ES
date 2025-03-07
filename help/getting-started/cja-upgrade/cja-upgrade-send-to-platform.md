---
title: Envío de datos a Adobe Experience Platform al migrar a Customer Journey Analytics
description: Envío de datos a Adobe Experience Platform al migrar a Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 58%

---

# Paso 3: Enviar datos a Adobe Experience Platform al actualizar

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de actualización más amplio. Asegúrese de que todos los pasos de actualización anteriores estén completos.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de actualización anteriores.

La información de esta página cubre el paso 3 del proceso de actualización, como se indica en la tabla siguiente:

| Actualizar tarea | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la actualización](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Conozca las ventajas de actualizar a Customer Journey Analytics y el proceso de actualización básico. |
| **Paso 2: [Elija la ruta de actualización](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Hay varios métodos disponibles para actualizar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, en función del entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| <span class="preview">**Paso 3: Enviar datos a Adobe Experience Platform**</span> | <span class="preview">El proceso de envío de datos a Adobe Experience Platform varía según la ruta de actualización elegida en el paso 2.</span> |
| **Paso 4: [Conservar los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 5: [Realizar tareas de implementación adicionales](/help/getting-started/cja-getting-started.md)** | En este punto del proceso de actualización, debe realizar varias tareas antes de que el entorno de Customer Journey Analytics esté listo para su uso.<p>Estas tareas adicionales se aplican a las actualizaciones desde Adobe Analytics, así como a las nuevas implementaciones de Customer Journey Analytics.</p><p>Esta tareas son:</p><ul><li>Incorporación de datos a Experience Platform</li><li>Creación de conexiones entre conjuntos de datos de Platform y Customer Journey Analytics</li><li>Creación de vistas de datos </li><li>Transferencia del uso de API de informes</li><li>Contabilidad de fuentes de datos y Data Warehouse</li><li>Migración de proyectos y componentes</li><li>Planificación de la incorporación del usuario</li></ul> <p>Para obtener más información, consulte [Introducción a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>La información de esta página se reemplaza con la siguiente información de actualización más completa: <ul><li>**Pasos de actualización recomendados**<p>Para obtener información detallada, consulte [Ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guía de actualización de Customer Journey Analytics**<p>Hay disponible una nueva guía de actualización que genera dinámicamente pasos de actualización adaptados a su organización y a sus circunstancias únicas.</p><p>Para acceder a la guía desde Customer Journey Analytics, selecciona la pestaña **[!UICONTROL Workspace]** y, a continuación, selecciona **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo. Siga las instrucciones que aparecen en pantalla.</p></li></ul>

Después de [elegir la ruta de actualización](/help/getting-started/cja-upgrade/cja-upgrade-path.md) que sea mejor para su organización, puede empezar a enviar datos a Adobe Experience Platform para que estén disponibles en Customer Journey Analytics.

A continuación, se muestra el proceso para enviar datos a Experience Platform para cada ruta de actualización. Siga los vínculos de la tabla para obtener información detallada sobre la configuración.

| Ruta de actualización | Proceso para enviar datos a Platform | Información adicional |
|---------|----------|----------|
| Nueva implementación del SDK web de Experience Platform | <ol><li>Cree un esquema XDM para su organización.<p>Trabaje con su equipo de datos para identificar el diseño de esquema ideal de su organización para Customer Journey Analytics.</p></li><li>Implemente el SDK web de Experience Platform.</li><li>Envíe datos a Platform.</li></ol><p>Para obtener información detallada sobre cada uno de estos pasos, consulte [Ingesta de datos mediante el SDK web de Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md). | Al tratarse de una nueva implementación del SDK web de Experience Platform, no es necesario implementar esquemas, ya que debe crearlos como uno de los primeros pasos durante la implementación. |
| Migrar la implementación de Adobe Analytics para utilizar el SDK web | <ol><li>Mueva la implementación de Adobe Analytics existente al SDK web de Experience Platform y, a continuación, compruebe que todo funciona en Adobe Analytics.<p>Para obtener información sobre cómo hacerlo, utilice los siguientes recursos, en función de si la implementación actual es la extensión de etiquetas o AppMeasurement de Analytics:</p><ul><li>Si utiliza la extensión de etiquetas de Analytics, consulte [Migración de la extensión de etiquetas de Adobe Analytics a la extensión de etiquetas del SDK web](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Si utiliza AppMeasurement, consulte [Migración de AppMeasurement al SDK web](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Cree un esquema XDM para su organización](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Trabaje con su equipo de datos para identificar el diseño de esquema ideal de su organización para Customer Journey Analytics.</p></li><li>[Utilice la preparación de datos para asignar todos los campos del objeto de datos al esquema XDM](https://experienceleague.adobe.com/es/docs/experience-platform/data-prep/home).</li><li>Comience a enviar datos a Platform mediante la [configuración de una secuencia de datos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configure la implementación de Adobe Analytics Web SDK existente para enviar datos a Platform | <ol><li>Comience a enviar datos a Platform mediante la [configuración de una secuencia de datos](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).<p>Dado que la implementación de Adobe Analytics ya está utilizando el SDK web de Experience Platform, puede ignorar las demás secciones de [Ingesta de datos mediante el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</p><p>Si ya está enviando datos a Platform con la implementación de Adobe Analytics, este paso no es obligatorio. Simplemente debe crear una conexión entre los conjuntos de datos de Platform y Customer Journey Analytics, tal como se describe más adelante en este proceso.</p></li><li>(Opcional) [Cree un esquema XDM para su organización](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Trabaje con su equipo de datos para identificar el diseño de esquema ideal de su organización para Customer Journey Analytics.</p><p>Nota: Para obtener más información sobre las ventajas de crear un esquema XDM, consulte [Elección del esquema](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Condicional) Si ha creado un esquema XDM, [utilice la preparación de datos para asignar todos los campos del objeto de datos al esquema XDM](https://experienceleague.adobe.com/es/docs/experience-platform/data-prep/home).</li></ol> |  |
| Uso del conector de origen de Analytics | [Ingesta y uso de datos de Adobe Analytics tradicional](/help/data-ingestion/analytics.md) | Los datos de Adobe Analytics se asignan automáticamente al esquema XDM al utilizar el conector de origen de Analytics. No se requiere una asignación adicional. |

## A continuación, conserve los datos históricos

A continuación, decida cómo [conservará los datos históricos de Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
