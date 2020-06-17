---
description: Uso compartido de proyectos y funciones de proyectos en Workspace
keywords: Analysis Workspace sharing
title: Compartir proyectos de Workspace
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 10%

---


# Compartir proyectos de Workspace

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

El uso compartido hace que un proyecto esté disponible para otros usuarios Analysis Workspace de su organización. Cualquier [depuración](curate.md) que haya aplicado se verá reflejada cuando los destinatarios abran el proyecto.

## Funciones de proyecto

Puede agregar destinatarios a una de las tres funciones del proyecto. Las funciones de proyecto están vinculadas al usuario y al ID de proyecto específico.

>[!NOTE]
> Las funciones de proyecto son independientes de los permisos de usuario administrados en la consola de administración de Experience Cloud.

| Función | Control de proyecto |
|---|---|
| Se puede editar | Los destinatarios pueden Guardar cambios en un proyecto y en una funcionalidad como copropietarios.<br>Esta función es útil si desea colaborar con compañeros en un proyecto. |
| Se puede duplicar | Los destinatarios pueden Guardar como y tienen acceso al panel izquierdo. Las interacciones son ilimitadas.<br>Esta función es útil si desea compartir un proyecto con usuarios que comprendan los datos de su organización y cómo usar Analysis Workspace, pero no desea que se modifique el proyecto guardado. |
| Se puede ver | Los Destinatarios no pueden guardar como y no tienen acceso al carril izquierdo. Las interacciones también son limitadas.<br>Esta función resulta útil si desea compartir un proyecto con usuarios menos familiarizados con la estructura de datos de su organización, con el Analysis Workspace o con Adobe Analytics en general. Sin embargo, aún desea que consuman datos y perspectivas en un entorno seguro.<br>Obtenga más información sobre la experiencia [del proyecto](/help/analysis-workspace/curate-share/view-only-projects.md)Can vista. |

### No se ha asignado ninguna función

Si a un destinatario no se le asigna una función y recibe un vínculo al proyecto ([!UICONTROL Compartir] > [!UICONTROL Obtener vínculo]de proyecto), se colocará en la función [!UICONTROL &quot;vista posible&quot;] de forma predeterminada.

### Múltiples funciones asignadas

Si un destinatario se coloca en varios roles, siempre tendrá el control más alto. Esto puede ocurrir si se agrega un usuario como individuo y como parte de un grupo. Por ejemplo, si se proporcionan las funciones Puede editar y [!UICONTROL &quot;Puede vista&quot;] , el usuario 1 tendrá el control [!UICONTROL &quot;Puede editar&quot;] del proyecto.

### Administradores y funciones

Los administradores ubicados en una función [!UICONTROL&quot;Puede duplicado&quot;] o [!UICONTROL &quot;Puede vista&quot;] recibirán esas experiencias limitadas cuando abran un proyecto. Si lo desea, un administrador puede aumentar su función a [!UICONTROL &quot;Puede editar&quot;] en cualquier momento mediante [!UICONTROL Componentes] > [!UICONTROL Proyectos].

## Añadir destinatarios a un proyecto compartido

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

## Compartir en grupos de destinatarios

Todos los usuarios pueden compartir proyectos con grupos, que son una colección de destinatarios. En Adobe Analytics, los grupos se definen por perfiles de producto en Adobe Experience Cloud.

* Los administradores pueden compartir con cualquier grupo, incluido &quot;Todos&quot;.
* Los no administradores pueden compartir con los grupos de los que son miembros, a excepción de &quot;Todos&quot;.

## Compartir proyectos en el administrador de proyectos

Los proyectos también se pueden compartir desde [!UICONTROL Componentes] > [!UICONTROL Proyectos]. Un solo proyecto se puede compartir siguiendo los mismos pasos descritos anteriormente.

Si se seleccionan varios proyectos para compartirlos, se agregarán destinatarios a la lista de destinatarios existente para cada proyecto. Por ejemplo:

* El proyecto A se comparte con los usuarios 1, 2, 3
* El proyecto B se comparte con el usuario 4, 5, 6
* Con el proyecto A y B seleccionado, los usuarios 4 y 7 se agregan a las listas de destinatario. La nueva lista de destinatario para cada proyecto ahora es:
   * Proyecto A: 1, 2, 3, 4, 7
   * Proyecto B: 4, 5, 6, 7
   ![](assets/mult-proj-sharing.png)
