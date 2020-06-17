---
title: Panel de Attribution
description: Cómo utilizar e interpretar el panel de atribución en Analysis Workspace.
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 14%

---


# Panel de Attribution

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

El panel Atribución es una forma sencilla de generar un análisis comparando varios modelos de atribución. Es una característica de IQ [de](../attribution/overview.md) atribución que le proporciona un espacio de trabajo dedicado para usar y comparar modelos de atribución.

## Creación de un panel de atribución

1. Haga clic en el icono del panel de la izquierda.
1. Arrastre el panel Atribución adentro de su Proyecto de Analysis Workspace.

   ![Nuevo panel de atribución](assets/Attribution_Panel_1.png)

1. Añada una métrica a la que desee atribuir y agregue cualquier dimensión para atribuirla. Algunos ejemplos son Canales de marketing o dimensiones personalizadas, como las promociones internas.

   ![Seleccionar dimensión y métrica](assets/attribution_panel2.png)

1. Seleccione los modelos de [atribución y la ventana](../attribution/models.md) retroactiva que desee comparar.

1. El panel Atribución devuelve un completo conjunto de datos y visualizaciones que comparan la atribución para la dimensión y métrica seleccionadas.

   ![Visualizaciones de atribución](assets/attr_panel_vizs.png)

## Visualizaciones de atribución

* **Métrica** total: El número total de conversiones que se produjeron durante el período de tiempo de sistema de informes. Estas son las conversiones que se atribuyen a través de la dimensión seleccionada.
* **Gráfico** de la barra de comparación de atribución de métricas: Compara visualmente las conversiones atribuidas en cada uno de los elementos de dimensión de la dimensión seleccionada. Cada color de barra representa un modelo de atribución distinto.
* **Tabla** improvisada de atribución de métricas: Muestra los mismos datos que el gráfico de barras, representado como una tabla. Al seleccionar distintas columnas o filas en esta tabla, se filtros el gráfico de barras, así como varias de las demás visualizaciones del panel. Esta tabla actúa de forma similar a cualquier otra tabla improvisada en Workspace, lo que le permite agregar componentes como métricas, segmentos o desgloses.
* **Gráfico** de superposición de dimensión: Diagrama de Venn que muestra los tres valores de dimensión principales y la frecuencia con la que participan conjuntamente en una conversión. Por ejemplo, el tamaño de la superposición de burbujas indica la frecuencia con la que se produjeron las conversiones cuando un visitante estuvo expuesto a ambos valores de dimensión. Al seleccionar otras filas en la tabla improvisada adyacente, se actualiza la visualización para reflejar su selección.
* **Puntos de contacto de marketing por viaje**: Un histograma que indica el número de puntos de contacto que un visitante tuvo en la ventana retroactiva. Esto resulta útil para ver qué impacto tuvo la atribución de múltiples contactos para su conjunto de datos. Si casi todos los visitantes tienen un solo punto de contacto, es probable que distintos modelos de atribución muestren datos similares.
* **Detalle** de rendimiento de Canal de mercadotecnia: Permite comparar hasta tres modelos de atribución visualmente mediante un diagrama de puntos.
* **Flujo** de Canal de mercadotecnia: Permite ver con qué canales se interactúan con mayor frecuencia y en qué orden durante el viaje de un visitante.
