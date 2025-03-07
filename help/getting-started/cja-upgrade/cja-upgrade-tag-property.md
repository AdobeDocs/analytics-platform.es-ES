---
title: Creación de una propiedad de etiquetas y adición de la extensión Web SDK
description: Obtenga información sobre cómo crear una propiedad de etiquetas y añadir la extensión Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 45%

---

# Creación de una etiqueta para su propiedad {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Creación de una propiedad de etiqueta en la recopilación de datos de Adobe Experience Platform"
>abstract="Usar etiquetas es el estándar típico para la recopilación de datos. Cree una etiqueta en la interfaz de Adobe Experience Platform para poder actualizar las variables de recopilación de datos en cualquier momento.<br><br>La creación de una propiedad de etiqueta puede completarse con varios clics y tardar solamente unos minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Puede utilizar la función Etiquetas en Adobe Experience Platform para implementar código en el sitio para recopilar datos. Esta solución de administración de etiquetas le permite implementar código de junto con otros requisitos de etiquetado. Las etiquetas ofrecen una integración perfecta con Adobe Experience Platform mediante la extensión del SDK web de Adobe Experience Platform.

La siguiente información describe cómo crear una etiqueta para la propiedad. Para obtener información adicional, consulte [Configuración de la extensión de etiquetas Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) en la documentación de Experience Platform. Web SDK incluye el [!UICONTROL servicio Adobe Experience Cloud ID] de forma nativa, por lo que no es necesario que agregue la extensión del servicio de ID a la etiqueta.

Una propiedad es básicamente un contenedor que se rellena con extensiones, reglas, elementos de datos y bibliotecas al implementar etiquetas en el sitio. Mucha gente crea una propiedad para cada sitio web (o grupo de sitios relacionados) donde desean implementar el mismo conjunto de etiquetas. Para obtener más información sobre las propiedades, consulte [Propiedades](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) en la documentación de recopilación de datos de Experience Platform.

Para crear una etiqueta para su propiedad:

1. Inicie sesión en experience.adobe.com con sus credenciales de Adobe ID.

1. En Adobe Experience Platform, vaya a **[!UICONTROL Recopilación de datos]** > **[!UICONTROL Etiquetas]**.

1. Seleccione **[!UICONTROL Nueva propiedad]**.

   Asigne un nombre a la etiqueta, seleccione **[!UICONTROL Web]** e introduzca un nombre de dominio. Seleccione **[!UICONTROL Guardar]** para continuar.

   ![Crear una propiedad](assets/create-property.png)

{{upgrade-final-step}}
