---
title: Configuración de una visualización de matriz en Analysis Workspace
description: Obtenga información sobre cómo configurar la visualización de matrices en Customer Journey Analytics Analysis Workspace, incluidos sus componentes, opciones de visualización y configuración.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 4%
---

# Configuración de una visualización de matriz

La visualización Matriz es una cuadrícula de valores que muestra cómo los elementos de dimensión de dos dimensiones se superponen o se correlacionan entre sí. Cada celda muestra la intersección del elemento de dimensión de la fila con la del elemento de dimensión de la columna.

![Visualización de matriz](assets/matrix-overview.png)

## Información general de matriz

Consulte [Información general de matriz](/help/analysis-workspace/visualizations/matrix/matrix.md) para obtener más información acerca de la visualización de matriz, lo que incluye:

* Funciones principales

* Información potencial

* Diferencias entre las visualizaciones de matriz, tabla de forma libre, Venn y Dispersión

## Creación de una visualización de matriz

1. Agregue un panel en blanco al proyecto, seleccione el icono [!UICONTROL **Visualizaciones**] en el carril izquierdo y, a continuación, arrastre la visualización [!UICONTROL **Matriz**] al panel. <!-- FOLLOW-UP: add the Matrix icon before the name when it's available in help/assets/icons. -->

   O bien

   Agregue una visualización de matriz de cualquiera de las formas descritas en la sección [Agregar visualizaciones a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) de [Información general sobre visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   <!-- add screenshot of the Matrix configuration fields -->

1. Especifique la siguiente información para configurar la visualización de la matriz:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Dimensión de fila**] | Dimensión cuyos elementos aparecen como filas en la matriz. |
   | [!UICONTROL **Dimensión de columna**] | Dimensión cuyos elementos aparecen como columnas en la matriz. <p>Si selecciona la misma dimensión tanto para la dimensión de fila como para la de columna, la visualización de matriz compara los elementos de dimensión entre sí. Por ejemplo, si ambas dimensiones son _Tipo de dispositivo_, cada celda muestra la superposición o correlación entre dos tipos de dispositivos, como _Teléfono móvil_ y _Tablet_. Los valores por encima y por debajo de la diagonal se reflejan entre sí.</p> |
   | [!UICONTROL **Métrica**] | La métrica que muestra cada celda para la combinación de su elemento de dimensión de fila y su elemento de dimensión de columna. |
   | [!UICONTROL **Contenedor**] | El contenedor que determina el ámbito de la superposición entre los elementos de dimensión de fila y los elementos de dimensión de columna. (Si los nombres de contenedor difieren de los nombres predeterminados que se muestran a continuación, se personalizaron en la vista de datos).<ul><li>**Persona:** (predeterminado) Un elemento de dimensión de fila y un elemento de dimensión de columna se superponen cuando se producen para la misma persona, en cualquier número de sesiones.</li><li>**Sesión:** Un elemento de dimensión de fila y un elemento de dimensión de columna se superponen cuando se producen en la misma sesión.</li><li>**Evento:** Un elemento de dimensión de fila y un elemento de dimensión de columna se superponen cuando se producen en el mismo evento.</li></ul><!-- SME CHECK: confirm how each container defines overlap. --> |

