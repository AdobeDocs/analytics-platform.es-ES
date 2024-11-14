---
title: Creación de un esquema XDM para el conector de origen de Analytics
description: Obtenga información sobre cómo crear un esquema XDM para el conector de origen de Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Creación de un esquema XDM para el conector de origen de Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Ya debería haber [creado un nuevo esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) para la implementación del SDK web de Experience Platform para utilizarlo con Customer Journey Analytics. Este esquema debe contener cualquier grupo de campos para los campos en los que planee recopilar datos.

Además del esquema XDM ya creado para la implementación del SDK web, ahora debe crear un segundo esquema XDM para utilizarlo con el conector de origen de Analytics para llevar los datos históricos a Customer Journey Analytics.

Este segundo esquema debe contener:

* Todos los grupos de campos (incluidos los grupos de campos personalizados) que se incluyen en el esquema creado para la implementación del SDK web. (Todos los campos personalizados que no formen parte de un grupo de campos predeterminado deberían haberse agregado al esquema del SDK web como parte de un grupo de campos personalizados).

* El grupo de campos Plantilla de Adobe Analytics ExperienceEvent

Para crear el esquema XDM para utilizarlo con el conector de origen de Analytics:

1. En Adobe Experience Platform, empiece a crear un nuevo esquema XDM como se describe en [Crear un esquema XDM para utilizarlo con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Añada todos los grupos de campos (incluidos los grupos de campos personalizados) que se incluyen en el esquema creado para la implementación del SDK web.

1. Cuando termine de agregar estos grupos de campos, agregue el grupo de campos Adobe Analytics ExperienceEvent:

   En la sección **[!UICONTROL Grupos de campos]**, seleccione **[!UICONTROL Agregar]** para agregar un grupo de campos adicional.

   ![Agregar grupo de campos al esquema](assets/schema-add-field-group.png)

1. Busque y seleccione el grupo de campos **[!UICONTROL Plantilla de Adobe Analytics ExperienceEvent]**.

   ![Agregar el grupo de campos Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Seleccione **[!UICONTROL Agregar grupos de campos]**.

1. Seleccione **[!UICONTROL Guardar]** para guardar el esquema.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).

