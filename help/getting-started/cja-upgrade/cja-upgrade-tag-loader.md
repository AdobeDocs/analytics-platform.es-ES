---
title: Implementar la etiqueta de carga para la extensión del SDK web
description: Aprenda a implementar la etiqueta de carga para la extensión del SDK web
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '283'
ht-degree: 100%

---

# Implementar la etiqueta de carga para la extensión del SDK web {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="Implemente la etiqueta de carga en su sitio"
>abstract="Trabaje con el equipo de desarrollo del sitio web para instalar la etiqueta de carga en cada página del sitio.<br><br>El tiempo necesario para llevar a cabo esta tarea depende en gran medida del tiempo de respuesta del equipo de ingeniería con el que trabaje para implementar el código. Algunas organizaciones que tienen equipos de ingeniería altamente adaptables pueden completar este paso en días, mientras que los equipos de ingeniería con un gran número de tareas pendientes pueden tardar un mes o más."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Debe instalar la etiqueta en el sitio web del que desee realizar un seguimiento, lo que implica colocar un código en la etiqueta de encabezado de la plantilla del sitio web.

El siguiente proceso describe cómo obtener el código que hace referencia a la etiqueta. Para obtener información adicional, consulte las [guías de implementación para etiquetas y reenvío de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) en la documentación de Experience Platform.

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

{{upgrade-final-step}}
