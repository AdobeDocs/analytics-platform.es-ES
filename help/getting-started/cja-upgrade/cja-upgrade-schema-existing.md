---
title: Elija su esquema para Customer Journey Analytics
description: Obtenga información sobre las opciones disponibles al elegir un esquema para Customer Journey Analytics y las ventajas y desventajas de cada uno
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---

# Elija su esquema para Customer Journey Analytics {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="Uso de un esquema personalizado"
>abstract="(Recomendado) La personalización de su esquema permite a la organización realizar un seguimiento únicamente de lo que necesita y evitar la sobrecarga vinculada a campos confusos e innecesarios. Esta opción incluye grupos de campos añadidos por el SDK web y grupos de campos personalizados para su organización."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="Uso del esquema predeterminado"
>abstract="(No recomendado) El esquema de Adobe Analytics contiene más de mil campos, lo que puede generar esquemas desordenados y complejos. Su organización se vería obligada a seguir utilizando el concepto de props y eVars, que es un concepto heredado que no se usa en Customer Journey Analytics. La integración con otros servicios de Adobe Experience Platform es más difícil."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Al actualizar a Customer Journey Analytics, Adobe recomienda crear un esquema de modelo de datos de experiencia (XDM) personalizado para que se ajuste mejor a las necesidades de su organización a medida que comienza a utilizar otros servicios de Platform. También puede optar por utilizar el esquema de Adobe Analytics existente.

Considere las ventajas y desventajas de cada uno.

## Crear un esquema personalizado adaptado a su organización (recomendado)

Adobe recomienda crear un esquema personalizado al actualizar a Customer Journey Analytics.

| Ventajas | Desventajas |
|----------|---------|
| <ul><p>Las ventajas de actualizar a su propio esquema personalizado son:</p><ul><li>Un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza.</li><p>Cuando es necesario realizar cambios en el esquema, no es necesario rebuscar entre miles de campos no utilizados para encontrar el campo que requiere actualización.</p></ul> | <p>Las desventajas de actualizar a su propio esquema personalizado son:</p><ul><li>Actualizar el esquema es un proceso que lleva tiempo y que es necesario antes de empezar a enviar datos a Customer Journey Analytics.</li></ul> |

## Uso del esquema de Adobe Analytics existente

La opción de usar el esquema de Adobe Analytics existente con Customer Journey Analytics solo está disponible si la implementación de Adobe Analytics se ha configurado con el SDK web de Adobe Experience Platform. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Ventajas | Desventajas |
|----------|---------|
| <p>Las ventajas de utilizar el esquema de Adobe Analytics son:</p><ul><li>Fácil actualización<p>Si ya está enviando datos a Adobe Analytics con el SDK web de Adobe Experience Platform, puede añadir un servicio adicional a la secuencia de datos para que envíe los datos a Adobe Experience Platform (que luego se podrán utilizar en la configuración de Customer Journey Analytics).</p></li></ul> | <p>Las desventajas de utilizar el esquema de Adobe Analytics son:</p><ul><li>Aunque el uso del esquema de Adobe Analytics no le limita en términos de cómo se puede utilizar con otras aplicaciones de Platform, sí da lugar a un esquema más complejo de lo que podría ser. Esto se debe a que el esquema de Adobe Analytics contiene muchos objetos específicos de Adobe Analytics que es poco probable que su organización utilice.<p>Cuando es necesario realizar cambios en el esquema, hay que rebuscar entre miles de campos no utilizados para encontrar el campo que requiere actualización.</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the Customer Journey Analytics Upgrade Guide.

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
