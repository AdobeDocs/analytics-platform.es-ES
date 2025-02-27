---
title: Métodos alternativos al actualizar a Customer Journey Analytics
description: Obtenga información acerca de los métodos alternativos al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 19%

---

# Alternativa de actualización: Utilice la recopilación de datos de AppMeasurement con Experience Platform Web SDK y Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Usar la lógica de AppMeasurement con Web SDK"
>abstract="En lugar de enviar datos a través de un objeto XDM, envíe todas las variables en formato AppMeasurement a través del objeto de datos.<br><br>Esta opción ahorra tiempo de implementación al permitirle asignar la lógica de AppMeasurement a XDM, en lugar de rellenar un objeto XDM desde cero. Sin embargo, aumenta la complejidad con el tiempo, ya que cualquier campo que agregue en el futuro debe asignarse a XDM en la secuencia de datos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Al actualizar a Customer Journey Analytics, Adobe [recomienda una nueva implementación de Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Sin embargo, dependiendo de varios factores, como el calendario y las restricciones de recursos, los pasos de actualización recomendados podrían no ser prácticos para su organización.

Puede utilizar la lógica de recopilación de datos de la extensión de AppMeasurement o Analytics con Web SDK para enviar datos a Platform y Customer Journey Analytics, en lugar de recopilar datos con el objeto XDM. Sin embargo, esta alternativa introduce una complejidad adicional a lo largo del tiempo.

## Ventajas y desventajas

Este método se excluye mutuamente con [el envío de toda la capa de datos a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), ya que ambos métodos realizan la misma tarea. (Este método es preferible a enviar toda la capa de datos a Adobe. Es más refinado porque las props y las evars pasan por los datos.__adobe.analytics._nombre-variable_.)

Considere las siguientes ventajas y desventajas de utilizar esta alternativa de actualización:

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>**Ofrece todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas son:</p><ul><li>Informes de alto rendimiento y disponibilidad de datos porque Adobe Experience Platform se ha creado para potenciar [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>No se limita a la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Utiliza la implementación existente**: aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Permite asignar la lógica de AppMeasurement a XDM, en lugar de rellenar un objeto XDM desde cero.</li></ul> | <ul><li>**Requiere asignación para enviar datos a Platform**: cuando su organización esté lista para utilizar Customer Journey Analytics, debe enviar los datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto de datos sea una entrada en la herramienta de asignación de la secuencia de datos que lo asigna a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario cuando se envían datos en un objeto XDM.</li><li>**Introduce una complejidad adicional con el tiempo**: cualquier campo que agregue en el futuro debe asignarse a XDM en el conjunto de datos.<p>Cada vez que se añade un nuevo campo a la implementación, puede realizar una de las siguientes acciones:</p><ul><li>**Opción 1:** Rellene una nueva eVar arbitraria o prop en el objeto de datos y, a continuación, asígnelo al campo XDM deseado.<p>Este proceso aporta coherencia a la implementación del lado del cliente, pero requiere asignación.</p></li><li>**Opción 2:** Deje el objeto de datos como una implementación heredada y empiece a rellenar solo el objeto XDM para todos los campos nuevos.<p>Este proceso no requiere asignación, pero significa que algunas de las variables solo se encuentran en un objeto de datos, mientras que otras variables solo se encuentran en un objeto XDM. Cada vez que necesite solucionar problemas de la implementación, debe ir a dos lugares. Asegúrese de que los flujos de trabajo internos se adaptan a esto.</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## Pasos básicos

Los pasos básicos para migrar una implementación de Adobe Analytics (ya sea AppMeasurement o la extensión de Analytics) para utilizar la SDK web y enviar datos a Customer Journey Analytics son los siguientes:

1. (Opcional) Migre su implementación de Adobe Analytics para utilizar Adobe Experience Platform Web SDK y comenzar a enviar datos a Edge Network.

   Este es un paso opcional que le permite migrar su implementación de Adobe Analytics existente para utilizar Web SDK y validar que todo funciona en Adobe Analytics. Una vez que se ha configurado y los datos de Adobe Analytics son satisfactorios, puede enviar datos de Edge Network a Customer Journey Analytics.

   Esta flexibilidad permite una actualización más metódica y considerada a Customer Journey Analytics.

   Para obtener información sobre cómo hacerlo, consulte los siguientes artículos en la documentación de Adobe Analytics:

   * [Migrar a Web SDK mediante etiquetas](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrar a Web SDK mediante JavaScript](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Enviar datos de Edge Network a Customer Journey Analytics.

   1. Envíe todas las variables en formato AppMeasurement a través del objeto de datos.

      Para obtener más información, vea [Asignación de variables de objetos de datos a Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Si aún no lo ha hecho, cree un esquema XDM para su organización.

      Para obtener más información, consulte [Crear un esquema personalizado para utilizarlo con su implementación de Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   1. Utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.

      Para obtener más información, consulte [Asignación](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) en [Preparación de datos para la recopilación de datos](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) en la documentación de Experience Platform.
