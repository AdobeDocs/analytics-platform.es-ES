---
title: Actualización de Adobe Analytics a Customer Journey Analytics
description: Obtenga información acerca de los pasos recomendados al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1629'
ht-degree: 10%

---

# Actualización de Adobe Analytics a Customer Journey Analytics

Al actualizar de Adobe Analytics a Customer Journey Analytics, puede seguir los [pasos de actualización recomendados](#recommended-upgrade-steps-for-most-organizations). O puede [generar dinámicamente pasos de actualización](#dynamically-generate-upgrade-steps-for-your-organization) para las circunstancias únicas de su organización.

## Pasos de actualización recomendados para la mayoría de las organizaciones {#upgrade-process}

El proceso recomendado para actualizar de Adobe Analytics a Customer Journey Analytics es una nueva implementación de Experience Platform Web SDK, que es el método de recopilación de datos preferido para Customer Journey Analytics. Junto con Web SDK, Adobe también recomienda utilizar el conector de origen de Analytics para facilitar la transición a Customer Journey Analytics. Utilice el conector de origen de Analytics para conservar los datos del historial de Adobe Analytics y realizar comparaciones de datos en paralelo.

Una vez que tenga suficientes datos históricos mediante Experience Platform Web SDK y haya realizado la transición completa a Customer Journey Analytics, el conector de origen de Analytics se puede desactivar y Web SDK se puede utilizar de forma exclusiva.

>[!NOTE]
>
>Si los pasos de actualización descritos en esta sección no son prácticos para su organización, utilice la Guía de actualización de Customer Journey Analytics para generar dinámicamente pasos de actualización adaptados a las circunstancias únicas de su organización. (Para acceder a la guía desde Customer Journey Analytics, selecciona la pestaña **[!UICONTROL Workspace]** y, a continuación, selecciona **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo. Siga las instrucciones que aparecen en pantalla).

### Proceso de actualización recomendado de alto nivel {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Datos históricos de Adobe Analytics"
>abstract="Incorpore sus datos históricos del grupo de informes de Adobe Analytics a Adobe Experience Platform y Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementar Experience Platform Web SDK (para la recopilación de datos continua)**

   Una nueva implementación de Experience Platform Web SDK es la mejor manera de recopilar datos para Customer Journey Analytics. Proporciona la mejor base para sacar el máximo partido a Customer Journey Analytics, ya que es el método con más rendimiento, sencillo y preparado para el futuro para implementar Customer Journey Analytics.

   * Creación de informes y disponibilidad de datos de alto rendimiento porque Adobe Experience Platform está diseñado para potenciar los casos de uso de personalización en tiempo real

   * Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)

   * No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)

1. **Configurar el conector de origen de Adobe Analytics (para traer datos históricos)**

   Para facilitar una transición sin problemas al uso de Experience Platform Web SDK con Customer Journey Analytics, Adobe también recomienda utilizar el conector de origen de Adobe Analytics. Esto le permite conservar los datos históricos y ver los datos de su implementación de Adobe Analytics existente en Customer Journey Analytics, junto con los datos de su nueva implementación de Experience Platform Web SDK.

   El conector de origen de Analytics le permite:

   * Incorpore sus datos históricos del grupo de informes de Adobe Analytics a Adobe Experience Platform y Customer Journey Analytics.

     Puede mantener el conector de origen de Analytics en ejecución durante el tiempo que necesite para conservar los datos del historial de Adobe Analytics.

   * Vea los datos recopilados con la implementación original de Adobe Analytics (AppMeasurement, la extensión de Analytics o la extensión de SDK web) en Customer Journey Analytics. Puede comparar estos datos en paralelo con los de su nueva implementación de Web SDK.

     Puede mantener el conector de origen de Analytics en ejecución hasta que esté familiarizado y cómodo con las diferencias. <!--elaborate on what those differences are? -->

   El conector de origen de Analytics como implementación independiente no es un método recomendado a largo plazo para utilizar Customer Journey Analytics. Esto se debe a la alta latencia, a los esquemas desordenados y complejos, a la dependencia de la nomenclatura de Adobe Analytics (prop, eVar, etc.) y a la dificultad para pasar finalmente del conector de origen de Analytics a la implementación de Web SDK recomendada.

### Pasos de actualización detallados recomendados

Los siguientes pasos describen el proceso recomendado para actualizar de Adobe Analytics a Customer Journey Analytics.

Cada paso proporciona una explicación de alto nivel de un proceso más detallado. Siga el vínculo de cada paso y complete sus tareas asociadas; a continuación, vuelva a esta página y continúe con el siguiente paso del proceso.

