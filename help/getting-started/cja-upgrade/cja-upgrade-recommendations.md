---
title: Ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ea16705e96047cbcf41e428d2018ea7c72b2afac
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 8%

---

# Actualización de Adobe Analytics a Customer Journey Analytics

Antes de comenzar el proceso de actualización de Adobe Analytics a Customer Journey Analytics, es necesario que entienda los pasos de actualización recomendados.

>[!NOTE]
>
>Los pasos de actualización descritos en esta sección son los pasos de actualización recomendados que cualquier organización podría utilizar para actualizar correctamente de Adobe Analytics a Customer Journey Analytics.
>
>Sin embargo, dependiendo de varios factores, como el calendario y las restricciones de recursos, los pasos de actualización recomendados podrían no ser prácticos para su organización. En ese caso, use el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) para generar dinámicamente pasos de actualización adaptados a las circunstancias únicas de su organización.

## Pasos de actualización recomendados para la mayoría de las organizaciones

Los pasos recomendados al actualizar de Adobe Analytics a Customer Journey Analytics son una nueva implementación del SDK web de Experience Platform, que es el método de recopilación de datos preferido para Customer Journey Analytics. Junto con el SDK web, Adobe también recomienda utilizar el conector de origen de Analytics para conservar los datos históricos de Adobe Analytics y realizar comparaciones de datos en paralelo.

Después de realizar la transición completa a Customer Journey Analytics, el conector de origen de Analytics se puede desactivar y el SDK web de Experience Platform se puede utilizar de forma exclusiva.

### Proceso de actualización recomendado de alto nivel

1. **Implementar el SDK web de Experience Platform**

   Una nueva implementación del SDK web de Experience Platform es la mejor manera de recopilar datos para Customer Journey Analytics. Proporciona la mejor base para sacar el máximo partido a Customer Journey Analytics, ya que es el método más eficaz, sencillo y con garantía de futuro para implementar Customer Journey Analytics.

   * Creación de informes y disponibilidad de datos de alto rendimiento porque Adobe Experience Platform está diseñado para potenciar los casos de uso de personalización en tiempo real

   * Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)

   * No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)

1. **Configurar el conector de origen de Adobe Analytics**

   Para facilitar una transición sin problemas al uso del SDK web de Experience Platform con Customer Journey Analytics, Adobe también recomienda utilizar el conector de origen de Adobe Analytics. Esto le permite conservar los datos históricos y ver los datos de la implementación de Adobe Analytics existente en Customer Journey Analytics, junto con los datos de la nueva implementación del SDK web de Experience Platform.

   El conector de origen de Analytics le permite:

   * Incluya los datos históricos del grupo de informes de Adobe Analytics en Adobe Experience Platform y Customer Journey Analytics.

     Puede mantener el conector de origen de Analytics en ejecución durante el tiempo que necesite para conservar los datos del historial de Adobe Analytics.

   * Vea los datos recopilados con la implementación original de Adobe Analytics (ya sea AppMeasurement, la extensión de Analytics o la extensión del SDK web) en Customer Journey Analytics. Puede comparar estos datos en paralelo con los de su nueva implementación del SDK web.

     Puede mantener el conector de origen de Analytics en ejecución hasta que esté familiarizado y cómodo con las diferencias. <!--elaborate on what those differences are? -->

   El conector de origen de Analytics como implementación independiente no es un método recomendado a largo plazo para utilizar Customer Journey Analytics. Esto se debe a la alta latencia, a los esquemas complejos y desordenados, a la dependencia de la nomenclatura de Adobe Analytics (prop, eVar, etc.) y a la dificultad para pasar finalmente del conector de origen a la implementación recomendada del SDK web.

### Pasos de actualización detallados recomendados

Los siguientes pasos muestran el proceso recomendado para actualizar de Adobe Analytics a Customer Journey Analytics.

Según el entorno y los requisitos únicos de su organización, es posible que estos pasos recomendados no sean adecuados para su organización. En ese caso, use el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) para generar dinámicamente pasos de actualización adaptados a las circunstancias únicas de su organización.

