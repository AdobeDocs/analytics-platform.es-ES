---
title: Crear un esquema personalizado para Customer Journey Analytics
description: Obtenga información sobre cómo crear un esquema personalizado para Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Creación de un esquema personalizado para utilizarlo con Customer Journey Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create"
>title="Cree el esquema personalizado deseado en Adobe Experience Platform"
>abstract="Utilice la interfaz de usuario de Adobe Experience Platform para crear un esquema para que Adobe conozca el formato correcto para almacenar los datos.<br><br>Este paso implica crear realmente el esquema acordado por su organización. El tiempo estimado para crear el esquema en la interfaz de Adobe Experience Platform es de aproximadamente una semana, según el número de dimensiones y métricas que sea necesario crear."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create-default-aa"
>title="Crear un esquema utilizando el grupo de campos Adobe Analytics ExperienceEvent"
>abstract="Utilice el grupo de campos &quot;Adobe Analytics ExperienceEvent&quot; para crear un esquema en Adobe Experience Platform que contenga todos los campos utilizados por Adobe Analytics.<br><br>Crear un esquema basado en el grupo de campos Adobe Analytics ExperienceEvent es sencillo y tarda solo unos minutos en completarse."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-profile"
>title="Habilitar el esquema para el perfil"
>abstract="Habilite el perfil en su esquema para utilizarlo en Adobe Real-time CDP. Este paso aparece porque ha seleccionado el deseo de integrarse con Adobe Real-time CDP.<br><br>Dado que este paso implica hacer clic en un solo cuadro, este paso solo lleva unos minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

