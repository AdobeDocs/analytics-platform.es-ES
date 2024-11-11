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
source-wordcount: '341'
ht-degree: 23%

---

# Añadir la extensión del SDK web a la etiqueta

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Puede utilizar la función Etiquetas en Adobe Experience Platform para implementar código en el sitio para recopilar datos. Esta solución de administración de etiquetas le permite implementar código de junto con otros requisitos de etiquetado. Las etiquetas ofrecen una integración perfecta con Adobe Experience Platform mediante la extensión del SDK web de Adobe Experience Platform.

En la siguiente información se describe cómo agregar la extensión del SDK web a la etiqueta. Para obtener información adicional, consulte [Configure the Web SDK tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) en la documentación del Experience Platform. El SDK web incluye el [!UICONTROL servicio Adobe Experience Cloud ID] de forma nativa, por lo que no es necesario que agregue la extensión del servicio de ID a la etiqueta.

Después de [crear una etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), debe configurarla con la extensión del SDK web de Adobe Experience Platform. Esto garantiza que pueda enviar datos a Adobe Experience Platform (a través de su conjunto de datos).

Para agregar la extensión del SDK web a la etiqueta:

1. Inicie sesión en experience.adobe.com con sus credenciales de Adobe ID.

1. En Adobe Experience Platform, vaya a **[!UICONTROL Recopilación de datos]** > **[!UICONTROL Etiquetas]**.

1. Seleccione la etiqueta recién creada de la lista de [!UICONTROL Propiedades de la etiqueta] para abrirla.

1. Seleccione **[!UICONTROL Extensiones]** en el carril izquierdo.

1. Seleccione **[!UICONTROL Catálogo]** en la barra superior.

1. Busque o desplácese hasta la **[!UICONTROL extensión del SDK web de Adobe Experience Platform]** y, a continuación, seleccione **[!UICONTROL Instalar]** para instalarla.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Seleccione la zona protegida y la secuencia de datos que ha creado anteriormente para su [!UICONTROL Entorno de producción], (opcionalmente) su [!UICONTROL Entorno de ensayo] y su [!UICONTROL Entorno de desarrollo].

   ![Configuración de la extensión del SDK web de AEP](assets/aepwebsk-extension-datastreams.png)

1. Seleccione **[!UICONTROL Guardar]**.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).