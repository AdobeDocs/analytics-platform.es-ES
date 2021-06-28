---
description: Uso compartido de proyectos y funciones de proyectos en Workspace
keywords: Uso compartido en Analysis Workspace
title: Compartir proyectos
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: 8cee89a8ed656ad6376e64c8327aa7c94a937ce9
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 92%

---

# Compartir proyectos

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Al compartir, hace que este proyecto esté disponible para otros usuarios de Analysis Workspace de su organización. Cualquier [depuración](curate.md) que haya aplicado se verá reflejada cuando los destinatarios abran el proyecto.

## Funciones de proyecto {#Roles}

Puede agregar destinatarios a una de las tres funciones del proyecto. Las funciones de proyecto están vinculadas al usuario y al ID de proyecto específico. Las funciones de proyecto son independientes de los permisos de usuario administrados en [Admin Console de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

| Función | Control de proyecto |
|---|---|
| Se puede editar | Los destinatarios pueden **[!UICONTROL Guardar]** cambios en un proyecto y en una funcionalidad como copropietarios. Esta función resulta útil si desea administrar un proyecto conjuntamente con otros compañeros. Esto incluye editar, eliminar y modificar listas de destinatario para un proyecto compartido. <br>Nota: Actualmente, Analysis Workspace no admite la colaboración en tiempo real, por lo que se recomienda que solo un usuario edite un proyecto a la vez. Si los proyectos se guardan al mismo tiempo, se conservará la última versión. |
| Se puede duplicar | Los Destinatarios pueden usar la opción **[!UICONTROL Guardar como]** y acceder al carril izquierdo. Las interacciones del proyecto no están limitadas en esta función. Esta función es útil si desea compartir un proyecto con usuarios que comprendan los datos de su organización y cómo usar Analysis Workspace, pero no desea que el proyecto se modifique. |
| Se puede ver | Los destinatarios no pueden Guardar como y no tienen acceso al panel izquierdo. Las interacciones del proyecto también están limitadas. Esta función es útil si desea compartir un proyecto con usuarios menos familiarizados con la estructura de datos de su organización, Analysis Workspace o Customer Journey Analytics en general. Sin embargo, aún desea que consuman datos y perspectivas en un entorno seguro.<br>Obtenga más información sobre la [la función de proyecto “Puede ver”](/help/analysis-workspace/curate-share/view-only-projects.md). |

>[!IMPORTANT]
> Los destinatarios del proyecto agregados antes del 18 de junio de 2020 se han migrado a una función de proyecto. Los usuarios administradores migraron a la función **[!UICONTROL Puede editar]** y los usuarios no administradores se migraron a la función **[!UICONTROL Puede duplicar]**. Estas funciones proporcionan la misma experiencia de proyecto que antes. Además, todos los grupos (incluido “Todos”) se migraron a la función **[!UICONTROL Puede duplicar]**.

### No se ha asignado ninguna función (destinatarios de vínculo del proyecto)

Si a un destinatario no se le asigna una función y recibe un [vínculo](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=es) al proyecto (**[!UICONTROL Compartir] > [!UICONTROL Obtener vínculo de proyecto]**), se le asignará una función de forma predeterminada. Los administradores reciben la función **[!UICONTROL Puede editar]** y los usuarios no administradores reciben la función **[!UICONTROL Puede duplicar]**.

### Múltiples funciones asignadas

Si un destinatario se coloca en varias funciones, siempre obtendrá la experiencia más alta. Esto puede ocurrir si se agrega un destinatario como individuo y como parte de un grupo. Por ejemplo, si a un destinatario se le asigna la función **[!UICONTROL Puede editar]** como individuo y la función **[!UICONTROL Puede ver]** como miembro de un grupo, recibirá una experiencia **[!UICONTROL Puede editar]** en el proyecto.

### Administradores y funciones

Los administradores con una función **[!UICONTROL Puede duplicar]** o **[!UICONTROL Puede ver]** recibirán esas experiencias limitadas cuando abran un proyecto. Si lo desea, un administrador puede aumentar su función a **[!UICONTROL Puede editar]** en cualquier momento mediante **[!UICONTROL Componentes] > [!UICONTROL Proyectos]**.

## Añadir destinatarios a un proyecto compartido {#Add}

Para agregar destinatarios al proyecto compartido:

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Compartir proyecto]**.
Si hay cambios sin guardar, se le pedirá que guarde primero el proyecto.
1. Añadir destinatarios o grupos de destinatarios.
Consulte el icono de ayuda en la parte superior para ver las descripciones de cada función.
1. (Opcional) Comparta componentes de proyecto incrustados (filtros, métricas calculadas e intervalos de fechas) con todos los destinatarios.
Después de compartirlos, estos componentes aparecerán en el menú desplegable de componentes de Workspace del destinatario. Tenga en cuenta que esta configuración no se mantiene, se trata de una acción concreta usada en el momento de compartir.
1. Si lo desea, puede configurar esta página como la página de aterrizaje para destinatarios.
Esta configuración no se mantiene, se trata de una acción concreta usada en el momento de compartir.
1. Haga clic en Compartir.
También puede hacer clic en **[!UICONTROL Depurar y compartir]** para aplicar la depuración del proyecto automáticamente. Si un proyecto ya se ha compartido, estos botones indicarán **[!UICONTROL Actualizar]** y **[!UICONTROL Depurar y actualizar]**. Obtenga más información sobre la [depuración del proyecto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html).

