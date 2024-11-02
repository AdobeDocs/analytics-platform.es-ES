---
title: Actualizar acceso directo Migrar una implementación de extensión de AppMeasurement o Analytics para utilizar el SDK web
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8ef60cc3918b79919674e3c0478a2c1b1bd21d27
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 46%

---

# Método abreviado de actualización: Migrar una implementación de extensión de AppMeasurement o Analytics para utilizar el SDK web {#shortcut-migrate-websdk}

>[!NOTE]
>
>Esta documentación se debe usar como parte del [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Migre su implementación de Analytics para utilizar el SDK web"
>abstract="En lugar de enviar datos a través de un objeto XDM, puede enviar todas las variables en formato de AppMeasurement a través del objeto de datos. Este método abreviado le permite seguir utilizando la lógica de AppMeasurement para enviar datos a Platform."

<!-- markdownlint-enable MD034 -->

Al actualizar a Customer Journey Analytics, el Adobe [recomienda una nueva implementación del SDK web de Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Sin embargo, dependiendo de varios factores, como el calendario y las restricciones de recursos, los pasos de actualización recomendados podrían no ser prácticos para su organización.

Si la implementación de Adobe Analytics es de AppMeasurement para la extensión de Analytics, hay disponible un método abreviado de actualización que le permite migrar la implementación de Adobe Analytics para utilizar el SDK web de Adobe Experience Platform para comenzar a enviar datos a Edge Network y Adobe Analytics, antes de enviarlos a Customer Journey Analytics.

## Ventajas y desventajas

Considere las siguientes ventajas y desventajas del método abreviado de actualización para migrar la implementación de extensión de AppMeasurement o Analytics y utilizar el SDK web:

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>**Ofrece todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas son:</p><ul><li>Informes de alto rendimiento y disponibilidad de datos porque Adobe Experience Platform se ha creado para potenciar [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Utiliza la implementación existente**: aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación sin que ello afecte a los informes de Adobe Analytics existentes.</li><li>**Ofrece flexibilidad para crear un esquema XDM para su organización más adelante**: puede migrar la implementación de Adobe Analytics existente para que utilice el SDK web y validar que todo funciona en Adobe Analytics y, a continuación, crear el esquema XDM. Esta flexibilidad permite una actualización más metódica y considerada a Customer Journey Analytics.</li></ul> | <ul><li>**Requiere asignación para enviar datos a Platform**: cuando su organización esté lista para utilizar Customer Journey Analytics, debe enviar los datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto de datos sea una entrada en la herramienta de asignación de la secuencia de datos que lo asigna a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario cuando se envían datos en un objeto XDM.</li><li>**Deuda técnica**: debido a que este enfoque utiliza una forma modificada de la implementación existente, puede resultar más difícil rastrear la lógica de implementación y realizar cambios en el futuro cuando sea necesario. </li></ul> |

{style="table-layout:auto"}

## Pasos básicos

Si decide utilizar el acceso directo de actualización para migrar la implementación de extensión de AppMeasurement o Analytics con el fin de utilizar el SDK web, se agrega un nuevo paso a los pasos generados dinámicamente para su organización en el cuestionario de actualización [Adobe Analytics to Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Los pasos básicos para migrar una implementación de extensión de AppMeasurement o Analytics para utilizar el SDK web son los siguientes:

1. Comience a enviar datos a Platform.

   Si ya está enviando datos a Platform con la implementación de Adobe Analytics, este paso no es obligatorio. Simplemente debe crear una conexión entre los conjuntos de datos de Platform y el Customer Journey Analytics, tal como se describe más adelante en este proceso.

1. (Opcional) Cree un esquema XDM para su organización si dispone de tiempo.

1. (Condicional) Si ha creado un esquema XDM, utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.

