---
title: Métodos alternativos al actualizar a Customer Journey Analytics
description: Obtenga información acerca de los métodos alternativos al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 9%

---

# Alternativa de actualización: Envíe la capa de datos a Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Envío de la capa de datos a Adobe"
>abstract="En lugar de enviar datos a través de un objeto XDM, puede enviar toda la capa de datos a Adobe a través del objeto de datos.<br><br>Esta opción ahorra tiempo de implementación al permitirle asignar la capa de datos a XDM, en lugar de rellenar un objeto XDM desde cero. Sin embargo, esta asignación supone una gran cantidad de trabajo porque habrá una cantidad significativa de datos que Adobe no puede interpretar fácilmente. Esta opción también introduce una complejidad adicional a lo largo del tiempo, ya que cualquier campo que añada a los datos más adelante debe asignarse a XDM en la secuencia de datos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="Envío de la capa de datos a Adobe"
>abstract="Configure la implementación para enviar datos a Adobe en el momento deseado y configure la carga útil JSON para que sea la capa de datos en su totalidad."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="Asignar cada elemento de capa de datos al XDM"
>abstract="Asigne cada elemento de capa de datos al campo XDM deseado. Los elementos de capa de datos que no estén asignados a un campo XDM se pierden de forma permanente, ya que Adobe no sabe dónde ni cómo almacenar esos datos."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use la información de esta página para responder preguntas en la [lista de comprobación de actualización de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Al actualizar a Customer Journey Analytics, Adobe [recomienda una nueva implementación de Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Sin embargo, dependiendo de varios factores, como el calendario y las restricciones de recursos, los pasos de actualización recomendados podrían no ser prácticos para su organización.

Puede enviar toda la capa de datos a Customer Journey Analytics en lugar de recopilar datos con el objeto XDM. Sin embargo, esta alternativa introduce una complejidad adicional a lo largo del tiempo.

## Ventajas y desventajas

Este método se excluye mutuamente con [usando la lógica de recopilación de datos de AppMeasurement con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), ya que ambos métodos realizan la misma tarea.

A continuación se indican las ventajas y desventajas de utilizar esta alternativa de actualización:

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>**Ofrece todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas son:</p><ul><li>Informes de alto rendimiento y disponibilidad de datos porque Adobe Experience Platform se ha creado para potenciar [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Utiliza la lógica actual de la capa de datos**: Este método usa la lógica actual de la capa de datos en lugar de una implementación convencional de Web SDK. Aunque este método requiere cierta configuración, no requiere una implementación completamente nueva desde cero y no requiere rellenar elementos de datos o reglas de etiquetas. Permite asignar datos de la capa de datos a XDM, en lugar de rellenar un objeto XDM desde cero.</li></ul> | <ul><li>**Requiere asignación para enviar datos a la plataforma**: cuando su organización esté lista para usar Customer Journey Analytics, debe enviar datos a un conjunto de datos en Adobe Experience Platform. <p>Dado que esta opción le permite colocar toda la capa de datos del lado del cliente en el objeto de datos y enviarlo a Adobe, el resultado es una cantidad significativa de datos que Adobe no puede interpretar fácilmente. Para permitir que Adobe interprete los datos, debe utilizar la asignación de secuencia de datos para asignar cada campo individual al campo XDM deseado.</p></li><li>**Implementación rígida**: La implementación está restringida a lo que proporciona la capa de datos en el momento en que se envía la visita. Esto puede ser aceptable para organizaciones con necesidades de datos básicas, pero la mayoría de las organizaciones deben evitar este tipo de implementación rígida en favor de una implementación más flexible que permita rellenar los elementos de datos.</li><li>**Es más difícil implementar futuros cambios**: cualquier campo que agregue a los datos más adelante debe asignarse a XDM en la secuencia de datos.</li></ul> |

{style="table-layout:auto"}

## Pasos básicos

Los pasos básicos para enviar toda la capa de datos a Customer Journey Analytics son los siguientes:

1. Configure la implementación para enviar datos a Adobe en el momento deseado y configure la carga útil JSON para que sea la capa de datos en su totalidad.

1. Asigne cada elemento de capa de datos al campo XDM deseado.

   Los elementos de capa de datos que no estén asignados a un campo XDM se pierden de forma permanente, ya que Adobe no sabe dónde ni cómo almacenar esos datos.



