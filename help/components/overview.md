---
title: Resumen de componentes
description: Aprenda qué componentes son las ofertas de CJA y cómo puede utilizarlas en el sistema de informes.
translation-type: tm+mt
source-git-commit: c1699c4319b3b840d8420f3ffa1a4bd1c1d9a4d4
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 57%

---


# Resumen de componentes

Los componentes son funciones de Customer Journey Analytics que se pueden utilizar en los informes o pueden complementar las funciones del sistema de informes. Puede administrar estos componentes siguiendo estos pasos:

1. Inicie sesión en [analytics.adobe.com](https://analytics.adobe.com) con sus credenciales de Adobe ID.
2. Vaya a [!UICONTROL Componentes] > [!UICONTROL Componentes] en el menú del encabezado.

Puede administrar los siguientes componentes:

* [**Filtros:**](filters/filters-overview.md) excluir partes de los datos para centrarse en elementos de dimensión comunes
* [**Métricas calculadas:**](calc-metrics/calc-metr-overview.md) usar las métricas y fórmulas como componentes nuevos para utilizarlas en sistemas de informes
* [**Intervalos de fechas:**](date-ranges/overview.md) personalizar y especificar las ofertas de Analysis Workspace en los intervalos de fechas
* [**Proyectos:**](/help/analysis-workspace/home.md) organizar y mantener sus proyectos en Analysis Workspace

## Componentes de Analysis Workspace

Los componentes de Analysis Workspace están formados por métricas, dimensiones, segmentos y granularidades de tiempo que puede arrastrar y soltar en un proyecto. Los componentes personalizados que crea se añaden a estos paneles como, por ejemplo, los intervalos de fecha personalizados.

Para acceder al panel Componentes, haga clic en el icono **[!UICONTROL Componentes]** del carril izquierdo. Puede alternar entre paneles (Panel en blanco, [Panel de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Información rápida](/help/analysis-workspace/c-panels/quickinsight.md), o [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) panel), [Visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), y Componentes con los iconos del carril izquierdo o con [métodos abreviados de teclado](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

Consulte [Crear un proyecto](/help/analysis-workspace/home.md) para obtener información sobre el uso de Componentes en un proyecto.

## Acciones de componente

Puede administrar componentes (de uno en uno o seleccionando más de uno) de diferentes formas. Haga clic con el botón secundario en un componente o haga clic en **[!UICONTROL Acciones]** en la parte superior de la lista de componentes.

>[!NOTE]
>
>Estas acciones no se aplican a los componentes de tiempo.

| Acción de componente | Descripción |
|--- |--- |
| Etiqueta | Organizar o administrar componentes aplicándoles etiquetas. A continuación, el componente se muestra en el administrador de componentes pertinente, como Analytics > Componentes > Segmentos o Analytics > Componentes > Proyectos. |
| Favorito | Añadir el componente a la lista de favoritos. A continuación, se muestra en el administrador de componentes pertinente, como Analytics > Componentes > Segmentos o Analytics > Componentes > Proyectos. |
| Aprobar | Aprobar el componente para hacerlo canónico. A continuación, el componente se muestra en el administrador de componentes pertinente, como Analytics > Componentes > Segmentos o Analytics > Componentes > Proyectos. |
| Compartir | Solo se aplica a los segmentos. |
| Eliminar | Solo se aplica a los segmentos. |

Vea el vídeo sobre la creación de métricas, segmentos y fechas:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Permisos de acceso a los componentes

Los administradores pueden depurar (a través del [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products)) qué componentes están expuestos a los usuarios en los informes. La tabla siguiente muestra cómo se comportan estos permisos de acceso a componentes:

| Tipo de depuración | El administrador puede ver | El propietario del proyecto que no es administrador (o la función de edición) puede ver | Función duplicada no de administrador |
| --- | --- | --- | --- |
| **Componentes &quot;ocultos&quot; de una vista de datos** | Todos los componentes de vista de datos disponibles para la creación de informes (los componentes ocultos requieren hacer clic en &quot;Mostrar todo&quot;) | No disponible para informes | No disponible para informes |
| **Componentes agregados o eliminados de una vista de datos** | Solo los componentes agregados a la vista de datos (ocultos o no ocultos). Los administradores no pueden informar sobre campos o componentes que no estén definidos por la vista de datos. | Solo los componentes agregados a la vista de datos o los componentes propiedad del usuario o compartidos con él. Los componentes ocultos no están disponibles (como la depuración de VRS). | Solo los componentes añadidos al DV no se ocultan y se incluyen en la depuración del proyecto. |
| **Componentes depurados en un proyecto** | Todos los componentes de vista de datos disponibles para la creación de informes (los componentes ocultos requieren hacer clic en &quot;Mostrar todo&quot;) | Todos los componentes de vista de datos no ocultos (requiere hacer clic en &quot;mostrar todo&quot;) | Solo los componentes depurados, además de los componentes que sean propiedad del usuario o que se compartan con él |
| **Proyecto depurado mediante una vista de datos con componentes ocultos** | Todos los componentes de datos disponibles para la creación de informes (los componentes ocultos y no depurados requieren hacer clic en &quot;Mostrar todo&quot;) | Todos los componentes de proyecto no depurados, todos los componentes de vista de datos no ocultos y cualquier componente propiedad del usuario o compartido con él | Solo los componentes depurados, además de los componentes que sean propiedad del usuario o que se compartan con él |

