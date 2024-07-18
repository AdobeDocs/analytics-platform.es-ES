---
description: Obtenga información sobre cómo añadir componentes a un proyecto en Analysis Workspace
title: Uso de componentes en Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 16%

---

# Uso de componentes en Analysis Workspace

Los componentes constituyen los datos reales de cualquier proyecto de Analysis Workspace. Los componentes están formados por dimensiones, métricas, filtros e intervalos de fechas. Puede añadir componentes a un proyecto arrastrándolos a visualizaciones o paneles.

Para obtener información general sobre los tipos de componentes que puede agregar, vea [Información general sobre componentes](/help/components/overview.md).

>[!TIP]
>
>Para obtener información sobre cada componente, seleccione el icono de información junto al nombre de un componente en el carril izquierdo de Analysis Workspace.

## Empezar a añadir componentes a un proyecto

1. [Cree un proyecto en Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) si aún no lo ha hecho.

1. [Agregue un panel](/help/analysis-workspace/c-panels/panels.md) o [agregue una visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) al proyecto en Analysis Workspace.

   Si agrega un componente a un proyecto en blanco, se crea automáticamente una visualización de tabla de forma libre.

1. Seleccione el icono **[!UICONTROL Componentes]** en el carril izquierdo.

   ![](assets/build-components.png)

1. Desplácese hasta el componente que desee añadir o búsquelo y, a continuación, arrástrelo hasta un panel o visualización del proyecto.

1. (Opcional) Arrastre un componente a la zona de colocación de filtros en el encabezado de un panel.

   Los filtros se aplican a todo el contenido del panel.

   Para obtener información sobre cómo usar la zona de colocación de filtros en un panel para filtrar el panel, consulte [Zona de colocación](/help/analysis-workspace/c-panels/panels.md#drop-zone) en [Información general de paneles](/help/analysis-workspace/c-panels/panels.md).

   ![soltar un filtro en la zona de colocación](assets/filter-dropzone.png)

1. Para obtener información más detallada, continúe con una de las siguientes secciones, según el tipo de componente que esté agregando:

   * [Adición de dimensiones a un proyecto](#add-dimensions-to-a-project)

   * [Agregar métricas a un proyecto](#add-metrics-to-a-project)

   * [Añadir filtros a un proyecto](#add-filters-to-a-project)

   * [Adición de intervalos de fechas a un proyecto](#add-date-ranges-to-a-project)

## Adición de dimensiones a un proyecto

[Dimension](/help/components/dimensions/overview.md) son variables en Adobe Analytics que generalmente contienen valores de cadena. Por el contrario, las [métricas](/help/components/calc-metrics/calc-metr-overview.md) contienen valores numéricos que se vinculan a una dimensión. Un informe básico muestra filas de valores de cadena (dimensión) frente a una columna de valores numéricos (métrica).

1. Empiece a agregar una dimensión al proyecto en Analysis Workspace, como se describe en [Empiece a agregar componentes a un proyecto](#begin-adding-components-to-a-project).

1. Elija uno de los siguientes métodos para añadir dimensiones y determinar el tipo de datos que desea analizar:

   * Arrastre una dimensión a una visualización (como una tabla de forma libre) en Analysis Workspace.

     ![Agregar dimensiones a un proyecto](assets/add-dimensions.png)

   * Arrastre una o más dimensiones del carril izquierdo a la zona de colocación de filtros para crear un filtro ad hoc, tal como se describe en [Agregar filtros a un proyecto](#add-filters-to-a-project).

1. (Opcional) Puede desglosar dimensiones y elementos de dimensión en Analysis Workspace con otros componentes.

   Para obtener más información, consulte [Desglosar dimensiones en Workspace](/help/components/dimensions/t-breakdown-fa.md).

Para obtener más información sobre cómo usar dimensiones en Analysis Workspace, consulte [Previsualizar dimensiones](/help/components/dimensions/view-dimensions.md), [Desglosar dimensiones](/help/components/dimensions/t-breakdown-fa.md) y [Dimensiones de partición de tiempo](/help/components/dimensions/time-parting-dimensions.md).

## Agregar métricas a un proyecto

Las métricas permiten cuantificar los puntos de datos en Analysis Workspace. Normalmente se utilizan como columnas en una visualización y están vinculadas a las dimensiones.

Para agregar una métrica a un proyecto en Analysis Workspace:

1. Empiece a agregar una métrica al proyecto en Analysis Workspace, como se describe en [Empiece a agregar componentes a un proyecto](#begin-adding-components-to-a-project).

1. Elija uno de los siguientes métodos para agregar una métrica en Analysis Workspace:

   * Arrastre una métrica a la zona de colocación de métricas en una tabla de forma libre vacía para ver las tendencias de esa métrica durante el período de fecha del proyecto.

     ![Agregar una métrica a un proyecto](assets/add-metrics.png)

   * Arrastrar una métrica cuando haya una dimensión presente para verla en comparación con cada elemento de dimensión.

   * Arrastrar una métrica sobre un encabezado de métrica existente para reemplazarla.

   * Arrastrar una métrica junto a un encabezado para ver ambas métricas en paralelo.

Para obtener más información acerca de las métricas, vea [Resumen de las métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md).

## Añadir filtros a un proyecto

Los [filtros](/help/components/filters/filters-overview.md) le permiten identificar subconjuntos de visitantes basándose en sus características o en interacciones específicas.

Puede utilizar filtros en Analysis Workspace de cualquiera de las siguientes maneras:

### Adición de filtros a un panel

Cuando se añaden filtros a un panel, los filtros se aplican a todo el contenido del panel.

Para obtener información sobre cómo usar la zona de colocación de filtros en un panel para filtrar el panel, consulte [Zona de colocación](/help/analysis-workspace/c-panels/panels.md#drop-zone) en [Información general de paneles](/help/analysis-workspace/c-panels/panels.md).

### Añadir filtros a una columna en una tabla de forma libre

Cuando se añaden filtros a una columna de una tabla de forma libre, los filtros se aplican a todo el contenido de la columna de la tabla.

### Uso de filtros al crear métricas calculadas

En el Creador de métricas calculadas, puede aplicar filtros dentro de su definición de métrica.

Para obtener más información, consulte [Métricas filtradas](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md).

## Adición de intervalos de fechas a un proyecto

[Los intervalos de fechas](/help/components/date-ranges/custom-date-ranges.md) determinan el lapso de tiempo de la creación de informes en Analysis Workspace y se pueden aplicar a uno o más paneles dentro de un proyecto.

Cada panel incluye un intervalo de fechas de forma predeterminada. Existen varias formas de actualizar un intervalo de fechas para un panel. Una forma de actualizar el intervalo de fechas de un panel en Analysis Workspace es arrastrar un componente de intervalo de fechas desde el carril izquierdo:

1. Empiece a agregar un intervalo de fechas al proyecto en Analysis Workspace, tal como se describe en [Empiece a agregar componentes a un proyecto](#begin-adding-components-to-a-project).

1. Arrastre un intervalo de fechas desde el carril izquierdo al intervalo de fechas actual en la parte superior derecha del panel.

   ![soltar un intervalo de fecha](assets/daterange-drop.png)

Para obtener más información sobre cómo usar calendarios e intervalos de fechas en Analysis Workspace, consulte [Resumen de calendario e intervalos de fechas](/help/components/date-ranges/custom-date-ranges.md).
