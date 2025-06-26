---
description: Uso compartido de proyectos y funciones de proyectos en Workspace
keywords: Uso compartido en Analysis Workspace
title: Compartir proyectos
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: a462e736ddcdf1a5ea84a85eea2c2ce0b8a34fb0
workflow-type: tm+mt
source-wordcount: '2092'
ht-degree: 98%

---

# Compartir proyectos {#share-projects}

>[!CONTEXTUALHELP]
>id="workspace_shareprojects"
>title="Compartir proyectos"
>abstract="Puede compartir cualquiera de estas funciones de proyecto con otros usuarios de su organización."



Puede compartir un proyecto de Analysis Workspace con los siguientes tipos de personas:

* Usuarios y grupos de su organización que tienen acceso a Adobe Customer Journey Analytics

  Puede compartir el acceso de Editar, Duplicar o Ver

* Usuarios y grupos de su organización que no tienen acceso a Customer Journey Analytics

  Los destinatarios tienen acceso de solo lectura

* Personas fuera de la organización

  Los destinatarios tienen acceso de solo lectura

Cualquier [depuración](curate.md) que haya aplicado antes del uso compartido se verá reflejada cuando los destinatarios abran el proyecto.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Uso compartido de proyectos en Analysis Workspace](https://video.tv.adobe.com/v/40033/?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]


## Compartir con usuarios y grupos de Customer Journey Analytics de su organización {#Add}

Puede compartir un proyecto con usuarios o grupos existentes de Customer Journey Analytics de su organización. Cuando comparte un proyecto, como se describe en esta sección, los usuarios con los que lo comparte deben tener una cuenta en Customer Journey Analytics.

Puede compartir una función específica con usuarios o grupos, o bien compartir un vínculo.

* [Compartir una función de proyecto específica](#share-a-specific-project-role)

* [Compartir un vínculo a un proyecto](#share-a-link-to-a-project)

## Compartir una función de proyecto específica

Cuando comparta una función de proyecto específica con usuarios y grupos de su organización, tenga en cuenta lo siguiente:

* Las funciones del proyecto (**[!UICONTROL Editar original]**, **[!UICONTROL Editar copia]**, y **[!UICONTROL Solo lectura]**) están vinculadas al usuario y al ID de proyecto específico. Las funciones de proyecto son independientes de los permisos de usuario administrados en la [Admin Console de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es).

* En Customer Journey Analytics, los grupos se definen mediante perfiles de producto en [Admin Console de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es). Los administradores pueden compartir con cualquier grupo, incluido “Todos”. Los no administradores pueden compartir con los grupos de los que son miembros, excepto con el grupo “Todos”.

* El usuario que desempeña varias funciones siempre obtiene la mayor experiencia. Esto puede ocurrir si se agrega un destinatario como individuo y además, como parte de un grupo. Por ejemplo, si a un usuario se le asigna la función **[!UICONTROL Editar original]** como individuo y la función **[!UICONTROL Solo lectura]** como miembro de un grupo, recibirá una experiencia de proyecto **[!UICONTROL Editar original]**.

* Los administradores con una función **[!UICONTROL Editar copia]** o **[!UICONTROL Solo lectura]** recibirán esas experiencias limitadas cuando abran un proyecto. Un administrador puede cambiar su función a **[!UICONTROL Editar original]** compartiendo el proyecto con él mismo y otorgando la función Editar, tal como se describe en el siguiente procedimiento.

* Si se seleccionan varios proyectos para compartirlos, se añadirán destinatarios a la lista de destinatarios existente para cada proyecto.

  Por ejemplo, el Proyecto A ya se comparte con los destinatarios 1, 2 y 3, mientras que el Proyecto B ya se comparte con los destinatarios 4, 5 y 6.

  A continuación, los proyectos A y B se comparten con los destinatarios 4 y 7. La nueva lista de uso compartido para el proyecto A es ahora 1, 2, 3, 4 y 7, mientras que la nueva lista de uso compartido para el proyecto B es 4, 5, 6 y 7.

Para compartir una función de proyecto específica con usuarios o grupos de su organización, haga lo siguiente:

1. En Customer Journey Analytics, seleccione la pestaña [!UICONTROL **Espacio de trabajo**] y, a continuación, seleccione [!UICONTROL **Proyectos**] en el panel de la izquierda.

1. Marque la casilla situada junto a uno o varios proyectos que desee compartir y, a continuación, seleccione [!UICONTROL **Compartir**].

   O bien

   Para compartir solo un proyecto individual, puede abrir el proyecto que desee compartir y, a continuación, seleccionar **[!UICONTROL Compartir]** > **[!UICONTROL Compartir con usuarios del espacio de trabajo]**.
Si hay cambios sin guardar, se le pedirá que guarde primero el proyecto.

   Se muestra el cuadro de diálogo Compartir proyecto. Las secciones [!UICONTROL **Compartir por vínculo**] y [!UICONTROL **Configuración**] del cuadro de diálogo solo son visibles cuando se comparte un único proyecto.

   ![Ventana Compartir proyecto.](assets/share-proj-modal.png)

1. Añada destinatarios o grupos de destinatarios en uno de los campos de función proporcionados:

   **Editar original:** los destinatarios pueden **[!UICONTROL Guardar]** los cambios en un proyecto y en una funcionalidad como copropietarios. Esta función resulta útil si desea administrar un proyecto conjuntamente con otros compañeros. Esto incluye editar, eliminar y modificar listas de destinatario para un proyecto compartido. <br>Nota: Actualmente, Analysis Workspace no admite la colaboración en tiempo real, por lo que se recomienda que solo un usuario edite un proyecto a la vez. Si los proyectos se guardan al mismo tiempo, se conservará la última versión.

   **Editar copia:** los destinatarios pueden **[!UICONTROL Guardar como]** y acceder al panel izquierdo. Las interacciones del proyecto no están limitadas en esta función. Esta función es útil si desea compartir un proyecto con usuarios que comprendan los datos de su organización y cómo usar Analysis Workspace, pero no desea que el proyecto se modifique.

   **Solo lectura** los destinatarios no pueden **[!UICONTROL Guardar]** o **[!UICONTROL Guardar como]** y no tienen acceso al panel izquierdo. Las interacciones del proyecto también están limitadas. Esta función resulta útil si desea compartir un proyecto con usuarios menos familiarizados con la estructura de datos de su organización, Analysis Workspace o Customer Journey Analytics en general. Sin embargo, aún desea que consuman datos y perspectivas en un entorno seguro. Obtenga más información sobre la [la experiencia de proyecto Solo lectura](/help/analysis-workspace/curate-share/view-only-projects.md).

1. (Condicional) Si comparte un único proyecto, elija si desea activar las siguientes opciones al compartir el proyecto:

   * **Compartir componentes del proyecto incrustados:** comparta segmentos, métricas calculadas e intervalos de fechas con todos los destinatarios. Después de compartirlos, estos componentes aparecerán en el menú desplegable Componentes de Workspace del destinatario. Esta configuración no se mantiene, se trata de una acción concreta usada al momento de compartir.

   * **Establecer como página de destino para destinatarios:** establece esta página como página de destino para destinatarios. Esta configuración no se mantiene, se trata de una acción concreta usada al momento de compartir.

1. Seleccione **[!UICONTROL Compartir]**. (Si el proyecto ya se ha compartido, haga clic en [!UICONTROL **Actualizar**].)

   O bien

   Seleccione **[!UICONTROL Depurar y compartir]** para aplicar la depuración del proyecto automáticamente. (Si el proyecto ya se ha compartido, seleccione **[!UICONTROL Depurar y actualizar]**). Obtenga más información sobre la [depuración del proyecto](curate.md).


## Compartir un vínculo a un proyecto

Cuando comparta un vínculo como se describe en esta sección, tenga en cuenta lo siguiente:

* Los destinatarios que utilicen el vínculo deben iniciar sesión en Customer Journey Analytics antes de obtener acceso al proyecto.

* Si a un destinatario no se le asigna una función y recibe un [vínculo que se puede compartir](/help/analysis-workspace/curate-share/shareable-links.md) con el proyecto (**[!UICONTROL Compartir] > [!UICONTROL Obtener vínculo del proyecto]**), se le asignará una función de forma predeterminada. Los administradores reciben **[!UICONTROL Editar original]** y los usuarios que no son administradores reciben **[!UICONTROL Editar copia]**.

Para compartir el vínculo del proyecto con los usuarios de su organización, haga lo siguiente:

1. Guarde el proyecto. Si hay cambios sin guardar, se le pedirá que guarde el proyecto antes de compartir un vínculo.

1. Seleccione **[!UICONTROL Compartir]** > **[!UICONTROL Compartir con usuarios de Workspace]**, y, a continuación, seleccione **[!UICONTROL Copiar]** junto al campo **[!UICONTROL Compartir mediante vínculo]**.

   ![Proyecto Compartir que resalta el campo Compartir mediante vínculo.](assets/share-proj-modal.png)

1. Comparta el vínculo con los usuarios de su organización. Por ejemplo, puede pegarlo en un correo electrónico, en un sitio web interno, etc.

## Compartir un proyecto con cualquiera (no se requiere inicio de sesión) {#share-public-link}

>[!CONTEXTUALHELP]
>id="workspace_share_with_anyone_require_aec_authentication"
>title="Requiere autenticación de Experience Cloud"
>abstract="Su organización requiere que los usuarios inicien sesión en Experience Cloud para poder utilizar este vínculo."


Puede conceder [acceso de solo lectura](/help/analysis-workspace/curate-share/view-only-projects.md) a proyectos de Analysis Workspace a las personas que no tienen acceso a Customer Journey Analytics. Esto puede incluir:

* Personas fuera de la organización

* Personas de su organización que no tienen acceso a Customer Journey Analytics

>[!NOTE]
>
>Tenga en cuenta lo siguiente cuando comparta un proyecto de Analysis Workspace con personas que no tienen acceso a Customer Journey Analytics:
>
>* La posibilidad de compartir un proyecto de esta manera, tal como se describe en [Preferencias](/help/analysis-workspace/user-preferences.md) la puede deshabilitar su administrador de Customer Journey Analytics. Si no puede compartir un proyecto como se describe en esta sección es que su administrador de Customer Journey Analytics ha desactivado esta posibilidad.
>
>* Los proyectos con más de 50 visualizaciones expandidas no se pueden compartir con personas que no tengan acceso a Customer Journey Analytics.
>
>* Los usuarios con los que comparte pueden ver cualquier segmento que se haya aplicado al proyecto durante el [curado](curate.md).
> 
>* Los usuarios con los que comparte puede cambiar el intervalo de fechas del proyecto. El intervalo de fechas que ha establecido para el proyecto se muestra de forma predeterminada.
>
>* Un proyecto podría resultar inaccesible si muchos usuarios intentan acceder a un vínculo determinado al mismo tiempo. De forma predeterminada, más de 190 personas pueden acceder a un solo vínculo cada 5 minutos. Si su organización alcanza este límite, espere 5 minutos e intente acceder al vínculo de nuevo.
>
>* Para las licencias [!DNL Healthcare Shield] y [!DNL Privacy & Security Shield], la característica [!UICONTROL Compartir con cualquiera] requiere autenticación de Experience Cloud. Para los clientes de [!DNL Healthcare Shield], aparece la advertencia &quot;HIPAA cumplimiento&quot;, pero aún puede usar esta característica después de autenticarse en Experience Cloud.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Compartir con cualquiera](https://video.tv.adobe.com/v/3452454/?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


Para compartir un proyecto de Analysis Workspace con cualquier persona:

1. Abra el proyecto de Analysis Workspace que desee compartir.

1. Seleccione **[!UICONTROL Compartir]** > **[!UICONTROL Compartir con cualquiera]**.

   Si hay cambios sin guardar, se le pedirá que guarde primero el proyecto.

   <!-- Add screen shot of new modal -->

1. Habilite la opción **[!UICONTROL El vínculo está activo]** si aún no está habilitada.

   Al seleccionar esta opción, se crea un vínculo al proyecto que se puede compartir con cualquier persona. Puede deshabilitar el acceso al proyecto en cualquier momento desactivando esta opción.

   El propietario del proyecto también es el propietario de este vínculo. La propiedad de los vínculos solo se puede transferir a otro usuario cuando se transfiere la propiedad del proyecto, tal como se describe en [Transferencia de recursos de usuario](/help/tools/asset-transfer/transfer-assets.md) en la guía de administración de Analytics.

1. Elija si desea activar la siguiente opción de seguridad (esta opción la puede controlar su administrador de Customer Journey Analytics):

   * **[!UICONTROL Requiere autenticación de Experience Cloud]:**

     Cuando esta opción está habilitada, los únicos usuarios que pueden acceder al proyecto son los que pueden iniciar sesión en la organización de Adobe Experience Cloud en la que se creó el proyecto que está compartiendo. Sin embargo, no es necesario que los usuarios con los que comparte tengan acceso a Customer Journey Analytics.

     Los administradores de Customer Journey Analytics pueden configurar esta preferencia para la compañía, como se describe en [Preferencias](/help/analysis-workspace/user-preferences.md). Dependiendo de cómo haya configurado esta opción el administrador, puede encontrarse con los siguientes escenarios:

      * Si esta opción no está visible es que su administrador de Customer Journey Analytics no ha habilitado esta función.

      * Si esta opción está activada y no puede desactivarla, significa que su administrador de Customer Journey Analytics requiere la autenticación de Experience Cloud para cualquiera que acceda a proyectos de Analysis Workspace. Este siempre es el caso de las organizaciones que conceden licencias a Healthcare Shield.

1. Junto al campo **[!UICONTROL Compartir con cualquiera (no es necesario iniciar sesión)]**, seleccione ![Vínculo](/help/assets/icons/Link.svg) para copiar el vínculo en el portapapeles del sistema.

1. Comparta el enlace con las personas que quiera que tengan acceso al proyecto. Por ejemplo, puede pegar el enlace en un correo electrónico.

   Cualquier persona con la que comparta el enlace podrá ver el proyecto de Analysis Workspace.

1. (Opcional) Puede seleccionar el icono ![Generar nuevo vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) para quitar el acceso de los usuarios que anteriormente recibieron un vínculo al proyecto. Se genera un nuevo enlace que puede compartir con los usuarios que desee que accedan al proyecto.

1. Seleccione **[!UICONTROL Cerrar]** para cerrar el cuadro de diálogo de compartir. Los cambios se guardan automáticamente.

## Ver proyectos compartidos con usted

Cuando alguien comparte un proyecto con usted [compartiendo una función de proyecto específica](#share-a-specific-project-role), usted puede acceder a los proyectos compartidos desde la pestaña [Proyectos de la página de destino de Analytics](/help/getting-started/landing.md#navigate-the-projects-tab).

Cuando alguien comparte un proyecto con usted compartiendo un vínculo (ya sea desde la pestaña [Compartir proyecto](#share-a-link-to-a-project) o utilizando un vínculo [Compartir con cualquiera](#share-a-project-with-anyone-no-login-required), debe utilizar el vínculo que compartió con usted para acceder al proyecto. Por ejemplo, el vínculo puede haberse compartido en un correo electrónico, en un sitio web interno, etc.

## Uso compartido de componentes incrustados

Puede compartir los componentes incrustados que forman parte del proyecto.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Compartir componentes incrustados en Analysis Workspace](https://video.tv.adobe.com/v/327499/?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]


## Preguntas frecuentes {#FAQs}

| Pregunta | Respuesta |
|---|---|
| ¿Qué sucede si dos editores guardan un proyecto al mismo tiempo? | Los cambios no se combinan y se conservará la última versión guardada del proyecto. Actualmente, Analysis Workspace no admite la colaboración en tiempo real. |
| Como administrador, ¿qué experiencia de proyecto veré? | Los administradores con una función **[!UICONTROL Editar copia]** o **[!UICONTROL Solo lectura]** recibirán esas experiencias limitadas cuando abran un proyecto. Si lo desea, un administrador puede ampliar su función a **[!UICONTROL Editar original]** en cualquier momento **[!UICONTROL Componentes] > [!UICONTROL Proyectos]**. |
| ¿Qué sucede si un destinatario se coloca en una función como individuo y otra como miembro de un grupo? | Si un destinatario se coloca en varias funciones, siempre recibirá la experiencia más alta. Por ejemplo, si a un destinatario se le asigna la función **[!UICONTROL Editar original]** como persona individual y la función **[!UICONTROL Puede ver]** como miembro de un grupo, recibirá una experiencia de proyecto **[!UICONTROL Editar original]**. |
| ¿Qué experiencia obtiene un destinatario si abre un vínculo de proyecto? | Los Destinatarios reciben la función que les ha asignado en el modal de uso compartido. Si a un destinatario no se le asigna una función y recibe un enlace al proyecto (**[!UICONTROL Compartir]** > **[!UICONTROL Compartir con usuarios de Workspace]**, a continuación, seleccione **[!UICONTROL Copiar]** junto al campo **[!UICONTROL Compartir por enlace]**), se le asignará una función predeterminada. Los administradores reciben **[!UICONTROL Editar original]** y los no administradores reciben **[!UICONTROL Editar copia]**. |
