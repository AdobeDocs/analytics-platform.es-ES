---
title: Creación del conector de origen de Analytics y asignación de campos
description: Obtenga más información sobre cómo crear el conector de origen de Analytics y los campos de asignación
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '745'
ht-degree: 100%

---

# Creación del conector de origen de Analytics y asignación de campos {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="Cree el conector de origen de Analytics"
>abstract="Utilice el conector de origen de Analytics para introducir datos del grupo de informes y utilizarlos en Customer Journey Analytics.<br><br>La creación del conector de origen de Analytics solo lleva unos minutos con la configuración predeterminada."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="Creación del conector de origen de Analytics y asignación de campos"
>abstract="El conector de origen necesita saber cómo asignar campos de Adobe Analytics al esquema de la organización. Utilice esta interfaz para proporcionar al conector de origen esa asignación. Este paso forma parte de la adición de datos históricos a Customer Journey Analytics.<br><br>El tiempo que tarda este paso depende en gran medida del número de dimensiones y métricas que debe asignar. Este paso no es tan difícil, pero es tedioso y repetitivo. La previsión es que la asignación de la secuencia de datos tarde aproximadamente una semana en completarse."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Descubra cómo el conector de origen de Analytics puede aportar datos históricos a Customer Journey Analytics

Puede utilizar el conector de origen de Analytics para incorporar datos del grupo de informes de Adobe Analytics a Adobe Experience Platform. A continuación, estos datos se pueden utilizar como datos históricos en Customer Journey Analytics.

Este proceso supone que desea [crear un esquema personalizado para utilizarlo con su implementación del SDK web de Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), porque desea un esquema optimizado que se adapte a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza.

Para utilizar el conector de origen de Analytics para introducir datos históricos en Customer Journey Analytics, debe:

1. [Creación de un esquema personalizado para el conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Si todavía no tiene un conector de origen de Analytics, deberá crearlo y asignar campos al esquema del SDK web personalizado como se describe a continuación.

   O bien

   Si ya tiene un conector de origen de Analytics, [asigne campos del conector de origen al esquema personalizado del SDK web](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Adición del conjunto de datos del conector de origen de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Creación del conector de origen de Analytics y asignación de campos

Con el esquema personalizado creado, debe crear el conector de origen de Adobe Analytics para utilizarlo con los datos históricos. (Para obtener instrucciones generales más completas sobre cómo crear un conector de origen, consulte [Creación de una conexión de origen de Adobe Analytics en la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es)).

Para crear un conector de origen de Adobe Analytics para utilizarlo para los datos históricos:

1. En la interfaz de usuario de Platform, en la sección **[!UICONTROL Conexiones]** del carril izquierdo, seleccione **[!UICONTROL Fuentes]**.

1. Seleccione **[!UICONTROL Aplicaciones de Adobe]** en la lista de [!UICONTROL CATEGORÍAS].

1. Seleccione **[!UICONTROL Añadir datos]** en el mosaico de Adobe Analytics.

   ![Ventana de Adobe Experience Platform con la opción Fuentes seleccionada junto con las aplicaciones de Adobe y la opción Añadir datos resaltada.](./assets/sources-overview.png)

1. Seleccione **[!UICONTROL Grupo de informes]** y, a continuación, en la lista de grupos de informes, seleccione el grupo de informes que contiene los datos históricos que desea utilizar en Customer Journey Analytics.

   ![Ventana de Adobe Experience Platform que muestra la lista de grupos de informes](./assets/report-suites.png)

1. Seleccione **[!UICONTROL Siguiente]** en la esquina superior derecha de la pantalla.

1. Seleccione **[!UICONTROL Esquema personalizado]** y, a continuación, seleccione el esquema que creó en [Crear un esquema personalizado que incluya el grupo de campos de Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md). <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Asigne cada dimensión de Adobe Analytics a una dimensión de esquema personalizada.

   1. En la sección **[!UICONTROL Asignar campos estándar]**, seleccione la pestaña **[!UICONTROL Personalizado]**.

   1. Seleccione **[!UICONTROL Añadir nueva asignación]**.

   ![asignar campos del esquema](assets/schema-mapping.png)

   1. En el **[!UICONTROL campo de origen]**, seleccione un campo de Adobe Analytics del grupo de campos Plantilla de Adobe Analytics ExperienceEvent. A continuación, en el **[!UICONTROL campo de destino]**, seleccione el campo personalizado en el esquema XDM al que desea asignarlo.

      No todos los campos de Adobe Analytics tienen un campo correspondiente en XDM debido a las diferencias de arquitectura inherentes entre AppMeasurement y XDM.

   1. Repita este proceso para cada campo del grupo de campos Plantilla de Adobe Analytics ExperienceEvent que esté utilizando para recopilar datos en Adobe Analytics.

1. Seleccione **[!UICONTROL Siguiente]** en la esquina superior derecha de la pantalla.

1. Asigne un nombre al flujo de datos y (opcionalmente) proporcione una descripción.

   ![Ventana de Adobe Experience Platform que resalta la sección de detalles del flujo de datos](./assets/dataflow-detail.png)

1. Seleccione **[!UICONTROL Siguiente]** en la esquina superior derecha de la pantalla.

1. Revise la conexión y a continuación, seleccione **[!UICONTROL Finalizar]**.

   ![Ventana de Adobe Experience Platform que resalta las secciones Conexión y Tipo de datos para su revisión](./assets/review.png)

   Una vez creada la conexión, el flujo de datos se crea automáticamente para rellenar un conjunto de datos con los datos de Adobe Analytics del grupo de informes. El flujo de datos ingiere hasta 13 meses de datos históricos para las zonas protegidas de producción. El relleno en zonas protegidas que no son de producción está limitado a tres meses.

   Si utiliza el conector de origen de Analytics para incorporar datos históricos a la implementación del SDK web de Customer Journey Analytics, deberá añadir este conjunto de datos creado automáticamente a la conexión que creó para la implementación del SDK web.

{{upgrade-final-step}}
