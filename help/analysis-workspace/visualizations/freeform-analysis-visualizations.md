---
description: Obtenga información sobre las visualizaciones y los ajustes de visualización en Analysis Workspace.
keywords: Analysis Workspace
title: Resumen de las visualizaciones
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 97%

---


# Resumen de las visualizaciones

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Workspace oferta una serie de visualizaciones que le permiten generar representaciones visuales de sus datos, como gráficos de barras, gráficos circulares, histogramas, gráficos de líneas, mapas, gráficos de dispersión, etc. Cada visualización tiene su propia configuración que puede administrar. Haga clic en el nombre de la visualización para obtener información más detallada.

Vídeo de YouTube: [tipos de visualización en Analysis Workspace](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (2:57)

| Nombre de la visualización | Descripción |
|---|---|
| [Área](/help/analysis-workspace/visualizations/area.md) | es similar a un gráfico de líneas, pero incluye una zona coloreada bajo la línea. Utilice un gráfico de áreas cuando tenga varias métricas y desee visualizar el área a la que hace referencia la intersección de dos o más métricas. |
| [Barra](/help/analysis-workspace/visualizations/bar.md) | Muestra las barras verticales que representan los distintos valores de una o varias métricas. |
| [Gráfico de viñetas](/help/analysis-workspace/visualizations/bullet-graph.md) | Muestra cómo se compara un valor que le interese con otros rangos de rendimiento (objetivos). |
| [Tabla de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Una *`cohort`* es un grupo de personas que comparten características en común durante un periodo especificado. El análisis de cohorte es útil, por ejemplo, cuando desea saber cómo se involucra una cohorte con una marca. Puede identificar fácilmente los cambios en tendencias y responder en consecuencia. |
| [Anillo](/help/analysis-workspace/visualizations/donut.md) | Similar a un gráfico circular, esta visualización muestra los datos como partes o segmentos de un todo. |
| [Abandono](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | Los informes de visitas en el orden previsto muestran dónde abandonaron los visitantes y continuaron en una secuencia de páginas predefinidas. |
| [Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md) | Muestra las rutas del cliente en sus sitios web y aplicaciones. |
| [Tabla improvisada](/help/analysis-workspace/visualizations/freeform-table.md) | Una tabla improvisada no es solamente una tabla de datos, sino también una visualización interactiva. |
| [Histograma](/help/analysis-workspace/visualizations/histogram.md) | Un histograma es similar a un gráfico de barras, pero agrupa números en rangos (contenedores). |
| [Barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) | Muestra las barras horizontales que representan los distintos valores de una o varias métricas. |
| [Líneas](/help/analysis-workspace/visualizations/line.md) | Representa las métricas con una línea para mostrar cómo cambian los valores con el paso del tiempo. Un gráfico de líneas solo se puede usar cuando se utiliza el tiempo como dimensión. |
| [Diagrama de dispersión](/help/analysis-workspace/visualizations/scatterplot.md) | Muestra la relación entre los valores de dimensión y hasta tres métricas. |
| [Número de resumen](/help/analysis-workspace/visualizations/summary-number-change.md) | En función de la celda seleccionada, esta visualización muestra los totales y los resúmenes. |
| [Cambio de resumen](/help/analysis-workspace/visualizations/summary-number-change.md) | En función de las celdas seleccionadas, esta visualización compara las celdas entre sí. |
| [Texto](/help/analysis-workspace/visualizations/text.md) | Le permite agregar texto definido por el usuario al Workspace. |
| [Gráfico de rectángulos](/help/analysis-workspace/visualizations/treemap.md) | Muestra datos de forma jerárquica (con estructura de árbol) como un conjunto de rectángulos anidados. |
| [Venn](/help/analysis-workspace/visualizations/venn.md) | Le permite arrastrar hasta tres segmentos (de Componentes) y una métrica para generar un diagrama de Venn. |

## Panel de visualizaciones {#section_DC07F032FBEF4046A40F7B95C28DA018}

Para mostrar el Panel de visualizaciones, haga clic en **[!UICONTROL Visualizaciones]** en el panel lateral.

![Resultado ](assets/visualizations.png)

La mayoría de los tipos de visualización (como los gráficos de área, barras, sectores y líneas) le resultarán familiares si utiliza Adobe Analytics. Sin embargo, Analysis Workspace proporciona una configuración de visualización y múltiples tipos de visualización únicos o nuevos con funciones interactivas.

## Configuración de visualización {#section_D3BB5042A92245D8BF6BCF072C66624B}

Para acceder a la [!UICONTROL configuración de visualización], arrastre una visualización al [!UICONTROL panel improvisado] y haga clic en el icono de engranaje de [!UICONTROL Configuración de visualización].

>[!IMPORTANT]
>
>La visibilidad de los ajustes de visualización varía en función de la visualización. No todos los ajustes se aplican a todas las visualizaciones. Además, algunos ajustes avanzados aparecen **solo** para visualizaciones concretas, como [Ajustes de histograma](/help/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477).

![](assets/visualization_settings.png)

| Configuración | Descripción |
|--- |--- |
| Porcentajes | Muestra valores en porcentajes. |
| Apilada al 100 % | Esta configuración en las visualizaciones de áreas apiladas, barras apiladas o barras horizontales apiladas convierte el gráfico en una visualización apilada al 100 %. Ejemplo: ![](assets/stacked_100_percent.png) |
| Leyenda visible | Le permite ocultar el texto de detalles del filtro para la visualización de Número de resumen/Resumen del cambio. |
| Límite máximo de elementos | Le permite limitar el número de elementos que se muestran en una visualización. |
| Eje Y delimitador a cero | Si todos los valores marcados en el gráfico están considerablemente por encima de cero, el gráfico mostrará el valor base del eje Y distinto a cero. Si marca esta casilla, el eje Y se forzará a ser cero (y se redibujará el gráfico). |
| Normalización | Fuerza métricas para igualar proporciones. |
| Mostrar eje doble | Solo es aplicable si cuenta con dos métricas: puede tener un eje Y a la izquierda (para una métrica) y a la derecha (para otra métrica). |
| Mostrar anomalías | Mejora los gráficos de líneas y las tablas improvisadas para mostrar las anomalías de datos. |

## Icono Crear imagen {#section_9C11D9DEDC42413AA53E69A71A509DFC}

Si no está seguro de qué visualización escoger, haga clic en el icono **[!UICONTROL Crear visualización]** en cualquier fila de la tabla. Dicho icono aparecerá cuando se sitúe sobre la fila de la tabla. Si hace clic en él, Analysis Workspace le dirá qué visualización sería la más adecuada para sus datos. Por ejemplo, si tiene hasta tres segmentos seleccionados, se creará un diagrama de Venn. Para más de tres segmentos, se creará un gráfico de barras. Para otros tipos de datos, es posible que se cree un gráfico de líneas, etc.

![](assets/create-visual.png)

## Hacer clic con el botón derecho en el menú Visualización/Panel {#section_05B7914D4C9E443F97E2BFFDEC70240C}

Se puede acceder a la configuración contextual de un gráfico si hace clic con el botón derecho junto al encabezado de una visualización o un panel. Estarán disponibles todos o algunos de los siguientes ajustes:

![](assets/right-click_menu.png)

| Configuración | Descripción |
|--- |--- |
| Insertar visualización/panel copiado | Le permite pegar (“insertar”) el elemento copiado en otro lugar del proyecto o en otro proyecto diferente. |
| Copiar visualización/panel | Le permite hacer clic con el botón derecho y copiar una visualización o un panel. |
| Duplicar visualización/panel | Crea un duplicado exacto de la visualización actual, el cual puede modificar a continuación. |
| Contraer todos los paneles | Contrae todos los paneles del proyecto. |
| Contraer todas las visualizaciones del panel | Contrae todas las visualizaciones de este panel de proyecto. |
| Ampliar todos los paneles | Amplía todos los paneles del proyecto. |
| Ampliar todas las visualizaciones del panel | Amplía todas las visualizaciones de este panel de proyecto. |
| Editar descripción | Añade (o edita) una descripción de texto del panel/visualización. Esta descripción se muestra en Proyecto > Información y configuración del proyecto. |
| Obtener vínculo del panel | Le permite dirigir a los usuarios a un panel concreto de un proyecto. |
| Obtener vínculo de visualización | Le permite copiar y compartir este vínculo para enviar a otros usuarios directamente a esta visualización. Los usuarios deberán iniciar sesión. |
| Volver a empezar | (Funciona en Flujo, Venn, Histograma) Elimina la configuración de la visualización actual y abre un panel nuevo donde puede volver a configurarla. |

## Edición de las etiquetas de la leyenda {#section_94F1988CB4B9434BA1D9C6034062C3DE}

Le permite cambiar el nombre de las series en las leyendas de las visualizaciones (visitas en el orden previsto, área, área apilada, barras, barras apiladas, anillo, histograma, barras horizontales, barras horizontales apiladas, líneas, dispersión y Venn) para contribuir al uso de las imágenes.

La edición de leyendas **no** se aplica a: visualizaciones de rectángulos, viñetas, número o cambio de resumen, texto, improvisación, histograma, cohorte o flujo.

Para editar una etiqueta de leyenda en un gráfico de líneas, por ejemplo:

1. Haga clic con el botón derecho en una de las etiquetas de leyenda.
1. Haga clic en **[!UICONTROL Editar etiqueta]**.

   ![](assets/edit-label.png)

1. Introduzca el nuevo texto de etiqueta.
1. Pulse **[!UICONTROL Intro]** para guardar.

Aquí tiene un [vínculo que dirige a un vídeo](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) sobre este tema.
