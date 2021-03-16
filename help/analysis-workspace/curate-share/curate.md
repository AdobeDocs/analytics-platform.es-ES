---
description: Una depuración le permite limitar los componentes antes de compartir un proyecto.
keywords: Revisión de Analysis Workspace
title: Depurar proyectos de
translation-type: tm+mt
source-git-commit: 1fd11bf0f34b9e4698285e5d29fd57fbab5238be
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 50%

---


# Depurar proyectos de

La depuración permite limitar los componentes (dimensiones, métricas, segmentos e intervalos de fechas) antes de compartir un proyecto. Cuando un destinatario abre el proyecto, verá un conjunto limitado de componentes que ha seleccionado para ellos. La depuración es un paso opcional pero recomendado antes de compartir un proyecto.

>[!NOTE]
> Los perfiles de productos son el mecanismo principal que controla los componentes que puede ver un usuario. Se administran mediante el [Admin Console de Adobe Experience Cloud](https://docs.adobe.com/content/help/es-ES/core-services/interface/manage-users-and-products/admin-getting-started.html). La depuración es un filtro secundario.

## Aplicar depuración de proyecto

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Depurar datos del proyecto]**.
Los componentes que se utilizan en el proyecto se añadirán automáticamente.
   **Nota**: Si un proyecto tiene varios grupos de informes, verá un campo de selección para cada grupo de informes en el proyecto.
1. (Opcional) Para agregar más componentes, arrastre los componentes que desee compartir desde el carril izquierdo al campo [!UICONTROL Depurar componentes].
1. Haga clic en **[!UICONTROL Finalizado]**.

La depuración también se puede aplicar desde el menú [!UICONTROL Compartir] haciendo clic en **[!UICONTROL Depurar y Compartir]**. Esta opción depura automáticamente el proyecto en los componentes que se utilizan en el proyecto. Puede agregar componentes adicionales siguiendo los pasos anteriores.

![](assets/curation-field.png)

## Vista de un proyecto depurado

Cuando un destinatario abre un proyecto depurado, solo verá el conjunto depurado de componentes que haya definido:

![](assets/curate-project.png)

## Eliminar depuración del proyecto

Para eliminar la depuración del proyecto y restaurar el conjunto completo de componentes en el carril izquierdo:

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Depurar datos del proyecto]**.
1. Haga clic en **[!UICONTROL Eliminar depuración]**.
1. Haga clic en **[!UICONTROL Finalizado]**.

## Opciones de depuración de componentes

En un proyecto depurado, se mostrará al destinatario la opción **[!UICONTROL Mostrar todos los componentes]** en el carril izquierdo. [!UICONTROL Mostrar todo] revela diferentes conjuntos de componentes, según:

* Nivel de permiso del usuario (administrador o no administrador)
* Función del proyecto (propietario/editor o no)
* Tipo de depuración aplicada (a nivel de proyecto)

| Tipo de depuración | El administrador puede ver | El propietario del proyecto que no es administrador (o la función de edición) puede ver | La función duplicada que no es de administrador puede ver |
| --- | --- | --- | --- |
| **Componentes &quot;ocultos&quot; de una vista de datos** | Todos los componentes de vista de datos disponibles para la creación de informes (los componentes ocultos requieren hacer clic en &quot;Mostrar todo&quot;) | No disponible para informes | No disponible para informes |
| **Componentes agregados o eliminados de una vista de datos** | Solo los componentes agregados a la vista de datos (ocultos o no ocultos). Los administradores no pueden informar sobre campos o componentes que no estén definidos por la vista de datos. | Solo los componentes agregados a la vista de datos o los componentes propiedad del usuario o compartidos con él. Los componentes ocultos no están disponibles (como la depuración de VRS). | Solo los componentes añadidos al DV no se ocultan y se incluyen en la depuración del proyecto. |
| **Componentes depurados en un proyecto** | Todos los componentes de vista de datos disponibles para la creación de informes (los componentes ocultos requieren hacer clic en &quot;Mostrar todo&quot;) | Todos los componentes de vista de datos no ocultos (requiere hacer clic en &quot;mostrar todo&quot;) | Solo los componentes depurados, además de los componentes que sean propiedad del usuario o que se compartan con él |
| **Proyecto depurado mediante una vista de datos con componentes ocultos** | Todos los componentes de datos disponibles para la creación de informes (los componentes ocultos y no depurados requieren hacer clic en &quot;Mostrar todo&quot;) | Todos los componentes de proyecto no depurados, todos los componentes de vista de datos no ocultos y cualquier componente propiedad del usuario o compartido con él | Solo los componentes depurados, además de los componentes que sean propiedad del usuario o que se compartan con él |

