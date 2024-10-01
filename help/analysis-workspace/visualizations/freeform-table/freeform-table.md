---
title: Resumen de tabla de forma libre
description: Las tablas de forma libre son la base del análisis de datos en Workspace
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 21%

---

# Resumen de tabla de forma libre

En Analysis Workspace, una visualización de ![Tabla](/help/assets/icons/Table.svg) **[!UICONTROL tabla de forma libre]** es la base del análisis de datos interactivo. Puede arrastrar y soltar una combinación de [componentes](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components) en filas y columnas para crear una tabla personalizada para su análisis. A medida que se suelta cada componente, la tabla se actualiza inmediatamente para que pueda analizar rápidamente y explorar en mayor profundidad.

![Tabla de forma libre que muestra componentes en filas y columnas, incluidas visitas y pedidos en línea de varias páginas web.](assets/opening-section.png)

Para crear y configurar una [!UICONTROL tabla de forma libre]:

* Agregue una visualización ![Tabla](/help/assets/icons/Table.svg) **[!UICONTROL Tabla de forma libre]**. Consulte [Agregar una visualización a un panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Tablas automatizadas

La forma más rápida de crear una tabla es soltar componentes directamente en un proyecto, panel o tabla de forma libre en blanco. Se ha creado una tabla de forma libre en un formato recomendado. [Vea el tutorial](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![Se colocó un nuevo panel con el componente de visitas en el espacio de trabajo.](assets/automated-table.png)

## Generador de tablas de forma libre

Si prefiere primero agregar varios componentes a la tabla y luego procesar los datos, puede seleccionar **[!UICONTROL Habilitar generador de tablas]**. Con el generador habilitado, puede arrastrar y soltar dimensiones, desgloses, métricas y filtros para crear tablas que respondan a preguntas más complejas. Se actualizarán los datos cuando seleccione **[!UICONTROL Generar]**.

![Generador de tablas de forma libre que muestra ](assets/table-builder.png)

## Interacciones

Puede interactuar con una tabla de forma libre y personalizarla de diversas maneras:

### Filtrar y ordenar

* Puede [filtrar y ordenar](filter-and-sort.md) los datos de una tabla.

### Filas

* Puede [crear rápidamente una nueva visualización](../freeform-analysis-visualizations.md#visualize) a partir de una o más filas usando ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg).
* Puede visualizar más filas en una sola pantalla ajustando la [densidad de vista](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) del proyecto.
* Cada fila de dimensión puede mostrar hasta 400 filas antes de que se produzca la paginación. Seleccione el número que hay junto a **[!UICONTROL Filas]** en el encabezado de la primera columna para mostrar más filas en una página. Vaya a otra página con ![ChevronRight](/help/assets/icons/ChevronRight.svg) en el encabezado de la primera columna.
* Puede desglosar filas por componentes adicionales. Para desglosar muchas filas a la vez, seleccione varias filas y, a continuación, arrastre el siguiente componente sobre las filas seleccionadas. Obtenga más información sobre los [desgloses](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa).
* Las filas se pueden [filtrar](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort) para mostrar un conjunto reducido de elementos. Hay opciones de configuración adicionales disponibles en [Configuración de fila](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings).

### Columnas

* Los componentes se pueden apilar en columnas para crear métricas filtradas, análisis entre pestañas, etcétera.
* La vista de cada columna se ajusta en la [configuración de columna](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/column-settings).
* Hay varias acciones disponibles a través del [menú contextual](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/right-click-for-workspace-efficiency). El menú proporciona diferentes acciones en función de si selecciona el encabezado de tabla, las filas o las columnas.


## Configuración

Seleccione ![Setting](/help/assets/icons/Setting.svg) para mostrar **[!UICONTROL Configuración de tabla]**. Están disponibles las siguientes opciones específicas de visualización [settings](../freeform-analysis-visualizations.md#settings):

### Fuente de datos

| Opción | Descripción |
|---|---|
| **[!UICONTROL Visualizaciones vinculadas]**. | Enumera todas las visualizaciones vinculadas. |
| **[!UICONTROL Mostrar origen de datos]** | Cuando está desmarcada, la tabla de forma libre que funciona como fuente de datos para la visualización está oculta en Workspace. |

### Configuración

| Opción | Descripción |
|---|---|
| **[!UICONTROL Alinear fechas de cada columna para que todas empiecen en la misma fila]** | Para alinear o no alinear fechas de cada columna con todas a partir de la misma fila. |


## Menú contextual

Las siguientes opciones de [menú contextual](../freeform-analysis-visualizations.md#context-menu) están disponibles en el encabezado de la visualización:

| Opción | Descripción |
| --- | --- |
| **[!UICONTROL Insertar visualización copiada]**n | Pegue (inserte) una visualización copiada en otro lugar del proyecto o en un proyecto completamente diferente. |
| **[!UICONTROL Copiar datos al portapapeles]** | Copie los datos de la visualización en el portapapeles. |
| **[!UICONTROL Copiar selección al portapapeles]** | Copie la selección de la visualización en el portapapeles. |
| **[!UICONTROL Descargar elementos como CSV (*nombre de dimensión*)]** | Descargue inmediatamente los elementos de dimensión (hasta un máximo de 50 000) de la visualización en su dispositivo local. Un máximo de 50 000 elementos de dimensión para la dimensión seleccionada. |
| **[!UICONTROL Copiar visualización]** | Copie la visualización para poder insertarla en otro lugar del proyecto o en un proyecto completamente diferente. |
| **[!UICONTROL Descargar CSV de datos]** | Descargue inmediatamente los datos mostrados de la visualización en su dispositivo local. |
| **[!UICONTROL Exportar tabla completa...]** | Exporte la tabla completa a las ubicaciones de nube designadas. Ver [Exporta informes de Customer Journey Analytics a la nube](../../export/export-cloud.md) |
| **[!UICONTROL Duplicar visualización]** | Cree un duplicado exacto de la visualización. |
| **[!UICONTROL Editar descripción]** | Añada (o edite) una descripción de texto para la visualización. Ver [Texto](../text.md). |
| **[!UICONTROL Obtener vínculo de visualización]** | Copie y comparta un vínculo directamente en la visualización. El cuadro de diálogo Compartir vínculo muestra el vínculo. Seleccione Copiar para copiar el vínculo en el portapapeles. |
| **[!UICONTROL Volver a empezar]** | Elimine la configuración de la visualización actual para poder volver a configurarla desde cero. |


>[!MORELIKETHIS]
>
>[Agregar una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configuración de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menú contextual de visualización ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
