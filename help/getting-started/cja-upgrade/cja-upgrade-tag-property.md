---
title: Crear una propiedad de etiqueta y agregar la extensión del SDK web
description: Obtenga información sobre cómo crear una propiedad de etiqueta y agregar la extensión del SDK web
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ccc6df56771cd9f83bbd7a8570e32d7ed63a0ced
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 22%

---

# Cree una etiqueta para su propiedad

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Puede utilizar la función Etiquetas en Adobe Experience Platform para implementar código en el sitio para recopilar datos. Esta solución de administración de etiquetas le permite implementar código de junto con otros requisitos de etiquetado. Las etiquetas ofrecen una integración perfecta con Adobe Experience Platform mediante la extensión del SDK web de Adobe Experience Platform.

La siguiente información describe cómo crear una etiqueta para la propiedad. Para obtener información adicional, consulte [Configure the Web SDK tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) en la documentación del Experience Platform. El SDK web incluye el [!UICONTROL servicio Adobe Experience Cloud ID] de forma nativa, por lo que no es necesario que agregue la extensión del servicio de ID a la etiqueta.

Una propiedad es básicamente un contenedor que se rellena con extensiones, reglas, elementos de datos y bibliotecas al implementar etiquetas en el sitio. Mucha gente crea una propiedad para cada sitio web (o grupo de sitios relacionados) donde desean implementar el mismo conjunto de etiquetas. Para obtener más información sobre las propiedades, consulte [Propiedades](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) en la documentación de recopilación de datos del Experience Platform.

Para crear una etiqueta para su propiedad:

1. Inicie sesión en experience.adobe.com con sus credenciales de Adobe ID.

1. En Adobe Experience Platform, vaya a **[!UICONTROL Recopilación de datos]** > **[!UICONTROL Etiquetas]**.

1. Seleccione **[!UICONTROL Nueva propiedad]**.

   Asigne un nombre a la etiqueta, seleccione **[!UICONTROL Web]** e introduzca un nombre de dominio. Seleccione **[!UICONTROL Guardar]** para continuar.

   ![Crear una propiedad](assets/create-property.png)

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).

