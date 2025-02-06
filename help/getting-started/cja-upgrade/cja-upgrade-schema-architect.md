---
title: Arquitectura del esquema para su uso con Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Arquitectura del esquema para su uso con Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Arquitecto de un esquema"
>abstract="Analice en su organización los requisitos de la recopilación de datos y determine cómo desea crear un esquema para utilizarlo en Adobe Experience Platform. Este paso aparece porque desea utilizar el proceso recomendado de usar un esquema adaptado a su organización. Realizar este paso correctamente es fundamental, ya que un esquema en el que se alineen todos los equipos de la organización facilita considerablemente la ingesta de datos.<br><br>El tiempo estimado para reunir a todas las partes relevantes de su organización para alinearse en un esquema unificado es de 1 a 2 meses. Este lapso de tiempo depende en gran medida del número de equipos necesarios para la coordinación y del número de dimensiones + métricas con las que se deba alinear."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Adobe recomienda crear un esquema de modelo de datos de experiencia (XDM) personalizado para utilizarlo con Web SDK al actualizar de Adobe Analytics a Customer Journey Analytics. También puede utilizar el esquema de Adobe Analytics predeterminado, que utiliza el grupo de campos Adobe Analytics ExperienceEvent.

Un esquema XDM personalizado permite un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza. A diferencia del esquema de Adobe Analytics predeterminado que utiliza el grupo de campos Adobe Analytics ExperienceEvent, cuando se requieren cambios en un esquema XDM personalizado, no es necesario revisar miles de campos no utilizados para encontrar el campo que requiere actualización.

Para obtener más información acerca de estas opciones de esquema, vea [Elegir el esquema para el Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

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
