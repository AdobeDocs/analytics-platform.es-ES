---
title: 'Anotaciones al informe de valoración móvil    '
description: Aprenda a que aparezcan anotaciones en informes de valoración móviles.
role: User, Admin
solution: Customer Journey Analytics
feature: Components
source-git-commit: 20e495040c213c5fff0450cddc1899ce340f785d
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 3%

---


# Uso compartido de anotaciones en informes de valoración móviles

>[!NOTE]
>
>Actualmente, esta función está en [prueba limitada](/help/release-notes/releases.md).

Puede mostrar anotaciones creadas en Workspace en informes de valoración móviles. Esto le permite compartir matices de datos contextuales y perspectivas sobre su organización y campañas directamente dentro de proyectos de informes de valoración móviles, visibles en la aplicación móvil de paneles de Analytics .

## Anotaciones de superficie en informes de valoración móviles

Para que aparezcan anotaciones en informes de valoración móviles, cree primero la anotación desde proyectos de Workspace o desde el menú de componentes.

Para obtener información sobre la creación de anotaciones, consulte [Crear anotaciones](create-annotations.md). Las anotaciones están desactivadas en los informes de valoración móviles de forma predeterminada y deben habilitarse para cada informe de valoración que desee que aparezca en los informes de valoración móviles.

1. Activar anotaciones. Para activar las anotaciones, consulte [Activar o desactivar anotaciones](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=en#turn-annotations-on-or-off).

1. Cree una anotación y asegúrese de que se comparta con todos sus proyectos. Para crear una anotación en Workspace, consulte [Crear anotaciones](create-annotations.md).

1. Select **Mostrar anotaciones** para mostrar la anotación en los informes de valoración móviles.

![](assets/show-annotations.png)

1. Confirme que la opción mostrar anotaciones está seleccionada y vaya a **Proyecto** > **Información y configuración del proyecto**.

![](assets/project-info-settings.png)

## Ver anotaciones en informes de valoración móviles

Cuando las anotaciones están activadas, los iconos de anotación se pueden ver en el Generador de informes de valoración. Las anotaciones aparecen únicamente en los gráficos y tablas de la vista detallada. Las anotaciones no están visibles desde la vista de mosaico principal del informe de valoración.

![](assets/view-annotations.png)

Cuando los iconos de anotación están visibles, no se puede ver ni interactuar con las anotaciones en el lienzo del generador. Utilice el modo de vista previa para ver e interactuar con anotaciones tal y como aparecen en la aplicación. ![](assets/preview-icon.png)

Los colores de anotación se seleccionan cuando la anotación se crea en el espacio de trabajo. Las anotaciones grises indicaban la presencia de más de una anotación. ![](assets/gray-annotations1.png) ![](assets/gray-annotations2.png)

## Ver anotaciones de gráfico

| Fecha | Aspecto |
| --- | --- |
| **Día único** | ![](assets/single-day-mobile-annotations.png)<br></br> |
| **Intervalo de fechas** | ![](assets/date-range.png) |
| **Anotaciones superpuestas** | ![](assets/overlapping-annotations.png)<br></br>Para ver los detalles de las anotaciones en la aplicación de paneles de Analytics, pulse un icono de anotación. <br></br>Cuando vea una anotación en un gráfico, puede deslizar hacia la izquierda y hacia la derecha para navegar por todas las anotaciones presentes en el gráfico. Cuando vea una anotación en la tabla, deslice hacia la izquierda y la derecha para navegar por todas las anotaciones asociadas con ese elemento de fila en la tabla. <br></br>![](assets/swipe-multiple-annotations.png) <br></br>En gráficos que no tienen una base de tiempo *eje x*, como los gráficos de barras circulares u horizontales, las anotaciones que se aplican al gráfico se pueden ver tocando el icono situado en la esquina inferior derecha.<br></br> ![](assets/charts-without-timebase.png) |
