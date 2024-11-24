---
title: Arquitectura del esquema para su uso con Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 7%

---

# Arquitectura del esquema para su uso con Customer Journey Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Adobe recomienda crear un esquema del Modelo de datos de experiencia (XDM) al actualizar a Customer Journey Analytics. Un esquema XDM permite un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza. Cuando es necesario realizar cambios en el esquema, no es necesario rebuscar entre miles de campos no utilizados para encontrar el campo que requiere actualización.

Revise las siguientes secciones a medida que empiece a crear el esquema XDM.

## Evite las restricciones de Adobe Analytics en el esquema XDM

La arquitectura subyacente de Customer Journey Analytics proporciona mucha más flexibilidad que Adobe Analytics. La creación de un nuevo esquema XDM es una forma clave de desbloquear esa flexibilidad. Cuando actualice a Customer Journey Analytics, asegúrese de evitar transferir restricciones de Adobe Analytics innecesarias al esquema.

| Arquitectura de datos de Adobe Analytics | Arquitectura de esquema XDM |
|---------|----------|
| Las métricas individuales se añaden a la arquitectura de datos de Analytics.<br/>Por ejemplo, en Adobe Analytics, tiene un eVar diferente para cada evento. | Cree métricas individuales en la vista de datos en lugar de en el esquema XDM. Al hacerlo, se proporciona más flexibilidad en si necesita realizar cambios más adelante.<br/>Por ejemplo, en Customer Journey Analytics, tiene un solo evento en el esquema y utiliza crear eventos en la vista de datos. |
| Se requieren props y eVars para crear variables personalizadas. | B2 |
| A3 | B3 |

## Identifique a su equipo de datos y a otras partes interesadas de su organización


## Considere otras aplicaciones de Adobe Experience Platform utilizadas en su organización



1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).
