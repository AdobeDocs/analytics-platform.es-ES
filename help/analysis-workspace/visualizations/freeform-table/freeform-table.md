---
title: Tabla de forma libre
description: Las tablas de forma libre son la base del análisis de datos en Workspace
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 90%

---

# Tabla de forma libre

En Analysis Workspace, una tabla de forma libre es la base del análisis de datos interactivo. Puede arrastrar y soltar una combinación de [componentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=es) en filas y columnas para crear una tabla personalizada para su análisis. A medida que se suelta cada componente, la tabla se actualiza inmediatamente para que pueda analizar rápidamente y explorar en mayor profundidad.

![Tabla de forma libre que muestra componentes en filas y columnas, incluidas visitas y pedidos en línea de varias páginas web.](assets/opening-section.png)

## Tablas automatizadas

La forma más rápida de crear una tabla es soltar componentes directamente en un proyecto, panel o tabla de forma libre en blanco. Se creará automáticamente una tabla de forma libre en un formato recomendado. [Vea el tutorial](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html?lang=es).

![Se colocó un nuevo panel con el componente de visitas en el espacio de trabajo.](assets/automated-table.png)

## Generador de tablas de forma libre

Si prefiere primero agregar varios componentes a la tabla y luego procesar los datos, puede habilitar el Generador de tablas de forma libre. Con el generador habilitado, puede arrastrar y soltar varias dimensiones, desgloses, métricas y filtros para crear tablas que respondan a preguntas más complejas. Los datos no se actualizarán sobre la marcha, sino una vez que haga clic en **[!UICONTROL Generar]**.

![Generador de tablas de forma libre que muestra ](assets/table-builder.png)

## Interacciones de tabla

Puede interactuar con una tabla de forma libre y personalizarla de diversas maneras:

* **Filas**
   * Puede visualizar más filas en una sola pantalla ajustando la [densidad de vista](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=es) del proyecto.
   * Cada fila de dimensión puede mostrar hasta 400 filas antes de que se produzca la paginación. Haga clic en el número junto a Filas para mostrar más filas en una página. Navegue a otra página utilizando la flecha de página en el encabezado.
   * Las filas se pueden desglosar en componentes adicionales. Para desglosar muchas filas a la vez solo tiene que seleccionar varias filas y arrastrar el siguiente componente sobre las filas seleccionadas. Obtenga más información sobre los [desgloses](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html?lang=es).
   * Las filas se pueden [filtrar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=es) para mostrar un conjunto reducido de elementos. Hay opciones de configuración adicionales disponibles en [Configuración de fila](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=es).

* **Columnas**
   * Los componentes se pueden apilar en columnas para crear métricas filtradas, análisis entre pestañas, etcétera.
   * La vista de cada columna se ajusta en la [configuración de columna](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=es).
   * Hay varias acciones disponibles a través del [menú accesible mediante el botón secundario](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html?lang=es). El menú proporciona diferentes acciones en función de si se hace clic en el encabezado de tabla, en las filas o en las columnas.

## Exportar datos de tabla de forma libre

Obtenga más información sobre todas las [opciones de exportación](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=es) de datos de Analysis Workspace.

* Al hacer clic con el botón derecho en > **[!UICONTROL Copiar datos en el portapapeles]**, se exportan los datos de tabla mostrados. Si se realiza una selección de tabla, esta opción dirá **[!UICONTROL Copiar selección al portapapeles]**. La tecla de acceso directo **Ctrl + C** también copia los datos seleccionados.
* Al hacer clic con el botón derecho en > **[!UICONTROL Descargar datos como CSV]**, se descargan los datos de tabla mostrados como CSV. Si se hace una selección de tabla, esta opción indicará **[!UICONTROL Descargar selección como CSV]**.
* Al hacer clic con el botón derecho en > **[!UICONTROL Proyecto > Descargar elementos como CSV]**, se exportarán hasta 50 000 elementos de dimensión de la dimensión seleccionada.

Obtenga más información sobre todas las [opciones de exportación](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=es) de datos de Analysis Workspace.

![Tabla de forma libre que muestra las opciones de exportación y los datos de copia al portapapeles seleccionados.](assets/export-options.png)