1. [Planifique su arquitectura de esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Cree el esquema personalizado que desee en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. [Crear un conjunto de datos en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. Expanda la sección que describe la implementación actual de Adobe Analytics y, a continuación, complete los pasos asociados:

   +++Para implementaciones de Adobe Analytics que utilizan el AppMeasurement

   1. [Crear una secuencia de datos en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

   +++Para implementaciones de Adobe Analytics que utilizan la extensión Analytics (etiquetas)

   1. [Crear una secuencia de datos en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

+++ Para implementaciones de Adobe Analytics que utilizan el SDK web

   No se requieren pasos adicionales.

+++

1. [Agregue Adobe Experience Platform como servicio a su secuencia de datos](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. Utilice la siguiente tabla para identificar cualquier función de Adobe Analytics que desee seguir utilizando en Customer Journey Analytics y, a continuación, utilice la información proporcionada para aprender a configurar esas funciones como parte de la actualización a Customer Journey Analytics:

   | Función Adobe Analytics | Requisitos de implementación para Customer Journey Analytics | Información adicional |
   |---------|----------|---------|
   | Datos de clasificación | Cree un conjunto de datos de búsqueda para cada dimensión que contenga datos de clasificación. |  |
   | Canales de marketing | Cree un campo derivado de canal de marketing. |  |
   | Superposición de Activity Map y seguimiento de vínculos | N/A | El Adobe está trabajando en la compatibilidad de superposiciones de Activity Map para el Customer Journey Analytics. |
   | Fuentes de datos | No se requiere configuración durante la implementación.<br/>[Obtenga información acerca de las distintas opciones de exportación de Customer Journey Analytics](/help/analysis-workspace/export/export-project-overview.md). | Aunque todavía no hay un reemplazo directo para las fuentes de datos en Customer Journey Analytics, puede exportar informes de Customer Journey Analytics desde Analysis Workspace para utilizarlos en herramientas de terceros o combinarlos con datos externos. |
   | Data Warehouse | No se requiere configuración durante la implementación.<br/>[Obtenga información acerca de la exportación de tablas completas en Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md). | Customer Journey Analytics La exportación de tablas completas es la evolución de los informes de Data Warehouse en Adobe Analytics, con muchas funciones nuevas y solicitadas que no están disponibles en Data Warehouse en la actualidad. |
   | Datos de medios de streaming |  |  |

1. (Opcional) Incluya datos históricos de Adobe Analytics mediante el conector de origen de Analytics.

   Para obtener más información, consulte [Usar un conector de origen](/help/data-ingestion/sources.md#use-a-source-connector) en [Ingesta y uso de datos mediante conectores de origen](/help/data-ingestion/sources.md).

1. Utilice la siguiente tabla para identificar las funciones de Customer Journey Analytics que desee y, a continuación, utilice la información proporcionada para aprender a configurarlas como parte de la actualización a Customer Journey Analytics:

   | Funciones de Customer Journey Analytics que desea | Requisitos de implementación para Customer Journey Analytics | Información adicional |
   |---------|----------|---------|
   | Asocie datos web con datos de otros canales, como los datos del centro de llamadas | Después de crear una conexión (como se describe en un paso posterior), agregue conjuntos de datos adicionales a la conexión en Customer Journey Analytics. |  |
   | Integración con RTCDP | Habilite el perfil en su esquema y cree un conjunto de datos de perfil para utilizarlo en RTCDP | Esto debe hacerse al crear el esquema XDM. |
   | Integración con Adobe Journey Optimizer | Utilice el objeto de personalización en la implementación para utilizarlo en Adobe Journey Optimizer |  |

1. Expanda la sección que describe la implementación de Customer Journey Analytics que desee y, a continuación, complete los pasos asociados:

   +++Implementación manual (archivo JS)

   1. [Agregue alloy.js a su sitio](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

+++

   +++Etiquetas

   1. [Crear una propiedad de etiquetas en la recopilación de datos de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property).

+++

+++ API

   1. Utilice la API de Edge Network para enviar datos al conjunto de datos deseado.

+++

1. [Crear una conexión en el Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. [Crear una vista de datos en el Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Valide que los datos estén fluyendo al Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migrar proyectos y componentes](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

1. Compare datos de la implementación antigua con los de la nueva implementación y asegúrese de comprender cualquier diferencia y por qué existen.

1. Planifique la incorporación del usuario.

   Al igual que en Adobe Analytics, Analysis Workspace es la principal herramienta de cara al usuario en Customer Journey Analytics. Sin embargo, existen algunas diferencias clave al utilizar Analysis Workspace en Customer Journey Analytics que los usuarios deben tener en cuenta.

   Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics.

   Para obtener información sobre algunas de las diferencias clave entre Adobe Analytics y Customer Journey Analytics, consulte [Guía del usuario para usuarios de Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Deshabilite la recopilación de datos de AppMeasurement.

1. Deshabilite el conector de origen de Analytics.

   Con la implementación del SDK web de Experience Platform, el conector de origen de Analytics solo es necesario para los datos del historial de Adobe Analytics y para comparar los datos de la implementación original con los de la nueva implementación.

   Cuando tenga suficientes datos históricos de la nueva implementación y esté familiarizado con las diferencias de creación de informes en Customer Journey Analytics, debe desactivar el conector de origen de Analytics.

## Generar pasos de actualización de forma dinámica para su organización

Según varios factores, como la escala de tiempo y las restricciones de recursos, los pasos de actualización recomendados que se describen en [Comprenda los pasos de actualización recomendados](#1-understand-the-recommended-upgrade-steps) podrían no ser prácticos para su organización.

Para generar dinámicamente los pasos de actualización para las circunstancias únicas de su organización:

1. Complete el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Después de completar este cuestionario, se le proporcionan instrucciones paso a paso, que describen los pasos de actualización óptimos que son exclusivos de los requisitos de su organización. Estos son los pasos de actualización que mejor se alinean con su entorno de Adobe Analytics existente y sus objetivos para Customer Journey Analytics.

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









