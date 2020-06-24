---
description: Uso compartido de proyectos y funciones de proyectos en Workspace
keywords: Analysis Workspace sharing
title: Compartir proyectos de Workspace
translation-type: tm+mt
source-git-commit: 92dfb091a004ca7403f67e3f16527ea1e39cd01a
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 7%

---


# Compartir proyectos de Workspace

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

El uso compartido hace que un proyecto esté disponible para otros usuarios Analysis Workspace de su organización. Cualquier [depuración](curate.md) que haya aplicado se verá reflejada cuando los destinatarios abran el proyecto.

## Funciones de proyecto {#Roles}

Puede agregar destinatarios a una de las tres funciones del proyecto. Las funciones de proyecto están vinculadas al usuario y al ID de proyecto específico. Las funciones de proyecto son independientes de los permisos de usuario administrados en la consola [de administración de](https://docs.adobe.com/content/help/es-ES/core-services/interface/manage-users-and-products/admin-getting-started.html)Adobe Experience Cloud.

| Función | Control de proyecto |
|---|---|
| Se puede editar | Los destinatarios pueden Guardar cambios en un proyecto y en una funcionalidad como copropietarios. Esta función es útil si desea co-editar proyectos con otros colegas.<br>Nota: Actualmente, Analysis Workspace no admite la colaboración en directo, por lo que se recomienda que solo un usuario edite un proyecto a la vez. Si los proyectos se guardan al mismo tiempo, se conservará la última versión. |
| Se puede duplicar | Los Destinatarios pueden guardar como y tener acceso al carril izquierdo. Las interacciones del proyecto no están limitadas en esta función. Esta función es útil si desea compartir un proyecto con usuarios que comprendan los datos de su organización y cómo usar Analysis Workspace, pero no desea que el proyecto se modifique. |
| Se puede ver | Los Destinatarios no pueden guardar como y no tienen acceso al carril izquierdo. Las interacciones del proyecto también son limitadas. Esta función resulta útil si desea compartir un proyecto con usuarios menos familiarizados con la estructura de datos de su organización, con el Analysis Workspace o con Adobe Analytics en general. Sin embargo, aún desea que consuman datos y perspectivas en un entorno seguro.<br>Obtenga más información sobre la experiencia [del proyecto](/help/analysis-workspace/curate-share/view-only-projects.md)Can vista. |

### No se ha asignado ninguna función

Si a un destinatario no se le asigna una función y recibe un vínculo al proyecto (**[!UICONTROL Compartir]>[!UICONTROL Obtener vínculo]** de proyecto), se colocará en la función de vista **** posible de forma predeterminada.

### Múltiples funciones asignadas

Si un destinatario se coloca en varias funciones, siempre obtendrá la experiencia más alta. Esto puede ocurrir si se agrega un usuario como individuo y como parte de un grupo. Por ejemplo, si a un usuario se le asigna la función **[!UICONTROL Puede editar]** como individuo y la función **[!UICONTROL Puede vista]** como miembro de un grupo, recibirá una experiencia de **[!UICONTROL edición]** del proyecto.

### Administradores y funciones

Los administradores ubicados en una función **[!UICONTROL Puede duplicado]** o **[!UICONTROL Puede vista]** recibirán esas experiencias limitadas cuando abran un proyecto. Si lo desea, un administrador puede aumentar su función en **[!UICONTROL Puede editar]** en cualquier momento mediante **[!UICONTROL Componentes]>[!UICONTROL Proyectos]**.

## Añadir destinatarios a un proyecto compartido {#Add}

Para agregar destinatarios al proyecto compartido:

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Compartir proyecto]**.
Si hay cambios sin guardar, se le pedirá que guarde primero el proyecto.
1. Añadir destinatarios o grupos de usuarios.
Consulte el icono de ayuda en la parte superior para ver las descripciones de cada función.
1. (Opcional) Comparta componentes de proyecto incrustados (segmentos, métricas calculadas e intervalos de fechas) con todos los destinatarios.
Después de compartirse, estos componentes aparecerán en la lista desplegable Componentes del espacio de trabajo del destinatario. Tenga en cuenta que esta configuración no persiste; es una acción única en el momento de compartir.
1. (Opcional) Configure esta página como la página de aterrizaje para destinatarios.
Esta configuración no se mantiene, se trata de una acción concreta usada en el momento de compartir.
1. Haga clic en Compartir.
También puede hacer clic en **[!UICONTROL Depurar y compartir]** para aplicar la depuración del proyecto automáticamente. Si un proyecto ya se ha compartido, estos botones indicarán **[!UICONTROL Actualizar]** y **[!UICONTROL Depurar y actualizar]**. Obtenga más información sobre la depuración [del](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/curate-share/curate.html)proyecto.

