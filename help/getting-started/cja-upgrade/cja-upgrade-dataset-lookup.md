---
title: Crear un esquema para el Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Crear conjuntos de datos de búsqueda para clasificar datos en Customer Journey Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

De forma similar a los datos de clasificaciones en Adobe Analytics, los conjuntos de datos de búsqueda son el método para clasificar datos en Customer Journey Analytics.

Al utilizar el conector de origen de Analytics, algunos conjuntos de datos de búsqueda estándar se aplican automáticamente en el momento del informe. Para obtener más información, consulte [Agregar búsquedas estándar a sus conjuntos de datos](/help/connections/standard-lookups.md).

Para clasificar los datos con una nueva implementación del SDK web de Experience Platform, debe crear un conjunto de datos de búsqueda para cada dimensión que contenga los datos que desea clasificar.

Para crear conjuntos de datos de búsqueda para utilizarlos en el Customer Journey Analytics:

1. En AEP, cree un nuevo esquema. Este es un nuevo esquema específico para los conjuntos de datos de búsqueda. No se puede utilizar un esquema existente.

1. Debe crear una nueva clase de esquema que sea para búsquedas.

1. Cree un conjunto de datos de búsqueda a partir de eso.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).
