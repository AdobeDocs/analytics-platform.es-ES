---
title: Cambio del conector de origen de Analytics al SDK web para Customer Journey Analytics
description: Obtenga información sobre cómo pasar al SDK web desde el conector de origen de Analytics al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: a1feb2e8458169ed208da2c42fab62d25e1015bb
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# Cambio del conector de origen de Analytics al SDK web para Customer Journey Analytics

>[!NOTE]
> 
>Use la información de esta página para responder preguntas en la [lista de comprobación de actualización de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

El uso del conector de origen de Analytics como única implementación para Customer Journey Analytics presenta desventajas inherentes. Si su organización ya ha actualizado a Customer Journey Analytics utilizando solo la implementación del conector de origen de Analytics, debe considerar pasar a una implementación del SDK web.

El Adobe recomienda utilizar el conector de origen de Analytics (para transmitir datos históricos), junto con una nueva implementación del SDK web (para la recopilación continua de datos).

## Comprenda las ventajas y desventajas de utilizar el conector de origen de Analytics exclusivamente

Para obtener información acerca de las ventajas y desventajas de usar el conector de origen de Analytics, vea [Usar el conector de origen de Analytics exclusivamente para actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Cambio del conector de origen de Analytics al SDK web

A continuación se muestra un proceso de alto nivel para pasar del conector de origen de Analytics a una implementación compuesta tanto por el conector de origen de Analytics como por una implementación de SDK web:

1. Cree una implementación de SDK web, tal como se describe en [Pasos detallados de la actualización recomendada](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) en el artículo [Actualizar de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Una vez configurada la implementación del SDK web, continúe con los siguientes pasos.

1. Decida si utilizará el esquema de Adobe Analytics o un esquema XDM en la implementación del SDK web.

   Para obtener más información, consulte [Elegir el esquema para el Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

1. (Condicional) Si planea utilizar el esquema de Adobe Analytics con la implementación del SDK web, agregue el conjunto de datos creado automáticamente por el conector de origen de Analytics a la conexión de Customer Journey Analytics.

   Para obtener más información, consulte [Agregar el conjunto de datos del conector de origen de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condicional) Si planea crear un esquema XDM para utilizarlo con la implementación del SDK web:

   1. [Cree un esquema XDM para el conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. Agregue el conjunto de datos que se creó automáticamente con el conector de origen original de Analytics a la conexión de Customer Journey Analytics.

      Para obtener más información, consulte [Agregar el conjunto de datos desde el conector de origen actual de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

   1. Elimine el conector de origen original de Analytics. <!-- need to add steps somewhere about how to do this -->

   1. [Cree un nuevo conector de origen de Analytics y asigne campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