1. (Opcional) Cambie cualquiera de las siguientes opciones de configuración:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Límite de fila**] | Número máximo de filas que muestra la visualización de la matriz. El valor predeterminado es 10. <!-- SME CHECK: Which items are shown (top items by the metric?)? Does the limit also apply to columns? What's the maximum? --> |
   | [!UICONTROL **Paleta de superposición**] | Escala de color de las celdas cuando la matriz muestra [recuentos de superposición](#view-overlap-count-or-correlation-strength). |
   | [!UICONTROL **Paleta de correlación**] | Escala de color de las celdas cuando la matriz muestra [intensidad de correlación](#view-overlap-count-or-correlation-strength). Las correlaciones negativas y positivas utilizan colores diferentes. |
   | [!UICONTROL **Granularidad de correlación**] | La granularidad de tiempo usada para calcular la [intensidad de la correlación](#view-overlap-count-or-correlation-strength), como **[!UICONTROL Día]**. Este valor se establece automáticamente en función del intervalo de fechas del panel. No lo puedes cambiar. <p>Se eligen las siguientes granularidades, según el intervalo de fechas del panel:</p><ul><li>[!UICONTROL **Hora**]: Elegida para intervalos de fechas de 7 días o menos</li><li>[!UICONTROL **Día**]: se eligió para intervalos de fechas de más de 7 días y hasta 3 meses</li><li>[!UICONTROL **Semana**]: se ha elegido para intervalos de fechas de más de tres meses y hasta un año</li><li>[!UICONTROL **Mes**]: se eligió para intervalos de fechas de más de 1 año</li></ul><!-- SME CHECK: The granularities and date range thresholds in this list are a best guess. Confirm which granularities are used for which date ranges. --> |
   | [!UICONTROL **Valores diagonales de celda**] | Cómo la visualización Matriz muestra las celdas donde se encuentra un elemento de dimensión. Esta configuración solo está disponible cuando la dimensión de fila y la dimensión de columna son la misma.<ul><li>**[!UICONTROL Mostrar]:** Muestra el valor.</li><li>**[!UICONTROL Guión]:** Muestra un guión en lugar del valor.</li><li>**[!UICONTROL En blanco]:** Deja vacía la celda.</li></ul> |

1. Seleccione [!UICONTROL **Generar**].

   <!-- add screenshot -->

1. Continúe con la siguiente sección [Ver recuento de superposición o intensidad de correlación](#view-overlap-count-or-correlation-strength).

## Ver recuento de superposición o intensidad de correlación

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_matrix_overlap_correlation"
>title="Recuento de superposiciones frente a intensidad de la correlación"
>abstract="<p>**Recuento de superposiciones** es el valor de la métrica seleccionada en la que se superponen un elemento de dimensión de fila y un elemento de dimensión de columna.</p><p>**Intensidad de correlación** es una correlación lineal, de -1 a +1, de cómo se mueve la métrica de los dos elementos de dimensión juntos a lo largo del tiempo. Un valor de +1 significa que suben y bajan juntos, 0 significa que no hay relación y -1 significa que se mueven en direcciones opuestas. La intensidad de la correlación se calcula separadamente de la superposición, por lo que los elementos de dimensión con poca superposición pueden seguir teniendo una correlación sólida.</p>"

<!-- markdownlint-enable MD034 -->

Puede alternar la visualización de la matriz para mostrar el recuento de superposición o la intensidad de la correlación. El recuento de superposición se muestra de forma predeterminada.

1. En Analysis Workspace, abra una visualización de matriz o [cree una nueva](#build-a-matrix-visualization).

1. En la esquina superior izquierda de la visualización de la matriz, seleccione una de las siguientes opciones:

   * [!UICONTROL **Recuento de superposición**]: muestra cuánta superposición existe para cada elemento de dimensión de fila con cada elemento de dimensión de columna. Cada celda muestra el valor de la métrica seleccionada para las personas, sesiones o eventos (según el contenedor) en los que se producen ambos elementos de dimensión.

   * [!UICONTROL **Intensidad de correlación**]: muestra la proximidad entre la métrica seleccionada para cada elemento de dimensión de fila y cada elemento de dimensión de columna en el intervalo de fechas del panel, como una correlación lineal entre -1 y +1. Un valor de +1 significa que los dos elementos de dimensión siempre suben y bajan juntos, 0 significa que no hay relación y -1 significa que siempre se mueven en direcciones opuestas. La intensidad de la correlación se calcula separadamente de la superposición, por lo que los elementos de dimensión con poca superposición pueden seguir teniendo una correlación sólida. La correlación se calcula con la granularidad de tiempo que se muestra en la configuración [!UICONTROL **Granularidad de correlación**]. <!-- SME CHECK: Confirm that the linear correlation is Pearson. -->

   Una leyenda en la esquina superior derecha de la visualización Matriz muestra la escala de colores de la vista actual: de menor a mayor para el recuento de superposición o de negativo (-1) a positivo (+1) para la intensidad de la correlación.

## Ver perspectivas

<!-- FOLLOW-UP: Draft based on a prototype screenshot. Add a screenshot of the insight card. -->

Una tarjeta de insight en la parte inferior de la visualización de la matriz describe patrones notables en los datos de la matriz.

<!-- SME CHECK: How are insights generated (AI)? What does the label on the card (such as ABSOLUTE) mean, and what other labels are there? Do the insights differ between the Overlap count and Correlation strength views? Are they updated when you change the settings or the panel date range? Can you hide the card? Are any permissions, entitlements, or AI settings required? -->

Para ver información:

1. En una visualización de matriz, vea la tarjeta de insight en la parte inferior de la visualización.

1. Utilice las flechas de la tarjeta de insight para desplazarse por las páginas de información disponible.

## Editar la configuración de la matriz

Después de crear una visualización de matriz, puede cambiar su configuración, como las dimensiones, la métrica o el contenedor.

Para editar la configuración de la matriz:

1. En una visualización de matriz, seleccione ![Editar](/help/assets/icons/Edit.svg) junto al subtítulo en la parte superior de la visualización. El subtítulo resume la configuración actual, como la métrica y las dimensiones.

1. Cambie cualquiera de las opciones de configuración descritas en [Generar una visualización de matriz](#build-a-matrix-visualization).

1. Seleccione [!UICONTROL **Generar**].

<!-- SME CHECK: Confirm that the Edit icon reopens the build settings. Does the Matrix keep the Overlap count or Correlation strength view after you rebuild it? -->

## Visualización de datos de tendencias

Puede ver los datos de tendencia de una celda en una [visualización de línea](/help/analysis-workspace/visualizations/line.md). La visualización de líneas muestra cómo cambia la métrica seleccionada en el intervalo de fechas del panel. Las líneas que se muestran dependen de si la matriz muestra [recuento de superposición o intensidad de correlación](#view-overlap-count-or-correlation-strength).

Para ver los datos de tendencias:

1. En una visualización de matriz, haga clic con el botón derecho en la celda cuyos datos de tendencia desee ver.

1. Seleccione [!UICONTROL **Tendencia**].

   Se agrega una visualización de línea al panel, encima de la visualización de matriz:

   * [!UICONTROL **Recuento de superposiciones**]: una sola línea muestra la métrica seleccionada, filtrada por el elemento de dimensión de fila y el elemento de dimensión de columna.

   * [!UICONTROL **Intensidad de correlación**]: dos líneas muestran la métrica seleccionada, una para el elemento de dimensión de fila y otra para el elemento de dimensión de columna. Compare las líneas para ver la tendencia conjunta de los dos elementos de dimensión.

   <!-- SME CHECK: Does the overlap count filter use the Matrix container? Is the time granularity the panel default or the Correlation granularity? Can you select multiple cells? Is the option available for diagonal cells? -->

## Ver la superposición en una visualización Venn

Puede ver la superposición entre el elemento de dimensión de fila y el elemento de dimensión de columna de una celda en una [visualización Venn](/help/analysis-workspace/visualizations/venn.md).

Para obtener más información sobre cuándo usar una visualización de matriz o una visualización Venn, consulte [Elegir entre visualizaciones de matriz, tabla de forma libre, Venn o de dispersión](/help/analysis-workspace/visualizations/matrix/matrix.md#choose-between-matrix-freeform-table-venn-or-scatter-visualizations) en [Información general de matriz](/help/analysis-workspace/visualizations/matrix/matrix.md).

Para ver la superposición en una visualización Venn:

1. En una visualización de matriz, haga clic con el botón derecho en la celda cuya superposición desee ver.

1. Seleccione [!UICONTROL **Mostrar en Venn**].

   Se agrega una visualización Venn al panel. Un círculo representa el elemento de dimensión de fila y el otro círculo representa el elemento de dimensión de columna. La visualización Venn utiliza la misma métrica que la visualización Matriz. <!-- SME CHECK: Where is the Venn visualization added? Are segments created for each dimension item, and do they use the Matrix container? Is the option available for diagonal cells and in the Correlation strength view? -->

## Aplicación de un desglose

Puede desglosar los datos de una celda en otra dimensión para ver qué elementos de dimensión contribuyen al valor de la celda.

Para aplicar un desglose:

1. En una visualización de matriz, haga clic con el botón derecho en la celda a la que desee aplicar un desglose.

1. Seleccione [!UICONTROL **Desglose**].

1. Seleccione la dimensión que desee utilizar para el desglose.

   Los elementos de dimensión principales para la dimensión de desglose se muestran en una nueva tabla de forma libre. <!-- SME CHECK: Where is the table added? Does the breakdown use the Matrix metric and container? Can you select multiple cells? Is the option available for diagonal cells and in the Correlation strength view? -->


