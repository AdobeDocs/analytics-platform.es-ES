---
title: Diseño de su esquema para utilizarlo con Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 26%

---

# Diseño de su esquema para utilizarlo con Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Diseño de un esquema"
>abstract="Analice en su organización los requisitos de la recopilación de datos y determine cómo desea crear un esquema para utilizarlo en Adobe Experience Platform. Este paso aparece porque desea utilizar el proceso recomendado de usar un esquema adaptado a su organización. Realizar este paso correctamente es fundamental, ya que un esquema con el que se alineen todos los equipos de la organización facilita considerablemente la ingesta de datos.<br><br>El tiempo estimado para reunir a todas las partes relevantes de su organización para alinearse en un esquema unificado es de 1 a 2 meses. Este lapso de tiempo depende en gran medida del número de equipos que haya que coordinar y del número de dimensiones + métricas que haya que alinear."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe recomienda crear un esquema XDM (Experience Data Model) personalizado para utilizarlo con Web SDK al actualizar de Adobe Analytics a Customer Journey Analytics. También puede utilizar el esquema de Adobe Analytics predeterminado, que utiliza el grupo de campos Adobe Analytics ExperienceEvent.

Un esquema XDM personalizado permite un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza. A diferencia del esquema de Adobe Analytics predeterminado que utiliza el grupo de campos Adobe Analytics ExperienceEvent, cuando se requieren cambios en un esquema XDM personalizado, no es necesario revisar miles de campos no utilizados para encontrar el campo que requiere actualización.

Para obtener más información sobre estas opciones de esquema, consulte [Elegir el esquema para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Revise las siguientes secciones a medida que empiece a crear el esquema XDM.

## Evite las restricciones de Adobe Analytics en el esquema XDM

La arquitectura subyacente de Customer Journey Analytics proporciona mucha más flexibilidad que Adobe Analytics. La creación de un nuevo esquema XDM es una forma clave de desbloquear esa flexibilidad. Cuando actualice a Customer Journey Analytics, asegúrese de evitar transferir restricciones de Adobe Analytics innecesarias al esquema.

>[!NOTE]
>
>La siguiente información aún no está completa. Se completará en un futuro próximo.

| Arquitectura de datos de Adobe Analytics | Arquitectura de esquema XDM |
|---------|----------|
| Las métricas individuales se añaden a la arquitectura de datos de Analytics.<br/>Por ejemplo, en Adobe Analytics, tiene un eVar diferente para cada evento. | Cree métricas individuales en la vista de datos en lugar de en el esquema XDM. Al hacerlo, se proporciona más flexibilidad en si necesita realizar cambios más adelante.<br/>Por ejemplo, en Customer Journey Analytics, tiene un solo evento en el esquema y utiliza crear eventos en la vista de datos. |
| Se requieren props y eVars para crear variables personalizadas. |  |

## Identifique a su equipo de datos y a otras partes interesadas de su organización

>[!NOTE]
>
>Esta información aún no está disponible. Estará disponible en un futuro próximo.

## Considere otras aplicaciones de Adobe Experience Platform utilizadas en su organización

>[!NOTE]
>
>Esta información aún no está disponible. Estará disponible en un futuro próximo.
