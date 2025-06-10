---
description: Obtenga información sobre cómo añadir componentes a un proyecto en Analysis Workspace
title: Uso de componentes en Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 7%

---

# Uso de componentes en Analysis Workspace

Los componentes constituyen los datos reales de cualquier proyecto de Analysis Workspace. Los componentes están formados por dimensiones, métricas, segmentos e intervalos de fechas. Puede añadir componentes a un proyecto arrastrándolos a visualizaciones o paneles.

Consulte la [Descripción general de componentes](/help/components/overview.md) para obtener más información sobre los tipos de componentes que puede agregar.

>[!TIP]
>
>Para obtener información acerca de cada componente, use ![InfoOutline](/help/assets/icons/InfoOutline.svg). Consulte [Información de componente](#component-info) para obtener más información

## Añadir componentes a un proyecto

1. [Crear un proyecto en Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Agregue un panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel) o [agregue una visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) al proyecto en Analysis Workspace. Si agrega un componente a un proyecto en blanco, ya se ha creado una visualización de tabla de forma libre.

1. Seleccione ![Depurar](/help/assets/icons/Curate.svg) **[!UICONTROL Componentes]** del panel de botones. Verá todos los componentes disponibles en el panel izquierdo. Consulte [Interfaz](/help/analysis-workspace/home.md#interface) para obtener más detalles.

1. Desplácese hasta el componente que desee añadir o búsquelo y arrástrelo a un panel o a una visualización dentro del proyecto.

1. Si lo desea, puede arrastrar un componente a la zona de colocación de segmentos en el encabezado de un panel. Con este proceso de arrastrar y soltar, se define el componente como un segmento y se aplica el segmento a todo el contenido del panel.
Para obtener información sobre cómo usar la zona de colocación de segmentos en un panel para segmentar el panel, consulte [Zona de colocación](/help/analysis-workspace/c-panels/panels.md#drop-zone) en [Información general de paneles](/help/analysis-workspace/c-panels/panels.md).

1. Para obtener información más detallada, consulte las siguientes secciones:

   * [Adición de dimensiones a un proyecto](#add-dimensions-to-a-project)

   * [Agregar métricas a un proyecto](#add-metrics-to-a-project)

   * [Añadir segmentos a un proyecto](#add-segments-to-a-project)

   * [Adición de intervalos de fechas a un proyecto](#add-date-ranges-to-a-project)

### Adición de dimensiones a un proyecto

[Las dimensiones](/help/components/dimensions/overview.md) son variables en Customer Journey Analytics que generalmente contienen valores de cadena. Por el contrario, las [métricas](/help/components/calc-metrics/calc-metr-overview.md) contienen valores numéricos que se vinculan a una dimensión. Un informe básico muestra filas de valores de cadena (dimensión) frente a una columna de valores numéricos (métrica).

1. Comience a agregar una dimensión al proyecto en Analysis Workspace, tal como se describe en [Agregar componentes a un proyecto](#add-components-to-a-project).

1. Elija uno de los siguientes métodos para añadir dimensiones y determinar el tipo de datos que desea analizar:

   ![Agregar una dimensión](/help/components/assets/add-dimension.gif)

   * Arrastre una dimensión a una visualización (como una tabla de forma libre) en Analysis Workspace.

   * Arrastre una o más dimensiones del panel izquierdo a la zona de colocación de segmentos para crear un segmento rápido, tal como se describe en [Agregar segmentos a un proyecto](#add-filters-to-a-project).

1. Si lo desea, puede desglosar dimensiones y elementos de dimensión en Analysis Workspace con otros componentes. Para obtener más información, consulte [Desglosar dimensiones en Workspace](/help/components/dimensions/t-breakdown-fa.md).

Para obtener más información sobre cómo usar dimensiones en Analysis Workspace, consulte [Previsualizar dimensiones](/help/components/dimensions/view-dimensions.md), [Desglosar dimensiones](/help/components/dimensions/t-breakdown-fa.md) y [Dimensiones de partición de tiempo](/help/components/dimensions/time-parting-dimensions.md).

### Agregar métricas a un proyecto

Las métricas permiten cuantificar los puntos de datos en Analysis Workspace. Normalmente se utilizan como columnas en una visualización y están vinculadas a las dimensiones.

Para agregar una métrica a un proyecto en Analysis Workspace:

1. Empiece a agregar una métrica al proyecto en Analysis Workspace, como se describe en [Agregar componentes a un proyecto](#add-components-to-a-project).



1. Elija uno de los siguientes métodos para agregar una métrica en Analysis Workspace:

   ![Agregando una métrica](/help/components/assets/add-metric.gif)

   * Arrastre una métrica a la zona de colocación de métricas en una tabla de forma libre vacía para ver las tendencias de esa métrica durante el período de fecha del proyecto.

   * Arrastre una métrica cuando haya una dimensión para ver esa métrica para cada elemento de dimensión.

   * Arrastrar una métrica sobre un encabezado de métrica existente para reemplazarla.

   * Arrastre una métrica junto a la izquierda o la derecha del encabezado de una métrica existente para agregar la nueva métrica.

   * Arrastre una métrica por encima o por debajo del encabezado de una métrica existente para crear una superposición de métricas.


Para obtener más información sobre las métricas, consulte [Métricas](/help/components/apply-create-metrics.md).

### Añadir segmentos a un proyecto

Los [segmentos](/help/components/segments/seg-overview.md) le permiten identificar subconjuntos de personas, sesiones o eventos según sus características o interacciones específicas.

Puede utilizar segmentos en Analysis Workspace de cualquiera de las siguientes maneras:

* Adición de segmentos a un panel
Cuando agrega segmentos a un panel, los segmentos se aplican a todo el contenido del panel.
Para obtener información sobre cómo usar la zona de colocación de segmentos en un panel para segmentar el panel, consulte [Zona de colocación](/help/analysis-workspace/c-panels/panels.md#drop-zone) en [Información general de paneles](/help/analysis-workspace/c-panels/panels.md).

* Añadir segmentos a una visualización
Cuando se añaden segmentos a una columna de una tabla de forma libre, los segmentos se aplican a todo el contenido de la columna de la tabla. También puede agregar segmentos como parte de una visualización de visitas en el orden previsto.

* Uso de segmentos en componentes
Al definir componentes como [métricas calculadas](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [anotaciones](/help/components/annotations/create-annotations.md#annotation-builder) o incluso [segmentos](/help/components/segments/seg-builder.md), puede usar segmentos como parte de la definición.


### Adición de intervalos de fechas a un proyecto

[Los intervalos de fechas](/help/components/date-ranges/overview.md) determinan el lapso de tiempo de la creación de informes en Analysis Workspace y se pueden aplicar a uno o más paneles dentro de un proyecto, así como a algunas visualizaciones (como la tabla de forma libre).

Cada panel incluye un intervalo de fechas de forma predeterminada. Existen varias formas de actualizar un intervalo de fechas para un panel. Una forma de actualizar el intervalo de fechas de un panel en Analysis Workspace es arrastrar un componente de intervalo de fechas desde el panel izquierdo:

1. Opcionalmente, agregue un intervalo de fechas al proyecto en Analysis Workspace, tal como se describe en [Agregar componentes a un proyecto](#add-components-to-a-project).

1. Arrastre y suelte un intervalo de fechas desde el panel izquierdo a:

   * El intervalo de fechas actual para modificar el intervalo de fechas del panel.

     ![Colocar un intervalo de fecha](assets/add-date-range.gif)

   * Una métrica o dimensión en una visualización de tabla de forma libre. Consulte [Usar intervalos de fechas](/help/components/date-ranges/overview.md#use-date-ranges) para obtener más información.

Para obtener más información sobre cómo usar y administrar intervalos de fechas en Analysis Workspace, consulte [Información general sobre los intervalos de fechas](/help/components/date-ranges/overview.md).

## Información del componente

Puede pasar el ratón sobre cualquier componente para mostrar ![Más información](/help/assets/icons/InfoOutline.svg). Al seleccionarlo, se muestra una ventana emergente con información adicional sobre el componente.

![Información de componente](assets/component-info.png)

En función del control de acceso, puede:

* Obtenga acceso a la definición de ![Marcador](/help/assets/icons/Bookmark.svg) [!UICONTROL Diccionario de datos] para el componente.
* Acceda al generador de componentes ![Edit](/help/assets/icons/Edit.svg) o a la vista de datos donde se definió el componente.
