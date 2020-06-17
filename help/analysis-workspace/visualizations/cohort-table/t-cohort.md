---
description: Crear una cohorte y ejecutar un informe de análisis de cohorte en Analysis Workspace.
keywords: Analysis Workspace
title: Ejecutar un informe de análisis de cohorte
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 73%

---


# Configure a [!UICONTROL Cohort Analysis] report

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Create a cohort and run a [!UICONTROL Cohort Analysis] report in Analysis Workspace.

1. En Analysis Workspace, haga clic en el icono **[!UICONTROL Visualizaciones]** en el panel izquierdo y, a continuación, arrastre una **[!UICONTROL tabla asociada]** al lienzo.

   ![](assets/cohort-table.png)

1. Defina los **[!UICONTROL Criterios de inclusión]**, **[!UICONTROL Criterios de retorno]**, **[!UICONTROL Tipo de cohorte]** y la **[!UICONTROL Configuración]** tal y como se indica en la siguiente tabla.

| Elemento | Descripción |
|--- |--- |
| **[!UICONTROL Criterios de inclusión]** | Puede aplicar hasta 10 segmentos de inclusión y hasta 3 métricas de inclusión. La métrica indica qué factores colocan a un usuario en una cohorte determinada. Por ejemplo, si la métrica de inclusión es Órdenes, solo se incluirán en la cohorte inicial aquellos usuarios que hayan realizado una orden durante el intervalo de tiempo del análisis de cohorte.<br>El operador predeterminado entre métricas es Y, aunque se puede cambiar a O. Además, se puede añadir filtrado numérico a estas métricas. Por ejemplo: &quot;Visitas >= 1&quot;.</br> |
| **[!UICONTROL Criterios de regreso]** | Puede aplicar hasta 10 segmentos de regreso y hasta 3 métricas de regreso. La métrica indica si se ha retenido al usuario (retención) o no (pérdida). Por ejemplo, si la métrica de regreso es Vistas de vídeo, solo se representarán como retenidos aquellos usuarios que hayan visto vídeos durante periodos de tiempo siguientes (después del periodo en el que se agregaron a una cohorte). Otra métrica que cuantifica la retención es Visitas. |
| **[!UICONTROL Granularidad]** | La granularidad de tiempo de Día, Semana, Mes, Trimestre o Año. |
| **[!UICONTROL Tipo]** | **[!UICONTROL Retención]** (predeterminado): una cohorte de retención mide en qué medida las cohortes de visitantes regresan a su propiedad a lo largo del tiempo. Esta es la cohorte estándar que siempre hemos tenido y que indica un comportamiento de regreso y repetición por parte del usuario. A [!UICONTROL Retention] Cohort is indicated by the color green in the table.<br>**[!UICONTROL Pérdida ]**: una cohorte de pérdida (también conocida como “desgaste” o “abandono”) mide cómo las cohortes de visitantes se alejan de su propiedad a lo largo del tiempo. Pérdida = 1 - Retención.[!UICONTROL La pérdida es una buena medida de la permanencia y una oportunidad, ya que muestra con qué frecuencia no regresan los clientes.]Puede utilizar la pérdida para analizar e identificar áreas en las que centrarse: ¿qué segmentos de cohorte deben recibir más atención? A[!UICONTROL Churn]Cohort is indicated by the color red in the table (similar to fallout in our**[!UICONTROL  Flow ]**visualization).</br> |
| **[!UICONTROL Configuración]** | **[!UICONTROL Cálculo móvil]**: calcule la retención o la pérdida en función de la columna previa, no de la columna Incluido (valor predeterminado). [!UICONTROL Cálculo móvil cambia el método de cálculo para sus periodos de &quot;regreso&quot;. ] El cálculo normal encuentra de forma independiente usuarios que satisfacen los criterios de &quot;regreso&quot; y que fueron parte del periodo de inclusión, sin importar si estaban o no en la cohorte durante el periodo anterior. Instead, [!UICONTROL Rolling Calculation] finds users who meet &quot;return&quot; criteria and were part of the previous period. Therefore, [!UICONTROL Rolling Calculation] filters and funnels the users who continually meet the &quot;return&quot; criteria period over period. [!UICONTROL Los criterios de devolución se aplican a cada uno de los periodos previos al periodo seleccionado. ] </br><br>**[!UICONTROL Tabla ]**de latencia: Una tabla de[!UICONTROL latencia]mide el tiempo transcurrido antes y después de que se produjo el evento de inclusión.[!UICONTROL La latencia es muy útil para el análisis previo/posterior.]For example, if you have an upcoming product or campaign launch and you want to track behavior before as well as see how it performs after, the[!UICONTROL Latency]table will display the pre and post behavior side by side to see the direct impact. The pre-inclusion cells in the[!UICONTROL Latency]Table are calculated by users who meet the[!UICONTROL Inclusion]criteria on the inclusion period and then meet the[!UICONTROL Return]criteria in the periods before the inclusion period. Note that[!UICONTROL Latency]tables and[!UICONTROL Custom Dimension]Cohort cannot be used together.</br><br>**[!UICONTROL Cohorte de dimensión personalizada]**: cree cohortes basadas en la dimensión seleccionada, no en el tiempo (valor predeterminado). Muchos clientes desean analizar sus cohortes en función de un criterio distinto del tiempo. La nueva función de cohorte de dimensión personalizada ofrece la flexibilidad para generar cohortes basadas en dimensiones de su elección. Utilice dimensiones como canal de marketing, campaña, producto, página, región o cualquier otra dimensión de Adobe Analytics para mostrar cómo cambia la retención en función de los distintos valores que adoptan. The [!UICONTROL Custom Dimension] Cohort segment definition applies the dimension item only as part of the inclusion period, not as part of the return definition.</br><br>[!UICONTROL Después de elegir la opción Cohorte de dimensión personalizada, puede arrastrar y soltar cualquier dimensión que desee en la zona de colocación. ] De este modo puede comparar elementos de dimensión similares durante el mismo periodo de tiempo. Por ejemplo, puede comparar el rendimiento de ciudades, de productos, de campañas, etcétera. Devuelve sus 14 elementos de dimensión principales. Sin embargo, puede utilizar un filtro (al que se accede manteniendo el puntero a la derecha de la dimensión que ha arrastrado) para que solo se muestren los elementos de dimensión que desee. A [!UICONTROL Custom Dimension] Cohort cannot be used with the [!UICONTROL Latency] Table feature.</br> |

