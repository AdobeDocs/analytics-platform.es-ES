---
title: Creación del conector de origen de Analytics y campos de asignación
description: Obtenga información sobre cómo crear el conector de origen de Analytics y asignar campos
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 3%

---

# Creación del conector de origen de Analytics y campos de asignación

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Puede utilizar el conector de origen de Analytics para incorporar datos del grupo de informes de Adobe Analytics a Adobe Experience Platform. Estos datos se pueden utilizar como datos históricos en Customer Journey Analytics.

Los siguientes pasos dan por sentado que desea [crear un esquema XDM al actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), ya que desea un esquema optimizado que se adapte a las necesidades de su organización y a las aplicaciones específicas de Platform que utiliza.

Con el esquema XDM creado, debe crear el conector de origen de Adobe Analytics para utilizarlo con los datos históricos.

Para obtener instrucciones generales más completas sobre cómo crear un conector de origen, consulte [Crear una conexión de origen de Adobe Analytics en la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es).

Para crear un conector de origen de Adobe Analytics para utilizarlo con datos históricos:

1. En la interfaz de usuario de Platform, en la sección **[!UICONTROL Conexiones]** del carril izquierdo, seleccione **[!UICONTROL Fuentes]**.

1. Seleccione **[!UICONTROL Aplicaciones de Adobe]** en la lista de [!UICONTROL CATEGORÍAS].

1. Seleccione **[!UICONTROL Agregar datos]** en el mosaico de Adobe Analytics.

   ![Ventana de Adobe Experience Platform con orígenes seleccionados junto con aplicaciones de Adobe y Agregar datos resaltados.](./assets/sources-overview.png)

1. Seleccione **[!UICONTROL Grupo de informes]** y, a continuación, en la lista de grupos de informes, seleccione el grupo de informes que contiene los datos históricos que desea utilizar en Customer Journey Analytics.

   ![Ventana de Adobe Experience Platform que muestra la lista de grupos de informes](./assets/report-suites.png)

1. Seleccione **[!UICONTROL Siguiente]** en la esquina superior derecha de la pantalla.

1. Seleccione **[!UICONTROL Esquema personalizado]** y, a continuación, seleccione el esquema que creó en [Crear un esquema XDM que incluya el grupo de campos Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md). <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Asigne cada dimensión de Adobe Analytics a una dimensión de esquema XDM personalizada.

   1. En la sección **[!UICONTROL Asignar campos estándar]**, seleccione la pestaña **[!UICONTROL Personalizado]**.

   1. Seleccione **[!UICONTROL Agregar nueva asignación]**.

   ![asignar campos de esquema](assets/schema-mapping.png)

   1. En el **[!UICONTROL campo Source]**, seleccione un campo Adobe Analytics del grupo de campos Plantilla de Adobe Analytics ExperienceEvent. A continuación, en el **[!UICONTROL campo de destino]**, seleccione el campo XDM al que desea asignarlo.

   1. Repita este proceso para cada campo del grupo de campos Plantilla de Adobe Analytics ExperienceEvent que esté utilizando para recopilar datos en Adobe Analytics.

1. Seleccione **[!UICONTROL Siguiente]** en la esquina superior derecha de la pantalla.

1. Asigne un nombre al flujo de datos y (opcionalmente) proporcione una descripción.

   ![Ventana de Adobe Experience Platform que resalta la sección de detalles del flujo de datos](./assets/dataflow-detail.png)

1. Seleccione **[!UICONTROL Siguiente]** en la esquina superior derecha de la pantalla.

1. Revise la conexión y, a continuación, seleccione **[!UICONTROL Finalizar]**.

   ![Ventana de Adobe Experience Platform que resalta las secciones Tipo de datos y Conexión para su revisión](./assets/review.png)

   Una vez creada la conexión, el flujo de datos se crea automáticamente para rellenar un conjunto de datos con los datos de Adobe Analytics del grupo de informes. El flujo de datos ingiere hasta 13 meses de datos históricos para las zonas protegidas de producción. El relleno en zonas protegidas que no sean de producción está limitado a tres meses.

   Si utiliza el conector de origen de Analytics para incorporar datos históricos a la implementación del SDK web de Customer Journey Analytics, debe agregar este conjunto de datos creado automáticamente a la conexión que creó para la implementación del SDK web.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).