>[!IMPORTANT]
>
>Antes de empezar a crear el esquema personalizado, colabore con el equipo de datos y otras partes interesadas de toda la organización para identificar el diseño de esquema ideal de su organización y las demás aplicaciones de Adobe Experience Platform que utilice. Para obtener más información, consulte [Arquitectura del esquema para su uso con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

En las secciones siguientes se describe cómo crear un esquema que se puede utilizar con Customer Journey Analytics. Las opciones de esquema disponibles son las siguientes:

* **Esquema XDM personalizado** (recomendado) permite un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utilice. Cualquier cambio futuro requerido es sencillo.

* **El esquema de Adobe Analytics que usa el grupo de campos de Adobe Analytics ExperienceEvent:** requiere la adición de miles de campos innecesarios. Cualquier cambio futuro requerido es más difícil.

Para obtener más información sobre estas opciones de esquema, consulte [Elija su esquema para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

## Creación del esquema

El esquema personalizado que defina para la implementación del SDK web representa el modelo de los datos que se recopila en Adobe Experience Platform.

Para crear un esquema personalizado:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. En la interfaz de usuario de Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Esquemas]** en [!UICONTROL ADMINISTRACIÓN DE DATOS].

1. Seleccione **[!UICONTROL Crear esquema]**. 

1. En el paso **[!UICONTROL Seleccionar una clase]** del asistente Crear esquema:

   1. Seleccione **[!UICONTROL Evento de experiencia]**.

      ![Crear un esquema resaltando el evento de experiencia](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Se utiliza un esquema de evento de experiencia para modelar el _comportamiento_ de un perfil (como el nombre de escena, botón de comando para añadir al carro de compras). Se utiliza un esquema de perfil individual para modelar los atributos del perfil (como nombre, correo electrónico o género).__

   1. Seleccione **[!UICONTROL Siguiente]**.


1. En el [!UICONTROL paso Nombre y revisión] del asistente [!UICONTROL Crear esquema]:

   1. Introduzca un **[!UICONTROL Nombre para mostrar para el esquema]** para su esquema y (opcionalmente) una **[!UICONTROL Descripción]**.

      ![Ventana Crear esquema que muestra los campos de Nombre de su esquema](assets/create-ee-schema-wizard-step-2.png)

   1. Seleccione **[!UICONTROL Finalizar]**.

1. Añada todos los grupos de campos que contengan cualquier campo que desee incluir en el esquema.

   Los grupos de campos son colecciones reutilizables de objetos y atributos que le permiten ampliar fácilmente su esquema.

   1. En la sección **[!UICONTROL Grupos de campos]**, seleccione **[!UICONTROL + Agregar]**.

      ![Agregar grupo de campos](assets/add-field-group-button.png)

   1. En el cuadro de diálogo [!UICONTROL Agregar grupos de campos], seleccione el grupo de campos **[!UICONTROL ExperienceEvent del SDK web de AEP]** en la lista.

      ![Grupo de campos ExperienceEvent del SDK web de AEP](assets/select-aepwebsdk-experienceevent.png)

      Puede seleccionar el botón de vista previa para ver una vista previa de los campos que forman parte de este grupo de campos, como `web > webPageDetails > name`.

      ![Vista previa del grupo de campos ExperienceEvent del SDK web de AEP](assets/aepwebsdk-experiencevent-preview.png)

      Seleccione **[!UICONTROL Atrás]** para cerrar la vista previa.

   1. (Opcional) Seleccione los grupos de campos adicionales que desee incluir.

      Si decide utilizar el esquema de Adobe Analytics predeterminado en lugar de crear un esquema XDM personalizado, puede añadir ahora el grupo de campos Adobe Analytics ExperienceEvent. Sin embargo, Adobe recomienda crear un esquema XDM personalizado en lugar de añadir este grupo de campos.

      Para obtener más información sobre estas opciones de esquema, consulte [Elija su esquema para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

   1. Seleccione **[!UICONTROL Agregar grupos de campos]**.

1. (Opcional) Si tiene campos personalizados que desea incluir en el esquema, cree un grupo de campos personalizados y añádalos al grupo de campos.

   1. En la sección **[!UICONTROL Grupos de campos]**, seleccione **[!UICONTROL + Agregar]**.

      ![Agregar grupo de campos](assets/add-field-group-button.png)

   1. En el cuadro de diálogo [!UICONTROL Agregar grupos de campos], seleccione **[!UICONTROL Crear nuevo grupo de campos]**.

   1. Especifique un nombre para mostrar y una descripción opcional y, a continuación, seleccione **[!UICONTROL Agregar grupos de campos]**.

1. Seleccione **[!UICONTROL +]** junto al nombre del esquema en el panel [!UICONTROL Estructura].

   ![Ejemplo de botón para agregar campo de esquema](assets/example-schema-plus.png)

1. En el panel [!UICONTROL Propiedades de campo], introduzca `Identification` como nombre, **[!UICONTROL Identificación]** como [!UICONTROL Nombre para mostrar], seleccione **[!UICONTROL Objeto]** como [!UICONTROL Tipo] y seleccione **[!UICONTROL ExperienceEvent Core v2.1]** como [!UICONTROL Grupo de campos].

   >[!NOTE]
   >
   >Si ese grupo de campos no está disponible, busque otro que contenga campos de identidad. O bien [cree un nuevo grupo de campos](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=es) y [agregue nuevos campos de identidad](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=es#define-a-identity-field) (como `ecid`, `crmId` y otros que necesite) al grupo de campos y seleccione ese nuevo grupo de campos.

   ![Objeto de identificación](assets/identification-field.png)

   El objeto de identificación añade capacidades de identificación al esquema. En su caso, desea identificar los perfiles que visitan el sitio mediante Experience Cloud ID y la dirección de correo electrónico. Hay muchos otros atributos disponibles para realizar un seguimiento de la identificación de la persona (por ejemplo, ID de cliente o ID de lealtad).

   Seleccione **[!UICONTROL Aplicar]** para agregar este objeto al esquema.

1. Seleccione el campo **[!UICONTROL ECID]** en el objeto de identificación que acaba de agregar y seleccione **[!UICONTROL Identidad]**, **[!UICONTROL Identidad principal]** y **[!UICONTROL ECID]** en la lista de [!UICONTROL Espacio de nombres de identidad] en el panel derecho.

   ![Especificar ECID como identidad](./assets/specify-identity.png)

   Está especificando la identidad de Experience Cloud como la identidad principal que el servicio de identidad de Adobe Experience Platform puede utilizar para combinar (unir) el comportamiento de los perfiles con el mismo ECID.

   Seleccione **[!UICONTROL Aplicar]**. Verá que aparece un icono de huella digital en el atributo de ECID.

1. Seleccione el campo de **[!UICONTROL correo electrónico]** en el objeto de identificación que acaba de añadir y seleccione **[!UICONTROL Identidad]** y **[!UICONTROL Correo electrónico]** en la lista de [!UICONTROL Espacio de nombres de identidad] del panel [!UICONTROL Propiedades de campo].

   ![Especificar el correo electrónico como identidad](./assets/specify-email-identity.png)

   Está especificando la dirección de correo electrónico como otra identidad que el servicio de identidad de Adobe Experience Platform puede utilizar para combinar (unir) el comportamiento de los perfiles.

   Seleccione **[!UICONTROL Aplicar]**. Verá que aparece un icono de huella digital en el atributo de correo electrónico.

   Seleccione **[!UICONTROL Guardar]**.

1. (Opcional) Si desea integrar Customer Journey Analytics con RTCDP, seleccione el elemento raíz del esquema que muestra el nombre del esquema y, a continuación, seleccione el conmutador **[!UICONTROL Perfil]**.

   Se le pedirá que habilite el esquema para el perfil. Tras la habilitación, cuando los datos se incorporan en conjuntos de datos basados en este esquema, los datos se combinan en el perfil del cliente en tiempo real.

   Consulte [Habilitar el esquema para utilizarlo en el perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es#profile) para obtener más información.

   >[!IMPORTANT]
   >
   >Después de habilitar un esquema para el perfil, no se puede deshabilitar para el perfil.

   ![Habilitar esquema para perfil](./assets/enable-for-profile.png)

1. Seleccione **[!UICONTROL Guardar]** para guardar el esquema.

   Ha creado un esquema mínimo que modela los datos que puede capturar del sitio web. El esquema permite identificar perfiles mediante la identidad de Experience Cloud y la dirección de correo electrónico. Al habilitar el esquema para el perfil, se asegura de que los datos capturados del sitio web se agregan al perfil del cliente en tiempo real.

   Junto a los datos de comportamiento, también puede capturar datos de atributos de perfil de su sitio (por ejemplo, detalles de perfiles que se subscriben a un boletín informativo).

   Para capturar estos datos de perfil, debe hacer lo siguiente:

   * Crear un esquema basado en la clase Perfil individual XDM.

   * Agregar el grupo de campos Profile Core v2 al esquema.

   * Agregar un objeto de identificación basado en el grupo de campos Profile Core v2.

   * Definir Experience Cloud ID como identificador principal y el correo electrónico como identificador.

   * Habilitar el esquema para el perfil

   Consulte [Crear y editar esquemas en la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=es) para obtener más información sobre cómo agregar y quitar grupos de campos y campos individuales a un esquema.

{{upgrade-final-step}}