1. Para ajustar la configuración de la **[!UICONTROL tabla asociada]**, haga clic en el icono de engranaje.

| Configuración | Descripción |
| Solo mostrar porcentaje | Elimina el valor numérico y solo muestra el porcentaje. |
| Porcentaje de redondeo al total más cercano | Redondea el valor porcentual al total más cercano en lugar de mostrar el valor decimal. |
| Mostrar fila de porcentaje promedio | Inserta una nueva fila en la parte superior de la tabla y, a continuación, agrega el promedio de los valores dentro de cada columna. |

## Build the [!UICONTROL Cohort Analysis] report

1. Haga clic en **[!UICONTROL Generar]**.

   ![Resultado](assets/cohort-report.png)

   El informe muestra los visitantes que realizaron un pedido (columna *`Included`*) y que regresaron al sitio en visitas posteriores. La reducción en visitas durante el tiempo le permite identificar problemas y tomar medidas.
1. (Opcional) Cree un segmento a partir de una selección.

   Seleccione celdas (contiguas o no) y haga clic con el botón secundario en > **[!UICONTROL Crear segmento a partir de la selección]**.

1. In the [Filter Builder](https://docs.adobe.com/content/help/es-ES/analytics/components/segmentation/segmentation-workflow/seg-build.html), further edit the segment, then click **[!UICONTROL Save]**.

   El segmento guardado está disponible para usar en el panel [!UICONTROL Segmento][!UICONTROL  en Analysis Workspace].
1. Especifique un nombre y guarde su proyecto de cohorte.
1. (Opcional) [Depure y comparta](/help/analysis-workspace/curate-share/curate.md) los componentes del proyecto.

   >[!NOTE]
   >
   >Debe guardar el proyecto antes de que la depuración esté disponible.

