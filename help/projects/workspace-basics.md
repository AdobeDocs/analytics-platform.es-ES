---
title: Conceptos básicos del espacio de trabajo
description: Describe cómo extraer informes básicos en Workspace
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# Conceptos básicos del espacio de trabajo

Si todavía no está familiarizado con la herramienta Espacio de trabajo, aquí tiene algunas sugerencias para empezar.

Workspace es la principal herramienta de Adobe para tomar decisiones procesables basadas en datos para su organización. La visualización más común, la tabla de forma libre, permite crear fácilmente informes personalizados con dimensiones, métricas, segmentos e intervalos de fechas.

## Extraer un informe de clasificación básico en Workspace

Un informe de clasificación muestra una vista total agregada de cada valor de dimensión, empezando por los valores más altos. Estos tipos de informes son útiles para ver qué componentes del sitio son los más efectivos, como por ejemplo qué páginas obtienen la mayor cantidad de tráfico o qué productos se venden más.

1. Asegúrese de haber iniciado sesión en [analytics.adobe.com](https://analytics.adobe.com).
1. En la barra de navegación superior, haga clic en **[!UICONTROL Workspace]**.
1. Haga clic en **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. A la izquierda, debería ver una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Páginas (de color naranja) y arrástrela al lienzo hasta la zona con el texto “Coloque una dimensión aquí”.
1. Se puede ver un informe que muestra las páginas más visitadas del mes actual. Analysis Workspace llenó automáticamente el informe con la métrica [Ocurrencias](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html).
1. Busque la métrica Visitas (de color verde) y arrástrela **sobre** o **junto** al encabezado de la métrica Ocurrencias (evite colocarla encima de la métrica). Si arrastra la métrica Visitas sobre Ocurrencias, la métrica se reemplaza en los informes. Si arrastra la métrica Visitas junto a Ocurrencias, ambas métricas se mostrarán una al lado de la otra.
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Extraer un informe de tendencias básico en Workspace

Un informe de tendencias muestra una vista de horas extras de las métricas que utilizan el intervalo de fechas seleccionado. Estos tipos de informes son útiles para identificar las tendencias a lo largo del tiempo y pueden utilizarse para medir el éxito o el fracaso de las decisiones comerciales tomadas. Por ejemplo: puede consultar un informe de vistas de páginas con tendencias a lo largo del tiempo para ver si el rediseño del sitio ayudó a aumentar o disminuir el tráfico.

1. Asegúrese de haber iniciado sesión en [analytics.adobe.com](https://analytics.adobe.com).
1. En la barra de navegación superior, haga clic en **[!UICONTROL Workspace]**.
1. Haga clic en **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. A la izquierda, debería ver una lista de dimensiones, métricas, segmentos e intervalos de fechas. Locate the Page Views dimension, and drag it to the small space on the canvas labeled **[!UICONTROL Drop a Metric Here]**. Evite soltarlo en el espacio reservado para dimensiones (al menos para este ejercicio).
1. Tenga en cuenta que si el grupo de informes tiene datos, debería ver un informe de vistas de página básico con tendencias del mes actual. Analysis Workspace introdujo automáticamente el intervalo de fechas “Día” para que pueda ver la tendencia de las vistas de página del mes actual.
1. Busque el intervalo de fechas de la semana (de color púrpura) en la lista de componentes de intervalo de fechas de la izquierda. Haga clic en el título del intervalo de fechas para expandir y ver todos los componentes del intervalo de fechas o utilice la barra de búsqueda.
1. Arrastre el intervalo de fechas de la semana sobre el encabezado del intervalo de fechas del día en el lienzo para reemplazarlo.
1. Tenga en cuenta que el informe de tendencias ahora se agrega por semana en lugar de por día.
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Experimente con la herramienta

Como Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto del espacio de trabajo para ver qué hay disponible.

Si arrastra accidentalmente un componente no válido al proyecto del espacio de trabajo o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. You can also start with a clean slate by clicking **[!UICONTROL Project]>[!UICONTROL New]**in the upper left menu.

## Resolución de problemas

### Cuando arrastro una métrica, significa “Datos no válidos”.

Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas en paralelo.

### Cuando arrastro una métrica, no veo ningún dato real, solo ceros.

Si crea correctamente un informe de espacio de trabajo pero no hay datos, puede comprobar algunas cosas:

* Compruebe el grupo de informes y asegúrese de que se rellena con datos.
* Si utiliza un segmento en el informe, es posible que los criterios del segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del mismo.
* Compruebe el intervalo de fechas en la esquina superior derecha y compruebe que está establecido en un valor que esperaba.
* Vaya al sitio web y utilice Debugger para validar que se están recopilando datos.

## Recursos adicionales

Tenga en cuenta que los siguientes recursos pueden hacer referencia al uso de Workspace en el producto tradicional de Adobe Analytics, no en el análisis de viajes del cliente.

* Publicaciones del blog:
   * [Fortalecer las empresas con un análisis más inteligente](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Espacio de trabajo de Análisis: La salsa secreta se está volviendo más desagradable](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [Por qué debería utilizar Analysis Workspace](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)
   * [5 consejos para optimizar su productividad con Analysis Workspace](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/)

## Pasos siguientes

Hay muchas formas diferentes de comprender mejor Workspace. A continuación se indican algunos aspectos básicos que Adobe recomienda:

### Para usuarios finales que buscan ampliar sus conocimientos sobre cómo utilizar Workspace

* [Detalles de la IU de Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html): Ahora que ha creado un informe básico, familiarícese con el resto de la interfaz.
* [Visualizaciones en Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html): Las tablas de forma libre son simplemente un tipo de visualización en Analysis Workspace. Aprenda a utilizar otras visualizaciones, como gráficos de líneas, gráficos de barras y mapas geográficos.
* [Dimensiones en Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html): Obtenga más información sobre las dimensiones y cómo utilizarlas en algo más que en los informes de clasificación.
* [Métricas en Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html): Obtenga más información sobre las métricas y cómo utilizarlas en otras partes de tablas de forma libre.
* [Introducción a la segmentación](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html): Obtenga información sobre los segmentos y extraiga un informe básico con un segmento.
* [Intervalos de fechas en Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html): Obtenga información sobre las fechas relativas y móviles y utilícelas en proyectos de Workspace.
* [Uso compartido de proyectos en Workspace: Muestre a sus compañeros el impresionante proyecto de Workspace que ha creado.](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)

### Para analistas y administradores que buscan mejorar la calidad del espacio de trabajo en su organización

* [Permisos de Analysis Workspace](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html): Asigne permisos de usuario a Workspace mediante Adobe Admin Console.
* [Plantillas en Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html): Cree plantillas para que sus compañeros puedan empezar con un espacio de proyecto adaptado a sus necesidades.
* [Preparación personalizada de Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html): Cree un proyecto que limite los componentes disponibles para que el Workspace sea más fácil de usar para los menos familiarizados con la herramienta
