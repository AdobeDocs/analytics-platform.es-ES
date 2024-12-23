---
title: Implementación de la etiqueta de carga para la extensión del SDK web
description: Obtenga información sobre cómo implementar la etiqueta de carga para la extensión del SDK web
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 937a7f31361027438929194f8ccc5aee83c33bc0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 34%

---

# Implementación de la etiqueta de carga para la extensión del SDK web

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Debe instalar la etiqueta en el sitio web que desee rastrear, lo que implica colocar un código en la etiqueta de encabezado de la plantilla del sitio web.

El siguiente proceso describe cómo obtener el código que hace referencia a la etiqueta. Para obtener información adicional, consulte las [Guías de implementación para etiquetas y reenvío de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) en la documentación del Experience Platform.

Para obtener el código que hace referencia a la etiqueta, debe hacer lo siguiente:

1. Seleccione **[!UICONTROL Entornos]** en el carril izquierdo.

1. En la lista de entornos, seleccione el botón (cuadro) de instalación correcto.

   En el cuadro de diálogo [!UICONTROL Instrucciones de instalación en la web] seleccione el botón para copiar junto al código de script que debería ser parecido a:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Entorno](assets/environment.png)

1. Seleccione **[!UICONTROL Cerrar]**.

   En lugar del código para el entorno de desarrollo, puede seleccionar otro entorno (ensayo o producción) en función de dónde se encuentre en el proceso de implementación del SDK web de Adobe Experience Platform.

   Consulte [Entornos](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=es) para obtener más información.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).
