---
title: Panel de Attribution
description: Utilizar e interpretar el panel de atribución en Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
source-git-commit: c21eb39e0af36ad54fd675c147e2f50b6b00711a
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 94%

---

# Panel de Attribution

El panel [!UICONTROL Atribución] es una forma sencilla de generar un análisis comparando varios modelos de atribución. Es una función que le proporciona un espacio de trabajo dedicado para usar y comparar modelos de atribución.

Customer Journey Analytics mejora la atribución al permitir lo siguiente:

* Definir la atribución más allá del contenido multimedia de pago: cualquier dimensión, métrica, canal o evento puede aplicarse a modelos (por ejemplo, búsqueda interna), no solo a campañas de marketing.
* Utilizar la comparación de modelos de atribución sin límites: compare dinámicamente todos los modelos que desee.
* Evitar cambios de implementación: con el procesamiento de tiempo de informes y las sesiones con reconocimiento de contexto, el contexto del recorrido del cliente puede generarse y aplicarse en el tiempo de ejecución.
* Construir la sesión más adecuada para su escenario de atribución.
* Desglosar la atribución por filtros: compare fácilmente el rendimiento de sus canales de marketing en cualquier filtro importante (por ejemplo, clientes nuevos frente a repetidos, producto X frente a producto Y, nivel de fidelidad o CLV).
* Inspeccionar análisis de canales cruzados y de múltiples contactos mediante Diagramas de Venn e Histogramas, y resultados de atribución de tendencias.
* Analizar visualmente secuencias de marketing clave: explore las rutas que generaron una conversión visualmente con las visualizaciones de visitas en el orden previsto y flujo de varios nodos.
* Generar métricas calculadas: Utilice todos los métodos de asignación de atribuciones que desee.

## Creación de un panel de atribución

1. Haga clic en el icono de panel situado en la izquierdo.
1. Arrastre el panel [!UICONTROL Atribución] a su Proyecto de Analysis Workspace.

   ![Nuevo panel de atribución](assets/Attribution_Panel_1.png)

1. Añada una métrica a la que desee atribuir y agregue cualquier dimensión para atribuirla. Algunos ejemplos son Canales de marketing o dimensiones personalizadas, como las promociones internas.

   ![Seleccionar dimensión y métrica](assets/attribution_panel2.png)

1. Seleccione los modelos de atribución y la ventana retrospectiva que desee comparar.

1. El panel Atribución devuelve un conjunto completo de datos y visualizaciones que comparan la atribución para la dimensión y métrica seleccionadas.

   ![Visualizaciones de atribución](assets/attr_panel_vizs.png)

## Visualizaciones de atribución

* **Métrica total**: El número total de conversiones que tienen lugar durante el periodo establecido por la ventana de creación de informes. Estas son las conversiones que se atribuyen a través de la dimensión seleccionada.
* **Barra comparativa de la atribución**: Compara visualmente las conversiones atribuidas en cada uno de los elementos de dimensión de la dimensión seleccionada. Cada color de barra representa un modelo de atribución distinto.
* **Tabla comparativa de la atribución**: Muestra los mismos datos que el gráfico de barras, representados como una tabla. Al seleccionar distintas columnas o filas en esta tabla, se filtra el gráfico de barras, así como varias de las demás visualizaciones del panel. Esta tabla actúa de manera similar a cualquier otra tabla de forma libre en Workspace, lo que le permite añadir componentes como métricas, filtros o desgloses.
* **Diagrama de superposición**: Un diagrama de Venn que muestra los tres elementos de dimensión principales y la frecuencia con la que participan conjuntamente en una conversión. Por ejemplo, el tamaño de la superposición de burbujas indica con qué frecuencia ocurrieron las conversiones cuando un visitante estuvo expuesto a ambos elementos de dimensión. Si se seleccionan otras filas en la Tabla de forma libre, se actualizará la visualización para reflejar su selección.
* **Detalles de rendimiento**: Permite comparar visualmente hasta tres modelos de atribución mediante un diagrama de puntos.
* **Rendimiento de tendencias**: Muestra la tendencia de las conversiones atribuidas para el elemento de dimensión principal. Si se seleccionan otras filas en la Tabla de forma libre, se actualizará la visualización para reflejar su selección.
* **Flujo**: Permite ver en qué canales hay interacción con más frecuencia y en qué orden a lo largo del recorrido de un visitante.
