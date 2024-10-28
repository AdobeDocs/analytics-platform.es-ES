---
title: Crear un esquema para el Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 59%

---

# Uso del esquema de Adobe Analytics con Customer Journey Analytics

>[!NOTE]
>
>Esta documentación se debe usar como parte del [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- this page exists as the "Learn more" link in the info icon for the option "I am comfortable using my Adobe Analytics schema as a basis" -->

La opción de usar un esquema de Adobe Analytics existente con Customer Journey Analytics solo está disponible si la implementación de Adobe Analytics está configurada con el SDK web de Adobe Experience Platform. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

Considere las siguientes ventajas y desventajas de utilizar el esquema de Adobe Analytics con Customer Journey Analytics:

| Ventajas | Desventajas |
|----------|---------|
| <p>Las ventajas de utilizar el esquema de Adobe Analytics son:</p><ul><li>Facilidad de actualización<p>Si ya está enviando datos a Adobe Analytics con el SDK web de Adobe Experience Platform, puede añadir un servicio adicional a la secuencia de datos para que envíe los datos a Adobe Experience Platform (que luego se podrán utilizar en la configuración de Customer Journey Analytics).</p></li></ul> | <p>Las desventajas de utilizar el esquema de Adobe Analytics son:</p><ul><li>Aunque el uso del esquema de Adobe Analytics no le limita en términos de cómo se puede utilizar con otras aplicaciones de Platform, sí da lugar a un esquema más complejo de lo que podría ser. Esto se debe a que el esquema de Adobe Analytics contiene muchos objetos específicos de Adobe Analytics que es poco probable que su organización utilice.<p>Cuando es necesario realizar cambios en el esquema, hay que rebuscar entre miles de campos no utilizados para encontrar el campo que requiere actualización.</p></li></ul> |

<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->