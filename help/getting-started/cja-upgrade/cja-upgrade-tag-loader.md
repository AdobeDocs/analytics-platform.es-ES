---
title: Implementación de la etiqueta de carga para la extensión del SDK web
description: Obtenga información sobre cómo implementar la etiqueta de carga para la extensión Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 28%

---

# Implementación de la etiqueta de carga para la extensión del SDK web {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="Implementación de la etiqueta de carga en el sitio"
>abstract="Trabaje con el equipo de desarrollo del sitio web para instalar la etiqueta de carga en cada página del sitio.<br><br>El tiempo de finalización de esta tarea depende en gran medida del tiempo de respuesta del equipo de ingeniería con el que trabaje para implementar el código. Algunas organizaciones que tienen equipos de ingeniería altamente adaptables pueden completar este paso en días, mientras que los equipos de ingeniería con un registro de tareas pendientes extenso pueden tardar un mes o más."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Debe instalar la etiqueta en el sitio web que desee rastrear, lo que implica colocar un código en la etiqueta de encabezado de la plantilla del sitio web.

El siguiente proceso describe cómo obtener el código que hace referencia a la etiqueta. Para obtener información adicional, consulte las [Guías de implementación para etiquetas y reenvío de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) en la documentación del Experience Platform.

Para obtener el código que hace referencia a la etiqueta, debe hacer lo siguiente:

1. Inicie sesión en experience.adobe.com con sus credenciales de Adobe ID.

1. En Adobe Experience Platform, vaya a **[!UICONTROL Recopilación de datos]** > **[!UICONTROL Etiquetas]**.

1. En la página **[!UICONTROL Propiedades de la etiqueta]**, seleccione la etiqueta recién creada en la lista de propiedades para abrirla.

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
