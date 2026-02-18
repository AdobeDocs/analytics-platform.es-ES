---
title: Creación de un esquema personalizado para el conector de origen de Analytics
description: Obtenga información sobre cómo crear un esquema personalizado para el conector de origen de Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Creación de un esquema personalizado para el conector de origen de Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Creación de un esquema para el conector de origen de Analytics"
>abstract="Este esquema es una combinación del grupo de campos ExperienceEvent de Adobe Analytics con todos los grupos de campos que conforman el esquema personalizado de su organización. Le permite asignar los campos utilizados por el conector de origen de Analytics al esquema de su organización y solo se utiliza para los datos históricos.<br><br>Aunque de naturaleza técnica, la creación de este esquema se puede completar en horas, posiblemente más rápido si sabe exactamente qué grupos de campos conforman el esquema personalizado de su organización."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="Creación del conector de origen de Analytics para datos históricos"
>abstract="Puede utilizar el conector de origen de Analytics para incorporar datos del grupo de informes de Adobe Analytics a Adobe Experience Platform. A continuación, estos datos se pueden utilizar como datos históricos en Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Descubra cómo el conector de origen de Analytics puede aportar datos históricos a Customer Journey Analytics

Puede utilizar el conector de origen de Analytics para incorporar datos del grupo de informes de Adobe Analytics a Adobe Experience Platform. A continuación, estos datos se pueden utilizar como datos históricos en Customer Journey Analytics.

Este proceso supone que desea [crear un esquema personalizado para utilizarlo con su implementación del SDK web de Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), porque desea un esquema optimizado que se adapte a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza.

Para utilizar el conector de origen de Analytics para introducir datos históricos en Customer Journey Analytics, debe:

1. Cree un esquema personalizado para el conector de origen de Analytics, tal como se describe a continuación.

1. Si todavía no tiene un conector de origen de Analytics, [deberá crearlo y asignar los campos a su esquema personalizado](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   O bien

   Si ya tiene un conector de origen de Analytics, [asigne campos del conector de origen al esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Adición del conjunto de datos del conector de origen de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Creación de un esquema personalizado para el conector de origen de Analytics

Ya debería haber [creado un nuevo esquema personalizado](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) para su implementación del SDK de Experience Platform para utilizarlo con Customer Journey Analytics. Este esquema debe contener los grupos de campos correspondientes a los campos sobre los que tiene previsto recopilar datos.

Ahora debe utilizar esos mismos grupos de campos del esquema del SDK web y añadirlos a un nuevo esquema que puede utilizar con el conector de origen de Analytics.

Este esquema para el conector de origen de Analytics debe contener:

* Todos los grupos de campos (incluidos los grupos de campos personalizados que haya creado) incluidos en el esquema personalizado que haya creado para la implementación del SDK web. (Todos los campos personalizados que no formen parte de un grupo de campos predeterminado deberían haberse añadido al esquema del SDK web como parte de un grupo de campos personalizados).

* El grupo de campos Plantilla de Adobe Analytics ExperienceEvent 

Para crear el esquema personalizado que se utilizará con el conector de origen de Analytics:

1. En Adobe Experience Platform, empiece a crear un nuevo esquema personalizado tal como se describe en [Creación de un esquema personalizado para utilizarlo con su implementación del SDK web](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Añada todos los grupos de campos (incluidos los grupos de campos personalizados) incluidos en el esquema creado para la implementación del SDK web.

1. Cuando termine de añadir estos grupos de campos, añada el grupo de campos Adobe Analytics ExperienceEvent:

   En la sección **[!UICONTROL Grupos de campos]**, seleccione **[!UICONTROL Agregar]** para añadir un grupo de campos adicional.

   ![Añadir un grupo de campos al esquema](assets/schema-add-field-group.png)

1. Busque y seleccione el grupo de campos **[!UICONTROL Plantilla de Adobe Analytics ExperienceEvent]**.

   ![Añadir el grupo de campos Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Seleccione **[!UICONTROL Agregar grupos de campos]**.

1. Seleccione **[!UICONTROL Guardar]** para guardar el esquema.

{{upgrade-final-step}}
