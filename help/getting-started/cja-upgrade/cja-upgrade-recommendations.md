---
title: Ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 4%

---

# Actualización de Adobe Analytics a Customer Journey Analytics

Antes de comenzar el proceso de actualización de Adobe Analytics a Customer Journey Analytics, es necesario que entienda los pasos de actualización recomendados.

Según varios factores, como la cronología y las restricciones de recursos, es posible que los pasos de actualización recomendados no sean prácticos para su organización. Después de comprender los pasos de actualización recomendados, complete el cuestionario para generar dinámicamente pasos de actualización adaptados a las circunstancias únicas de su organización.

## 1. Comprender los pasos de actualización recomendados

>[!NOTE]
>
>Los pasos de actualización descritos en esta sección son los pasos de actualización recomendados que cualquier organización podría utilizar para actualizar correctamente de Adobe Analytics a Customer Journey Analytics.
>
>Sin embargo, dependiendo de varios factores, como el calendario y las restricciones de recursos, los pasos de actualización recomendados podrían no ser prácticos para su organización. Después de comprender los pasos de actualización recomendados, complete el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) para generar dinámicamente pasos de actualización adaptados a las circunstancias únicas de su organización.

Los pasos recomendados al actualizar de Adobe Analytics a Customer Journey Analytics son una nueva implementación del SDK web de Experience Platform, que es el método de recopilación de datos preferido para Customer Journey Analytics. Junto con el SDK web, Adobe también recomienda utilizar el conector de origen de Analytics para conservar los datos históricos de Adobe Analytics y realizar comparaciones de datos en paralelo.

Después de realizar la transición completa a Customer Journey Analytics, el conector de origen de Analytics se puede desactivar y el SDK web de Experience Platform se puede utilizar de forma exclusiva.

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

## 2. Generar dinámicamente pasos de actualización para su organización

Según varios factores, como la escala de tiempo y las restricciones de recursos, los pasos de actualización recomendados que se describen en [Comprenda los pasos de actualización recomendados](#1-understand-the-recommended-upgrade-steps) podrían no ser prácticos para su organización.

Para ver los pasos de actualización generados dinámicamente para las circunstancias únicas de su organización:

1. Complete el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Después de completar este cuestionario, se le proporcionan instrucciones paso a paso, en las que se describen los pasos de actualización óptimos que son exclusivos de su organización. Estos son los pasos de actualización que mejor se alinean con su entorno de Adobe Analytics existente y sus objetivos para Customer Journey Analytics.

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









