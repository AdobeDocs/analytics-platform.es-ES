---
description: Uso compartido de proyectos y funciones de proyectos en Workspace
keywords: Uso compartido en Analysis Workspace
title: Compartir proyectos
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 534f163230ea7cafc97948fe0e8196d1dea47fa8
workflow-type: tm+mt
source-wordcount: '2091'
ht-degree: 57%

---

# Compartir proyectos

Puede compartir un proyecto de Analysis Workspace con los siguientes tipos de personas:

* Usuarios y grupos de su organización que tienen acceso a Adobe Customer Journey Analytics

  Puede compartir el acceso de Editar, Duplicar o Ver

* Usuarios y grupos de su organización que no tienen acceso a Customer Journey Analytics

  Los destinatarios tienen acceso de solo lectura

* Personas fuera de la organización

  Los destinatarios tienen acceso de solo lectura

Cualquier [depuración](curate.md) que haya aplicado antes del uso compartido se verá reflejada cuando los destinatarios abran el proyecto.

A continuación se muestra un vídeo introductorio del uso compartido de proyectos:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Compartir con usuarios y grupos de Customer Journey Analytics de su organización {#Add}

Puede compartir un proyecto con usuarios o grupos de Customer Journey Analytics existentes de su organización. Cuando comparte un proyecto como se describe en esta sección, los usuarios con los que comparte ya deben tener una cuenta de Customer Journey Analytics.

Puede compartir una función específica con usuarios o grupos, o bien compartir un vínculo.

* [Compartir una función de proyecto específica](#share-a-specific-project-role)

* [Compartir un vínculo a un proyecto](#share-a-link-to-a-project)

## Compartir una función de proyecto específica

Cuando comparta una función de proyecto específica con usuarios y grupos de su organización, tenga en cuenta lo siguiente:

* Las funciones del proyecto (**[!UICONTROL Editar original]**, **[!UICONTROL Editar copia]**, y **[!UICONTROL Solo lectura]**) están vinculadas al usuario y al ID de proyecto específico. Las funciones de proyecto son independientes de los permisos de usuario administrados en la [Admin Console de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es).

* En Customer Journey Analytics, los grupos se definen mediante perfiles de producto en [Admin Console de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es). Los administradores pueden compartir con cualquier grupo, incluido “Todos”. Los no administradores pueden compartir con los grupos de los que son miembros, excepto con el grupo “Todos”.

* El usuario que desempeña varias funciones siempre obtiene la mayor experiencia. Esto puede ocurrir si se agrega un destinatario como individuo y además, como parte de un grupo. Por ejemplo, si a un usuario se le asigna la función **[!UICONTROL Editar original]** como individuo y la función **[!UICONTROL Solo lectura]** como miembro de un grupo, recibirá una experiencia de proyecto **[!UICONTROL Editar original]**.

* Los administradores con una función **[!UICONTROL Editar copia]** o **[!UICONTROL Solo lectura]** recibirán esas experiencias limitadas cuando abran un proyecto. Un administrador puede cambiar su función a **[!UICONTROL Editar original]** compartiendo el proyecto con él mismo y otorgando la función Editar, tal como se describe en el siguiente procedimiento.

* Si se seleccionan varios proyectos para compartirlos, se agregarán destinatarios a la lista de destinatarios existente para cada proyecto.

  Por ejemplo, el proyecto A ya se comparte con los destinatarios 1, 2 y 3, mientras que el proyecto B ya se comparte con los destinatarios 4, 5 y 6.

  Los proyectos A y B se comparten con los destinatarios 4 y 7. La nueva lista de uso compartido para el proyecto A es ahora 1, 2, 3, 4 y 7, mientras que la nueva lista de uso compartido para el proyecto B es 4, 5, 6 y 7.

Para compartir una función de proyecto específica con usuarios o grupos de su organización, haga lo siguiente:

1. En Customer Journey Analytics, seleccione la opción [!UICONTROL **Workspace**] pestaña, luego seleccione [!UICONTROL **Proyectos**] en el carril izquierdo.

1. Seleccione la casilla de verificación situada junto a uno o varios proyectos que desee compartir y, a continuación, seleccione [!UICONTROL **Compartir**].

   O

   Para compartir solo un proyecto individual, puede abrir el proyecto que desea compartir y, a continuación, seleccionar **[!UICONTROL Compartir]** > **[!UICONTROL Compartir con usuarios de Workspace]**.
Si hay cambios sin guardar, se le pedirá que guarde primero el proyecto.

   Se muestra el cuadro de diálogo Compartir proyecto. El [!UICONTROL **Compartir mediante vínculo**] y [!UICONTROL **Configuración**] Las secciones del cuadro de diálogo sólo están visibles al compartir un único proyecto.

   ![La ventana Compartir proyecto.](assets/share-proj-modal.png)

1. Añada destinatarios o grupos de destinatarios en uno de los campos de función proporcionados:

   **Editar original:** los destinatarios pueden **[!UICONTROL Guardar]** los cambios en un proyecto y en una funcionalidad como copropietarios. Esta función resulta útil si desea administrar un proyecto conjuntamente con otros compañeros. Esto incluye editar, eliminar y modificar listas de destinatario para un proyecto compartido. <br>Nota: Actualmente, Analysis Workspace no admite la colaboración en tiempo real, por lo que se recomienda que solo un usuario edite un proyecto a la vez. Si los proyectos se guardan al mismo tiempo, se conservará la última versión.

   **Editar copia:** los destinatarios pueden **[!UICONTROL Guardar como]** y acceder al carril izquierdo. Las interacciones del proyecto no están limitadas en esta función. Esta función es útil si desea compartir un proyecto con usuarios que comprendan los datos de su organización y cómo usar Analysis Workspace, pero no desea que el proyecto se modifique.

   **Solo lectura:** los destinatarios no pueden **[!UICONTROL Guardar]** o **[!UICONTROL Guardar como]** y no tienen acceso al carril izquierdo. Las interacciones del proyecto también están limitadas. Esta función resulta útil si desea compartir un proyecto con usuarios menos familiarizados con la estructura de datos de su organización, con Analysis Workspace o con el Customer Journey Analytics en general. Sin embargo, aún desea que consuman datos y perspectivas en un entorno seguro. Obtenga más información sobre la [la experiencia de proyecto Solo lectura](/help/analysis-workspace/curate-share/view-only-projects.md).

1. (Condicional) Si comparte un solo proyecto, elija si desea habilitar las siguientes opciones al compartir el proyecto:

   * **Compartir componentes de proyecto incrustados:** Comparte filtros, métricas calculadas e intervalos de fechas con todos los destinatarios. Después de compartirlos, estos componentes aparecerán en el menú desplegable de componentes del espacio de trabajo del destinatario. Esta configuración no se mantiene, se trata de una acción concreta usada al momento de compartir.

   * **Establecer como página de aterrizaje para destinatarios:** establece esta página como página de aterrizaje para destinatarios. Esta configuración no se mantiene, se trata de una acción concreta usada al momento de compartir.

1. Seleccionar **[!UICONTROL Compartir]**. (Si el proyecto ya se ha compartido, seleccione [!UICONTROL **Actualizar**].)

   O

   Seleccionar **[!UICONTROL Depurar y compartir]** para aplicar la depuración del proyecto automáticamente. (Si el proyecto ya se ha compartido, seleccione **[!UICONTROL Depurar y actualizar]**.) Obtenga más información sobre la [depuración del proyecto](curate.md).

## Compartir un vínculo a un proyecto

Cuando comparta un vínculo como se describe en esta sección, tenga en cuenta lo siguiente:

* Los destinatarios que utilicen el vínculo deben iniciar sesión en Customer Journey Analytics antes de obtener acceso al proyecto.

* Si a un destinatario no se le asigna una función y recibe un [vínculo](/help/analysis-workspace/curate-share/shareable-links.md) al proyecto (**[!UICONTROL Compartir] > [!UICONTROL Obtener vínculo de proyecto]**), se le asignará una función predeterminada. Los administradores reciben **[!UICONTROL Editar original]** y los usuarios que no son administradores reciben **[!UICONTROL Editar copia]**.

Para compartir el vínculo del proyecto con los usuarios de su organización, haga lo siguiente:

1. Guarde el proyecto. Si hay cambios sin guardar, se le pedirá que guarde el proyecto antes de compartir un vínculo.

1. Seleccione **[!UICONTROL Compartir]** > **[!UICONTROL Compartir con usuarios de Workspace]**, y, a continuación, seleccione **[!UICONTROL Copiar]** junto al campo **[!UICONTROL Compartir mediante vínculo]**.

   ![El proyecto Compartir resalta el campo Compartir por vínculo.](assets/share-proj-modal.png)

1. Comparta el vínculo con los usuarios de su organización. Por ejemplo, puede pegarlo en un correo electrónico, en un sitio web interno, etc.

## Compartir un proyecto con cualquiera (no se requiere inicio de sesión) {#share-public-link}

Puede conceder [acceso de solo lectura](/help/analysis-workspace/curate-share/view-only-projects.md) a proyectos de Analysis Workspace para personas que no tienen acceso a Customer Journey Analytics. Esto puede incluir:

* Personas fuera de la organización

* Personas de su organización que no tienen acceso a Customer Journey Analytics

>[!NOTE]
>
>Tenga en cuenta lo siguiente al compartir un proyecto de Analysis Workspace con personas que no tienen acceso a Customer Journey Analytics:
>
>* El administrador del Customer Journey Analytics puede deshabilitar la capacidad para compartir un proyecto de esta manera, tal como se describe en [Preferencias](/help/analysis-workspace/user-preferences.md). Si no puede compartir un proyecto como se describe en esta sección, el administrador del Customer Journey Analytics ha desactivado esta capacidad.
>
>* Los proyectos con más de 50 visualizaciones expandidas no se pueden compartir con personas que no tengan acceso a Customer Journey Analytics.
>
>* Los usuarios con los que comparta pueden ver cualquier filtro que se haya aplicado al proyecto durante [depuración](curate.md).
> 
>* Los usuarios con los que comparte puede cambiar el intervalo de fechas del proyecto. El intervalo de fechas que ha establecido para el proyecto se muestra de forma predeterminada.
>
>* Un proyecto podría resultar inaccesible si muchos usuarios intentan acceder a un vínculo determinado al mismo tiempo. De forma predeterminada, más de 190 personas pueden acceder a un solo vínculo cada 5 minutos. Si su organización alcanza este límite, espere 5 minutos e intente acceder al vínculo de nuevo.
>
>* Si su organización dispone de licencia para Healthcare Shield, solo podrá compartir proyectos con usuarios autenticados mediante el inicio de sesión único (SSO) o Adobe ID; no podrá compartir proyectos con usuarios no autenticados. Es su responsabilidad utilizar esta función de conformidad con las políticas internas de control de datos de su empresa y compartir únicamente los vínculos de proyecto que contengan Información médica personal (PHI) con los usuarios que tengan los permisos adecuados.

La siguiente demostración en vídeo y la documentación adjunta describen las opciones asociadas con el uso compartido de un vínculo con cualquier persona:

>[!VIDEO](https://video.tv.adobe.com/v/3420093/?learn=on)

Para compartir un proyecto de Analysis Workspace con cualquier persona:

1. Abra el proyecto de Analysis Workspace que desee compartir.

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Compartir con cualquiera]**.

   Si hay cambios sin guardar, se le pedirá que guarde primero el proyecto.

   <!-- Add screen shot of new modal -->

1. Habilite la opción **[!UICONTROL El vínculo está activo]** si aún no está habilitada.

   Al seleccionar esta opción, se crea un vínculo al proyecto que se puede compartir con cualquier persona. Puede deshabilitar el acceso al proyecto en cualquier momento desactivando esta opción.

   El propietario del proyecto también es el propietario de este vínculo. La propiedad de los vínculos solo se puede transferir a otro usuario cuando se transfiere la propiedad del proyecto, tal como se describe en [Transferir recursos de usuario o establecer caducidades de cuenta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=es) en la guía de administración de Analytics.

1. Elija si desea activar la siguiente opción de seguridad (esta opción puede controlarla el administrador del Customer Journey Analytics):

   * **[!UICONTROL Requiere autenticación de Experience Cloud]:**

     Cuando esta opción está habilitada, los únicos usuarios que pueden acceder al proyecto son los que pueden iniciar sesión en la organización de Adobe Experience Cloud en la que se creó el proyecto que está compartiendo. Sin embargo, no es necesario que los usuarios con los que comparte tengan acceso a Adobe Analytics.

     Los administradores de Customer Journey Analytics pueden configurar esta preferencia para la empresa, tal como se describe en [Preferencias](/help/analysis-workspace/user-preferences.md). Dependiendo de cómo haya configurado esta opción el administrador, puede encontrarse con los siguientes escenarios:

      * Si esta opción no está visible, el administrador del Customer Journey Analytics no habilitó esta función.

      * Si esta opción está habilitada y no puede deshabilitarla, significa que el administrador del Customer Journey Analytics requiere la autenticación del Experience Cloud para cualquier persona que acceda a proyectos de Analysis Workspace. Este siempre es el caso de las organizaciones que conceden la licencia a Healthcare Shield.

1. Junto a la **[!UICONTROL Compartir con cualquiera (no se requiere inicio de sesión)]** , haga clic en el **Copiar vínculo** icono ![Icono Copiar vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg)) para copiar el enlace en el portapapeles del sistema.

1. Comparta el enlace con las personas que quiera que tengan acceso al proyecto. Por ejemplo, puede pegar el enlace en un correo electrónico.

   Cualquier persona con la que comparta el enlace podrá ver el proyecto de Analysis Workspace.

1. (Opcional) Puede hacer clic en el icono **Generar nuevo enlace** ![icono Generar enlace](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) para quitar el acceso de los usuarios que anteriormente recibieron un enlace al proyecto. Se genera un nuevo enlace que puede compartir con los usuarios que desee que accedan al proyecto.

1. Seleccione **[!UICONTROL Cerrar]** para cerrar el cuadro de diálogo de compartir. Los cambios se guardan automáticamente.

## Ver proyectos compartidos con usted

Cuando alguien comparte un proyecto con usted por [uso compartido de una función de proyecto específica](#share-a-specific-project-role), puede acceder a los proyectos compartidos desde el [Pestaña Proyectos de en la página de aterrizaje de Analytics](/help/getting-started/landing.md#navigate-the-projects-tab).

Cuando alguien comparte un proyecto con usted compartiendo un vínculo (desde el [Pestaña Compartir proyecto](#share-a-link-to-a-project) o mediante una [vínculo compartir con cualquiera](#share-a-project-with-anyone-no-login-required)), debe utilizar el vínculo que se compartió con usted para acceder al proyecto. Por ejemplo, es posible que el vínculo se haya compartido en un correo electrónico, en un sitio web interno, etc.

## Uso compartido de componentes incrustados

A continuación se muestra un vídeo sobre este tema:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Preguntas frecuentes {#FAQs}

| Pregunta | Respuesta |
|---|---|
| ¿Qué sucede si dos editores guardan un proyecto al mismo tiempo? | Los cambios no se combinan y se conservará la última versión guardada del proyecto. Actualmente, Analysis Workspace no admite la colaboración en tiempo real. |
| Como administrador, ¿qué experiencia de proyecto veré? | Administradores ubicados en un **[!UICONTROL Editar copia]** o **[!UICONTROL Solo lectura]** Esta función recibirá esas experiencias limitadas cuando abra un proyecto. Si lo desea, un administrador puede aumentar su función a **[!UICONTROL Editar original]** en cualquier momento mediante **[!UICONTROL Componentes] > [!UICONTROL Proyectos]**. |
| ¿Qué sucede si un destinatario se coloca en una función como individuo y otra como miembro de un grupo? | Si un destinatario se coloca en varias funciones, siempre recibirá la experiencia más alta. Por ejemplo, si a un destinatario se le asigna la variable **[!UICONTROL Editar original]** función como individuo y la función **[!UICONTROL Puede ver]** función como miembro de un grupo, recibirá una **[!UICONTROL Editar original]** experiencia del proyecto. |
| ¿Qué experiencia obtiene un destinatario si abre un vínculo de proyecto? | Los Destinatarios reciben la función que les ha asignado en el modal de uso compartido. Si a un destinatario no se le asigna una función y recibe un enlace al proyecto (**[!UICONTROL Compartir]** > **[!UICONTROL Compartir con usuarios de Workspace]**, a continuación, seleccione **[!UICONTROL Copiar]** junto al campo **[!UICONTROL Compartir por enlace]**), se le asignará una función predeterminada. Los administradores reciben **[!UICONTROL Editar original]** y los no administradores reciben **[!UICONTROL Editar copia]**. |
