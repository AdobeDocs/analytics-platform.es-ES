---
title: Transición del conector de origen de Analytics a Web SDK para Customer Journey Analytics
description: Obtenga información sobre cómo realizar la transición a Web SDK desde el conector de origen de Analytics al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Transición del conector de origen de Analytics a Web SDK para Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Implementación del conector de origen de Analytics"
>abstract="El conector de origen de Analytics le permite obtener fácilmente valor de Customer Journey Analytics, pero requiere que pague tanto por Adobe Analytics como por Customer Journey Analytics. Esta guía puede ayudarle a pasar a una implementación independiente de Web SDK."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use la información de esta página para responder preguntas en la [lista de comprobación de actualización de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

El uso del conector de origen de Analytics como única implementación para Customer Journey Analytics presenta desventajas inherentes.

Si su organización ya se ha actualizado a Customer Journey Analytics utilizando solo la implementación del conector de origen de Analytics, Adobe recomienda realizar la transición a una implementación que utilice el conector de origen de Analytics (para datos históricos), junto con una nueva implementación de Web SDK (para la recopilación continua de datos).

## Comprenda las ventajas y desventajas de utilizar el conector de origen de Analytics exclusivamente

Para obtener información acerca de las ventajas y desventajas de usar el conector de origen de Analytics, vea [Usar el conector de origen de Analytics exclusivamente para actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Transición del conector de origen de Analytics a Web SDK

A continuación se muestra un proceso de alto nivel para la transición de utilizar exclusivamente el conector de origen de Analytics a una implementación compuesta tanto por el conector de origen de Analytics como por una implementación de Web SDK:

1. Cree una implementación de Web SDK, tal como se describe en [Pasos detallados de la actualización recomendada](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) en el artículo [Actualizar de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Una vez configurada la implementación de Web SDK, continúe con los siguientes pasos.

1. [Cree un esquema XDM para el conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Asigne cada dimensión de Adobe Analytics desde el conector de origen de Analytics a la dimensión del esquema de Web SDK.

   1. 
      <!-- how do you get here -->

   1. En la sección **[!UICONTROL Asignar campos estándar]**, seleccione la pestaña **[!UICONTROL Personalizado]**.

   1. Seleccione **[!UICONTROL Agregar nueva asignación]**.

      ![asignar campos de esquema](assets/schema-mapping.png)

   1. En el **[!UICONTROL campo Source]**, seleccione un campo Adobe Analytics del grupo de campos Plantilla de Adobe Analytics ExperienceEvent. A continuación, en el **[!UICONTROL campo de destino]**, seleccione el campo XDM al que desea asignarlo.

   1. Repita este proceso para cada campo del grupo de campos Plantilla de Adobe Analytics ExperienceEvent que esté utilizando para recopilar datos en Adobe Analytics.

1. Agregue el conjunto de datos que se creó automáticamente con el conector de origen original de Analytics a la conexión de Customer Journey Analytics.

   Para obtener más información, consulte [Agregar el conjunto de datos desde el conector de origen actual de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condicional) Si utiliza conjuntos de datos de búsqueda, debe crear el conjunto de datos de búsqueda y agregarlo a la conexión. Para obtener más información, consulte [Crear conjuntos de datos de búsqueda para clasificar datos en el Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Elimine el conector de origen original de Analytics. <!-- need to add steps somewhere about how to do this -->

1. [Cree un nuevo conector de origen de Analytics y asigne campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
