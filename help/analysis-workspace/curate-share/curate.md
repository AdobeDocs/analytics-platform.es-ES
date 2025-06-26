---
description: Una depuración le permite limitar los componentes antes de compartir un proyecto.
keywords: Revisión de Analysis Workspace
title: Depurar proyectos de
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: f940e5cba11df0ff158093a503213ff1641b1c5d
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 55%

---

# Depurar proyectos de

La depuración permite limitar los componentes (dimensiones, métricas, segmentos e intervalos de fechas) antes de compartir un proyecto. Cuando un destinatario abre el proyecto, ve un conjunto limitado de componentes que ha seleccionado para ellos. La depuración es un paso opcional pero recomendado antes de compartir un proyecto.

>[!NOTE]
> Los perfiles de productos son el mecanismo principal que controla los componentes que puede ver un usuario. Se administran a través de [Admin Console de Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/core-services/interface/administration/admin-tool-experience-cloud). La depuración es un segmento secundario.

## Aplicar depuración de proyecto

1. Seleccione **[!UICONTROL Compartir]** > **[!UICONTROL Depurar datos de proyectos]**.
Los componentes que se utilizan en el proyecto se añaden automáticamente.
Si un proyecto tiene varias vistas de datos, verá un destino de colocación depurada para cada vista de datos del proyecto.
1. (Opcional) Para agregar más componentes, arrastre los componentes que desee compartir desde el panel izquierdo a la zona de colocación de **[!UICONTROL Depurar componentes]** para la vista de datos.
1. Seleccione **[!UICONTROL Listo]**.

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![Ventana Depurar componentes que muestra los componentes en uso del proyecto.](assets/curation-field.png)

Cuando un destinatario abre un proyecto depurado, solo ve el conjunto depurado de componentes que ha definido:


## Eliminar depuración del proyecto

Para eliminar la depuración del proyecto y restaurar el conjunto completo de componentes en el panel izquierdo:

1. Seleccione **[!UICONTROL Compartir]** > **[!UICONTROL Depurar datos de proyectos]**.
1. Seleccione **[!UICONTROL Quitar revisión]**.
1. Seleccione **[!UICONTROL Listo]**.

## Opciones de depuración de componentes

En un proyecto depurado, el destinatario tiene la opción de **[!UICONTROL Mostrar todos]** los componentes en el panel izquierdo. [!UICONTROL Mostrar todo] revela diferentes conjuntos de componentes, según:

* Nivel de permiso del usuario (administrador o no administrador)
* Función del proyecto (propietario/editor o no)
* Tipo de depuración aplicada (en el nivel de proyecto)

| Tipo de depuración | El administrador puede ver | El propietario del proyecto que no es administrador (o la función de edición) puede ver | La función duplicada que no es de administrador puede ver |
| --- | --- | --- | --- |
| **Componentes *ocultos* de una vista de datos** | Todos los componentes de vista de datos están disponibles para la creación de informes (los ocultos requieren que seleccione **[!UICONTROL Mostrar todo]**) | No disponible para la creación de informes | No disponible para la creación de informes |
| **Componentes añadidos o eliminados de una vista de datos** | Solo los componentes añadidos a la vista de datos (ocultos o no ocultos). Los administradores no pueden informar sobre campos o componentes que no estén definidos en la vista de datos. | Solo los componentes añadidos a la vista de datos o los componentes propiedad del usuario o compartidos con él. Los componentes ocultos no están disponibles (como la depuración del grupo de informes virtuales). | Solo los componentes agregados a la vista de datos no se ocultan y se incluyen en la depuración del proyecto. |
| **Componentes depurados en un proyecto** | Todos los componentes de vista de datos disponibles para informes (los ocultos requieren que seleccione **[!UICONTROL Mostrar todo]**) | Todos los componentes de vista de datos no ocultos (requiere hacer clic en Mostrar todo) | Solo los componentes depurados, además de los componentes que sean propiedad del usuario o que se compartan con él |
| **Proyecto depurado mediante una vista de datos con componentes ocultos** | Todos los componentes de datos disponibles para los informes (los ocultos y no depurados requieren que seleccione **[!UICONTROL Mostrar todo]**) | Todos los componentes de proyecto no depurados, todos los componentes de vista de datos no ocultos y cualquier componente propiedad del usuario o compartido con él | Solo los componentes depurados, además de los componentes que sean propiedad del usuario o que se compartan con él |
