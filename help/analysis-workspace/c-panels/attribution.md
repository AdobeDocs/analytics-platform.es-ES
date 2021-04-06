---
title: Panel de Attribution
description: Utilizar e interpretar el panel de atribución en Analysis Workspace.
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 60%

---

# Panel de Attribution

El panel [!UICONTROL Atribución] es una forma sencilla de generar un análisis comparando varios modelos de atribución. Es una funcionalidad de [Attribution IQ](../attribution/overview.md) que le proporciona un espacio de trabajo dedicado para usar y comparar modelos de atribución.

## Creación de un panel de atribución

1. Haga clic en el icono de panel situado en la izquierdo.
1. Arrastre el panel [!UICONTROL Atribución] a su proyecto de Analysis Workspace.

   ![Nuevo panel de atribución](assets/Attribution_Panel_1.png)

1. Añada una métrica a la que desee atribuir y agregue cualquier dimensión para atribuirla. Algunos ejemplos son Canales de marketing o dimensiones personalizadas, como las promociones internas.

   ![Seleccionar dimensión y métrica](assets/attribution_panel2.png)

1. Seleccione los modelos de [atribución y la ventana retrospectiva](../attribution/models.md) que desee comparar.

1. El panel Atribución devuelve un conjunto completo de datos y visualizaciones que comparan la atribución para la dimensión y métrica seleccionadas.

   ![Visualizaciones de atribución](assets/attr_panel_vizs.png)

## Visualizaciones de atribución

* **Métrica total**: El número total de conversiones que tienen lugar durante el periodo establecido por la ventana de creación de informes. Estas son las conversiones que se atribuyen a través de la dimensión seleccionada.
* **Barra de comparación de atribución**: Compara visualmente las conversiones atribuidas en cada uno de los elementos de dimensión de la dimensión seleccionada. Cada color de barra representa un modelo de atribución distinto.
* **Tabla** de comparación de atribución: Muestra los mismos datos que el gráfico de barras, representados como una tabla. Al seleccionar distintas columnas o filas en esta tabla, se filtra el gráfico de barras, así como varias de las demás visualizaciones del panel. Esta tabla actúa de forma similar a cualquier otra tabla improvisada en Workspace, lo que le permite agregar componentes como métricas, filtros o desgloses.
* **Diagrama** de superposición: Diagrama de Venn que muestra los tres elementos de dimensión principales y la frecuencia con la que participan conjuntamente en una conversión. Por ejemplo, el tamaño de la superposición de burbujas indica con qué frecuencia ocurrieron las conversiones cuando un visitante estuvo expuesto a ambos elementos de dimensión. Si se seleccionan otras filas en la Tabla improvisada, se actualizará la visualización para reflejar su selección.
* **Detalles** de rendimiento: Permite comparar visualmente hasta tres modelos de atribución mediante un diagrama de puntos.
* **Rendimiento** de tendencias: Muestra la tendencia de las conversiones atribuidas para el elemento de dimensión principal. Si se seleccionan otras filas en la Tabla improvisada, se actualizará la visualización para reflejar su selección.
* **Flujo**: Permite ver en qué canales hay interacción con más frecuencia y en qué orden a través del recorrido de un visitante.
