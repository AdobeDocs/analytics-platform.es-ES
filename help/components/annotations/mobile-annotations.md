---
title: Anotaciones de cuadros de resultados móviles
description: Aprenda a mostrar anotaciones en cuadros de resultados móviles.
solution: Customer Journey Analytics
feature: Components
exl-id: c0f276b4-3514-4f93-8b6c-6896eb4da6e4
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '402'
ht-degree: 100%

---


# Compartir anotaciones en cuadros de resultados móviles

Puede mostrar anotaciones creadas en Workspace en cuadros de resultados móviles. Esto le permite compartir matices de datos contextuales y perspectivas sobre su organización y campañas directamente en proyectos de cuadros de resultados móviles, visibles en la aplicación móvil de paneles de Analytics.

## Anotaciones de superficie en cuadros de resultados móviles

Para que aparezcan anotaciones en cuadros de resultados móviles, primero cree la anotación desde proyectos de Workspace o desde el menú de componentes.

Para obtener información sobre la creación de anotaciones, consulte [Crear anotaciones](create-annotations.md). Las anotaciones están desactivadas en los cuadros de resultados móviles de forma predeterminada y deben habilitarse para cada cuadro de resultados que desee que aparezca en los cuadros de resultados móviles.

1. Activar anotaciones. Para activar las anotaciones, consulte [Activar o desactivar anotaciones](overview.md#annotations-on-off).

1. Cree una anotación y asegúrese de que se comparta con todos sus proyectos. Para crear una anotación en Workspace, consulte [Crear anotaciones](create-annotations.md).

1. Seleccione **[!UICONTROL Mostrar anotaciones]** para mostrar la anotación en los cuadros de resultados móviles.

   ![Opciones de anotaciones para móviles para cuadros de resultados.](assets/show-annotations.png)

1. Confirme que la opción mostrar anotaciones esté seleccionada y vaya a **[!UICONTROL Proyecto]** > **[!UICONTROL Información y configuración del proyecto]**.

   ![Opciones de anotaciones para móviles para la información y la configuración del proyecto que resaltan la opción Mostrar anotaciones.](assets/project-info-settings.png)

## Ver anotaciones en cuadros de resultados móviles

Cuando las anotaciones están activadas, los iconos de anotación se pueden ver en el Generador de cuadros de resultados. Las anotaciones solo aparecen en los gráficos y tablas de la vista detallada. Las anotaciones no están visibles desde la vista de mosaico principal del cuadro de resultados.

![Creador de cuadros de resultados que resalta los iconos de anotación.](assets/view-annotations.png)

Cuando los iconos de anotación están visibles, no se puede ver ni interactuar con las anotaciones en el lienzo del generador. Utilice el modo de vista previa para ver e interactuar con anotaciones tal y como aparecen en la aplicación. ![Icono de vista previa](assets/preview-icon.png)

Los colores de anotación se seleccionan cuando la anotación se crea en el espacio de trabajo. Las anotaciones grises indicaban la presencia de más de una anotación. ![Iconos de anotación](assets/gray-annotations1.png) ![Cuadro de resultados para móviles con el icono de anotación resaltado.](assets/gray-annotations2.png)

## Ver anotaciones de gráfico

| Fecha | Aspecto |
| --- | --- |
| **[!UICONTROL Un solo día]** | ![](assets/single-day-mobile-annotations.png)<br></br> |
| **[!UICONTROL Intervalo de fechas]** | ![](assets/date-range.png) |
| **[!UICONTROL Anotaciones superpuestas]** | ![](assets/overlapping-annotations.png)<br></br>Para ver los detalles de las anotaciones en la aplicación de paneles de Analytics, pulse un icono de anotación. <br></br>Cuando vea una anotación en un gráfico, puede deslizar hacia la izquierda y hacia la derecha para navegar por todas las anotaciones presentes en el gráfico. Cuando vea una anotación en la tabla, deslice a izquierda y derecha para navegar por todas las anotaciones asociadas con ese elemento de fila en la tabla. <br></br>![](assets/swipe-multiple-annotations.png) <br></br>En gráficos que no tienen un *eje x* basado en el tiempo, como los gráficos de barras circulares u horizontales, las anotaciones que se aplican al gráfico se pueden ver tocando el icono situado en la esquina inferior derecha.<br></br> ![](assets/charts-without-timebase.png) |