![](assets/share-proj-modal.png)

## Compartir en grupos de destinatarios {#Groups}

Todos los usuarios pueden compartir proyectos con grupos, que son una recopilación de destinatarios. En el Customer Journey Analytics, los grupos se definen mediante perfiles de producto en [Adobe Experience Cloud admin console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

* Los administradores pueden compartir con cualquier grupo, incluido “Todos”.
* Los no administradores pueden compartir con los grupos de los que son miembros, excepto con el grupo “Todos”.

## Compartir un vínculo a un proyecto {#Links}

Puede obtener un vínculo a un proyecto en **[!UICONTROL Compartir] > [!UICONTROL Obtener vínculo del proyecto]**. Cuando se hace clic, se requiere que los destinatarios inicien sesión antes de aterrizar en el proyecto. Si el destinatario no se ha colocado en una función, recibirá una función predeterminada. Los administradores reciben la función **[!UICONTROL Puede editar]** y los usuarios no administradores reciben la función **[!UICONTROL Puede duplicar]**. [Obtenga más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) sobre la creación de vínculos que se pueden compartir a proyectos de Workspace.

## Compartir proyectos en el administrador de proyectos {#Manager}

Los proyectos también se pueden compartir desde **[!UICONTROL Componentes] > [!UICONTROL Proyectos]**. Un solo proyecto se puede compartir siguiendo los mismos pasos descritos anteriormente.  Si se seleccionan varios proyectos para compartirlos, se agregarán destinatarios a la lista de destinatarios existente para cada proyecto.

Por ejemplo:

* El proyecto A se comparte con los destinatarios 1, 2 y 3
* El proyecto B se comparte con los destinatarios 4, 5 y 6

Con el proyecto A y B seleccionado, los destinatarios 4 y 7 se agregan a las listas de uso compartido. La nueva lista de uso compartido para cada proyecto ahora es:

* Proyecto A: 1, 2, 3, 4, 7
* Proyecto B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Preguntas frecuentes {#FAQs}

| Pregunta | Respuesta |
|---|---|
| ¿Qué sucede si dos editores guardan un proyecto al mismo tiempo? | Los cambios no se combinan y se conservará la última versión guardada del proyecto. Actualmente, Analysis Workspace no admite la colaboración en tiempo real. |
| Como administrador, ¿qué experiencia de proyecto veré? | Los administradores con una función **[!UICONTROL Puede duplicar]** o **[!UICONTROL Puede ver]** recibirán esas experiencias limitadas cuando abran un proyecto. Si lo desea, un administrador puede aumentar su función a **[!UICONTROL Puede editar]** en cualquier momento mediante **[!UICONTROL Componentes] > [!UICONTROL Proyectos]**. |
| ¿Qué sucede si un destinatario se coloca en una función como individuo y otra como miembro de un grupo? | Si un destinatario se coloca en varias funciones, siempre recibirá la experiencia más alta. Por ejemplo, si a un destinatario se le asigna la función **[!UICONTROL Puede editar]** como individuo y la función **[!UICONTROL Puede ver]** como miembro de un grupo, recibirá una experiencia **[!UICONTROL Puede editar]** en el proyecto. |
| ¿Qué experiencia obtiene un destinatario si abre un vínculo de proyecto? | Los Destinatarios reciben la función que les ha asignado en el modal de uso compartido. Si a un destinatario no se le asigna una función y recibe un vínculo al proyecto (**[!UICONTROL Compartir] > [!UICONTROL Obtener vínculo de proyecto]**), se le asignará una función de forma predeterminada. Los administradores reciben la función **[!UICONTROL Puede editar]** y los usuarios no administradores reciben la función **[!UICONTROL Puede duplicar]**. |
