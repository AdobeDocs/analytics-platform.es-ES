---
title: Información general sobre las tablas de forma libre
description: Las tablas de forma libre son la base del análisis de datos en Workspace
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 100%

---

# Información general sobre las tablas de forma libre {#freeform-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="Tabla de forma libre"
>abstract="Cree una visualización de tabla de forma libre vacía que pueda elaborar con dimensiones, segmentos, métricas e intervalos de fechas. Puede utilizar la tabla de forma libre como base para otras visualizaciones."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_En este artículo se describe la visualizaciónTabla de forma libre en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consulte [Tabla de forma libre](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) para ver la versión de_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de este artículo._

>[!ENDSHADEBOX]


En Analysis Workspace, una visualización ![Tabla](/help/assets/icons/Table.svg) **[!UICONTROL Tabla de forma libre]** es la base para el análisis interactivo de datos. Puede arrastrar y soltar una combinación de [componentes](/help/components/overview.md) en filas y columnas para crear una tabla personalizada para su análisis. A medida que se suelta cada componente, la tabla se actualiza inmediatamente para que pueda analizar rápidamente y explorar en mayor profundidad.

![Tabla de forma libre que muestra los componentes en filas y columnas, incluidas las visitas y los pedidos en línea de varias páginas web.](assets/opening-section.png)

Para crear y configurar una [!UICONTROL tabla de forma libre]:

* Añada una visualización ![Tabla](/help/assets/icons/Table.svg) **[!UICONTROL Tabla de forma libre]**. Consulte [Añadir una visualización a un panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Tablas automatizadas

La forma más rápida de crear una tabla es soltar componentes directamente en un proyecto, panel o tabla de forma libre en blanco. Se creará automáticamente una tabla de forma libre en un formato recomendado. [Vea el tutorial](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![Un nuevo Panel con el componente de visitas que se ha soltado en el espacio de trabajo.](assets/automated-table.png)

## Generador de tablas de forma libre

Si prefiere primero añadir varios componentes a la tabla y luego procesar los datos, puede seleccionar **[!UICONTROL Habilitar generador de tablas de forma libre]**. Con el generador habilitado, puede arrastrar y soltar dimensiones, desgloses, métricas y segmentos para generar tablas que respondan a preguntas más complejas. Se actualizarán los datos cuando seleccione **[!UICONTROL Generar]**.

![Generador de tablas de forma libre que muestra ](assets/table-builder.png)

## Interacciones

Puede interactuar con una tabla de forma libre y personalizarla de diversas maneras:

### Filtrar y ordenar

* Puede [segmentar y ordenar](filter-and-sort.md) los datos en una tabla.

### Filas

* Puede [crear una nueva visualización](../freeform-analysis-visualizations.md#visualize) rápidamente desde una o varias filas usando ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg).
* Puede visualizar más filas en una sola pantalla ajustando la [densidad de vista](/help/analysis-workspace/build-workspace-project/view-density.md) del proyecto.
* Cada fila de dimensión puede mostrar hasta 400 filas antes de que se produzca la paginación. Seleccione el número que hay junto a **[!UICONTROL Filas]** en el encabezado de la primera columna para mostrar más filas en una página. Vaya a otra página mediante ![ChevronRight](/help/assets/icons/ChevronRight.svg) en el encabezado de la primera columna.
* Puede desglosar filas por componentes adicionales. Para desglosar muchas filas a la vez solo tiene que seleccionar varias filas y arrastrar el siguiente componente sobre las filas seleccionadas. Obtenga más información sobre los [desgloses](/help/components/dimensions/t-breakdown-fa.md).
* Las filas se pueden [segmentar](/help/components/segments/seg-overview.md) para mostrar un conjunto reducido de elementos. Hay opciones de configuración adicionales disponibles en la [Configuración de fila](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

### Columnas

* Los componentes se pueden apilar en columnas para crear métricas segmentadas, análisis entre fichas, etcétera.
* La vista de cada columna se ajusta en la [configuración de columna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
* Hay varias acciones disponibles a través del [menú contextual](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu). El menú proporciona diferentes acciones en función de si selecciona el encabezado de tabla, las filas o las columnas.


## Configuración

Seleccione ![Configuración](/help/assets/icons/Setting.svg) para mostrar **[!UICONTROL Configuración de tabla]**. Están disponibles las siguientes opciones de [configuración](../freeform-analysis-visualizations.md#settings) específicas de la visualización:

### Fuente de datos

| Opción | Descripción |
|---|---|
| **[!UICONTROL Visualizaciones vinculadas]**. | Enumera todas las visualizaciones vinculadas. |
| **[!UICONTROL Mostrar fuente de datos]** | Cuando esta opción está desmarcada, la tabla de forma libre que funciona como fuente de datos para la visualización queda oculta en Workspace. |

### Configuración

| Opción | Descripción |
|---|---|
| **[!UICONTROL Alinear fechas de cada columna para que todas empiecen en la misma fila]** | Seleccione esta opción para alinear las fechas de cada columna para que todas empiecen en la misma fila. |


## Menú contextual

Las siguientes opciones de [menú contextual](../freeform-analysis-visualizations.md#context-menu) están disponibles en el encabezado de la visualización:

| Opción | Descripción |
| --- | --- |
| **[!UICONTROL Insertar visualización copiada]**n | Pega (inserta) una visualización copiada en otro lugar dentro del proyecto o en un proyecto completamente diferente. |
| **[!UICONTROL Copiar datos en el portapapeles]** | Copia los datos de la visualización en el portapapeles. |
| **[!UICONTROL Copiar selección en el portapapeles]** | Copia la selección de la visualización en el portapapeles. |
| **[!UICONTROL Descargar elementos como CSV (*nombre de dimensión*)]** | Descarga inmediatamente los elementos de dimensión (hasta un máximo de 50 000) de la visualización en su dispositivo local. Un máximo de 50 000 elementos de dimensión para la dimensión seleccionada. |
| **[!UICONTROL Copiar visualización]** | Copia la visualización para que la pueda insertar en otro lugar del proyecto o en un proyecto completamente diferente. |
| **[!UICONTROL Descargar CSV de datos]** | Descarga inmediatamente los datos mostrados de la visualización en su dispositivo local. |
| **[!UICONTROL Exportar tabla completa…]** | Exporta la tabla completa a las ubicaciones en la nube designadas. Para obtener más información, consulte [Exporta informes de Customer Journey Analytics a la nube](../../export/export-cloud.md). |
| **[!UICONTROL Duplicar visualización]** | Crea un duplicado exacto de la visualización. |
| **[!UICONTROL Editar descripción]** | Añade (o edita) una descripción de texto para la visualización. Véase [Texto](../text.md). |
| **[!UICONTROL Obtener vínculo de visualización]** | Copia y comparte un vínculo directamente en la visualización. El cuadro de diálogo Compartir vínculo muestra el vínculo. Seleccione Copiar para copiar el vínculo en el portapapeles. |
| **[!UICONTROL Volver a empezar]** | Elimina la configuración de la visualización actual para que la pueda volver a configurar desde cero. |


>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Configuración de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Menú contextual de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