![](assets/share-proj-modal.png)

## Compartir en grupos de destinatarios {#Groups}

Todos los usuarios pueden compartir proyectos con grupos, que son una colección de destinatarios. En Adobe Analytics, los grupos se definen mediante perfiles de producto en la consola [de administración de](https://docs.adobe.com/content/help/es-ES/core-services/interface/manage-users-and-products/admin-getting-started.html)Adobe Experience Cloud.

* Los administradores pueden compartir con cualquier grupo, incluido &quot;Todos&quot;.
* Los no administradores pueden compartir con los grupos de los que son miembros, a excepción de &quot;Todos&quot;.

## Compartir proyectos en el administrador de proyectos {#Manager}

Los proyectos también se pueden compartir desde **[!UICONTROL Componentes]>[!UICONTROL Proyectos]**. Un solo proyecto se puede compartir siguiendo los mismos pasos descritos anteriormente.

Si se seleccionan varios proyectos para compartirlos, se agregarán destinatarios a la lista de destinatarios existente para cada proyecto. Por ejemplo:

* El proyecto A se comparte con los usuarios 1, 2, 3
* El proyecto B se comparte con el usuario 4, 5, 6
* Con el proyecto A y B seleccionado, los usuarios 4 y 7 se agregan a las listas de destinatario. La nueva lista de destinatario para cada proyecto ahora es:
   * Proyecto A: 1, 2, 3, 4, 7
   * Proyecto B: 4, 5, 6, 7

   ![](assets/mult-proj-sharing.png)

## Preguntas frecuentes {#FAQs}

| Pregunta | Respuesta |
|---|---|
| ¿Qué sucede si dos editores guardan un proyecto al mismo tiempo? | Los cambios no se combinan y se conservará la última versión guardada del proyecto. Actualmente, Analysis Workspace no admite la colaboración en directo. |
| Como administrador, ¿qué experiencia de proyecto veré? | Los administradores ubicados en una función **[!UICONTROL Puede duplicado]** o **[!UICONTROL Puede vista]** recibirán esas experiencias limitadas cuando abran un proyecto. Si lo desea, un administrador puede aumentar su función en **[!UICONTROL Puede editar]** en cualquier momento mediante **[!UICONTROL Componentes]>[!UICONTROL Proyectos]**. |
| ¿Qué sucede si un usuario se coloca en una función como individuo y en otra como miembro de un grupo? | Si un destinatario se coloca en varias funciones, siempre recibirá la experiencia más alta. Por ejemplo, si a un usuario se le asigna la función **[!UICONTROL Puede editar]** como individuo y la función **[!UICONTROL Puede vista]** como miembro de un grupo, recibirá una experiencia de **[!UICONTROL edición]** del proyecto. |
| ¿Por qué un usuario recibe una experiencia de solo Vista cuando obtiene un vínculo de proyecto? | Si a un destinatario no se le asigna una función y recibe un vínculo al proyecto (**[!UICONTROL Compartir]>[!UICONTROL Obtener vínculo]** de proyecto), se colocará en la función de vista **** posible de forma predeterminada. Si el usuario desea un rol de proyecto mayor, el propietario o editor del proyecto puede agregarlo al duplicado Can o al rol Can edit a través del modal Project share. |