1. [Planifique su arquitectura de esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Cree el esquema personalizado que desee en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Tenga en cuenta las siguientes opciones al crear el esquema:

   * Si desea integrar Customer Journey Analytics con RTCDP, debe habilitar la opción **[!UICONTROL Perfil]** en su esquema, tal como se describe en [Crear un esquema XDM para utilizarlo con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). Con esta opción habilitada, cuando los datos se incorporan a conjuntos de datos basados en este esquema, esos datos se combinan en el Perfil del cliente en tiempo real.

   * Si desea incluir datos de medios de transmisión, debe [configurar su esquema para que ingrese y use datos de transmisión](/help/data-ingestion/streaming.md).

1. [Crear un conjunto de datos en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Opcional) Si utiliza datos de clasificación en Adobe Analytics, puede agregar datos de clasificación al conjunto de datos en Customer Journey Analytics.

   Para ello, [cree un conjunto de datos de búsqueda para cada dimensión que contenga datos de clasificación](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Para implementaciones de Adobe Analytics que usan AppMeasurement o la extensión de Analytics (etiquetas), [cree una secuencia de datos en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Para implementaciones de Adobe Analytics que utilizan Web SDK, ya existe una secuencia de datos. Para obtener más información, consulte [Configuración de la implementación de Adobe Analytics Web SDK existente para enviar datos a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Agregue Adobe Experience Platform como servicio a su secuencia de datos](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Opcional) Si desea integrar Customer Journey Analytics con Adobe Journey Optimizer, utilice el objeto de personalización en la implementación para utilizarlo en Adobe Journey Optimizer.

1. Expanda la sección que describe cómo desea implementar Experience Platform Web SDK para la implementación de Customer Journey Analytics y, a continuación, complete los pasos asociados:

   +++Implementación manual (archivo JS)

   1. [Agregue alloy.js a su sitio](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Rellene un objeto XDM y envíelo al conjunto de datos.

+++

   +++Etiquetas

   1. [Cree una propiedad de etiquetas y agregue la extensión Adobe Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Añada la extensión de SDK web de Adobe Experience Platform a su propiedad de etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implemente la etiqueta de carga en su sitio](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Agregue la lógica de recopilación de datos XDM a su etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Utilice la API de Edge Network para enviar datos al conjunto de datos deseado.

+++

1. [Compruebe que su implementación de Web SDK está enviando datos a un conjunto de datos](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Crear una conexión en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Opcional) Asocie datos web con datos de otros canales, como los datos del centro de llamadas.

   Esto se logra agregando conjuntos de datos adicionales a la conexión de Customer Journey Analytics, tal como se describe en [Importar centro de llamadas y datos web](/help/use-cases/cross-channel/call-center.md).

1. [Crear una vista de datos en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Valide que los datos estén fluyendo a la vista de datos en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migrar proyectos y componentes](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Opcional) Si usa canales de marketing en Adobe Analytics, puede [crear un campo derivado del canal de marketing en Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Los campos derivados son un aspecto importante de los informes en tiempo real de Customer Journey Analytics. Un campo derivado le permite definir (a menudo complejas) manipulaciones de datos sobre la marcha, a través de un generador de reglas personalizable.

   Un uso de los campos derivados es definir un campo de canal de marketing derivado que determine el canal de marketing adecuado en función de una o más condiciones (por ejemplo, parámetro de URL, dirección URL de página o nombre de página).

   Utilice [la plantilla de función de canales de marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) en los campos derivados para crear rápidamente un campo derivado para los canales de marketing.

1. Compare datos de la implementación antigua de Adobe Analytics con los datos de la nueva implementación de Customer Journey Analytics y asegúrese de comprender cualquier diferencia y por qué existen. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Obtenga datos históricos de Adobe Analytics mediante el conector de origen de Analytics:

   >[!NOTE]
   >
   >Siga estos pasos si no ha creado anteriormente un conector de origen de Analytics.
   >
   >Si ya está usando el conector de origen de Analytics con Customer Journey Analytics, siga los pasos de [Transición del conector de origen de Analytics a Web SDK para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Creación de un esquema XDM para el conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Si aún no tiene un conector de origen de Analytics, [cree el conector de origen de Analytics y asigne campos de al esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      O

      Si ya tiene un conector de origen de Analytics, [asigne campos del conector de origen al esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Agregue el conjunto de datos del conector de origen de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Planifique la incorporación del usuario.

   Al igual que en Adobe Analytics, Analysis Workspace es la principal herramienta de cara al usuario en Customer Journey Analytics. Sin embargo, existen algunas diferencias clave al utilizar Analysis Workspace en Customer Journey Analytics que los usuarios deben tener en cuenta.

   Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics.

   Para obtener información sobre algunas de las diferencias clave entre Adobe Analytics y Customer Journey Analytics, consulte [Guía del usuario para usuarios de Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Obtenga información acerca de la compatibilidad con [funciones en Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). La mayoría de las funciones de Adobe Analytics son compatibles con Customer Journey Analytics y hay muchas funciones adicionales disponibles en Customer Journey Analytics.

1. Deshabilite Adobe Analytics cuando la implementación de Customer Journey Analytics Web SDK haya finalizado y esté cómodo con los datos que está recopilando.

   Adobe recomienda mantener el entorno de Adobe Analytics en ejecución durante un periodo de tiempo después de implementar Customer Journey Analytics.

   Para obtener más información sobre los usos de Adobe Analytics durante una actualización y después de ella, así como el momento sugerido para deshabilitar Adobe Analytics, vea [Evaluar cuánto tiempo necesita Adobe Analytics después de actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Generar pasos de actualización de forma dinámica para su organización

Según varios factores, como la escala de tiempo y las restricciones de recursos, los pasos de actualización recomendados que se describen en [Comprenda los pasos de actualización recomendados](#1-understand-the-recommended-upgrade-steps) podrían no ser prácticos para su organización.

Para generar dinámicamente los pasos de actualización para las circunstancias únicas de su organización:

1. Complete la Guía de actualización de Customer Journey Analytics.

   Para acceder a la guía desde Customer Journey Analytics, selecciona la pestaña **[!UICONTROL Workspace]** y, a continuación, selecciona **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo. Siga las instrucciones que aparecen en pantalla.

   Después de completar esta guía de actualización, se le proporcionan instrucciones paso a paso, en las que se describen los pasos de actualización óptimos que son exclusivos de los requisitos de su organización. Estos son los pasos de actualización que mejor se alinean con su entorno de Adobe Analytics existente y sus objetivos para Customer Journey Analytics.

1. Siga las instrucciones paso a paso generadas para actualizar a Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
