---
title: Creación de un esquema personalizado para el conector de origen de Analytics
description: Obtenga información sobre cómo crear un esquema personalizado para el conector de origen de Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 45f2097d2f0657f623b825acb8d06ec6972f757f
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 3%

---

# Creación de un esquema personalizado para el conector de origen de Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

## Descubra cómo el conector de origen de Analytics puede llevar datos históricos a Customer Journey Analytics

Puede utilizar el conector de origen de Analytics para incorporar datos del grupo de informes de Adobe Analytics a Adobe Experience Platform. Estos datos se pueden utilizar como datos históricos en Customer Journey Analytics.

Este proceso supone que desea [crear un esquema personalizado para utilizarlo con la implementación del SDK web de Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), ya que desea un esquema optimizado que se adapte a las necesidades de su organización y a las aplicaciones específicas de Platform que utiliza.

Para utilizar el conector de origen de Analytics para llevar los datos históricos a Customer Journey Analytics, debe:

1. Cree un esquema personalizado para el conector de origen de Analytics, como se describe a continuación.

1. Si todavía no tiene un conector de origen de Analytics, [cree el conector de origen de Analytics y asigne campos a su esquema personalizado](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   O

   Si ya tiene un conector de origen de Analytics, [asigne campos del conector de origen al esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Adición del conjunto de datos del conector de origen de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Creación de un esquema personalizado para el conector de origen de Analytics

Ya debería haber [creado un nuevo esquema personalizado](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) para la implementación del SDK web de Experience Platform para utilizarlo con Customer Journey Analytics. Este esquema debe contener cualquier grupo de campos para los campos en los que planee recopilar datos.

Ahora debe utilizar esos mismos grupos de campos del esquema del SDK web y agregarlos a un nuevo esquema que pueda utilizar con el conector de origen de Analytics.

Este esquema para el conector de origen de Analytics debe contener:

* Todos los grupos de campos (incluidos los grupos de campos personalizados que haya creado) que se incluyen en el esquema personalizado que ha creado para la implementación del SDK web. (Todos los campos personalizados que no formen parte de un grupo de campos predeterminado deberían haberse agregado al esquema del SDK web como parte de un grupo de campos personalizados).

* El grupo de campos Plantilla de Adobe Analytics ExperienceEvent

Para crear el esquema personalizado que se utilizará con el conector de origen de Analytics:

1. En Adobe Experience Platform, empiece a crear un nuevo esquema personalizado como se describe en [Cree un esquema personalizado para utilizarlo con la implementación del SDK web de Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Añada todos los grupos de campos (incluidos los grupos de campos personalizados) que se incluyen en el esquema creado para la implementación del SDK web.

1. Cuando termine de agregar estos grupos de campos, agregue el grupo de campos Adobe Analytics ExperienceEvent:

   En la sección **[!UICONTROL Grupos de campos]**, seleccione **[!UICONTROL Agregar]** para agregar un grupo de campos adicional.

   ![Agregar grupo de campos al esquema](assets/schema-add-field-group.png)

1. Busque y seleccione el grupo de campos **[!UICONTROL Plantilla de Adobe Analytics ExperienceEvent]**.

   ![Agregar el grupo de campos Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Seleccione **[!UICONTROL Agregar grupos de campos]**.

1. Seleccione **[!UICONTROL Guardar]** para guardar el esquema.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).