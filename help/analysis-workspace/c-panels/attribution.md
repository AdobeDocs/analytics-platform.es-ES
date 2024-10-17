---
title: Panel de Attribution
description: Utilizar e interpretar el panel de atribución en Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 44%

---

# Panel de Attribution {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_button"
>title="Atribución"
>abstract="Compare y visualice rápidamente los modelos de atribución utilizando cualquier dimensión y métrica de conversión"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panel de Attribution IQ"

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_panel"
>title="Panel de Attribution"
>abstract="Compare y visualice rápidamente los modelos de atribución utilizando cualquier dimensión y métrica de conversión.<br/><br/>**Parámetros **<br/>**Canal**<br/> Dimensión con la que se va a atribuir. Esta dimensión puede consistir en canales de marketing, campañas o cualquier otra dimensión.<br/>**Modelos**<br/> El modelo determina cómo se asigna crédito a puntos de contacto.<br/>**Ventana retroactiva**<br/> Este ajuste determina la ventana de atribución de datos que se aplica a cada conversión."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panel de Attribution IQ"

<!-- markdownlint-enable MD034 -->


El panel **[!UICONTROL Atribución]** es una forma sencilla de generar un análisis comparando varios modelos de atribución. El panel le proporciona un espacio de trabajo dedicado para utilizar y comparar modelos de atribución.

Customer Journey Analytics mejora la atribución al permitir lo siguiente:

* Defina la atribución más allá de los medios de pago: Cualquier dimensión, métrica, canal o evento se puede aplicar a modelos (por ejemplo, búsqueda interna), no solo a campañas de marketing.
* Utilice la comparación de modelos de atribución ilimitada: compare dinámicamente todos los modelos que desee.
* Evitar cambios de implementación: con el procesamiento de tiempo de informes y las sesiones con reconocimiento de contexto, el contexto de recorrido del cliente se puede generar y aplicar en el tiempo de ejecución.
* Construir la sesión más adecuada para su escenario de atribución.
* Desglosar la atribución por filtros: compare fácilmente el rendimiento de sus canales de marketing en cualquier filtro importante (por ejemplo, clientes nuevos frente a repetidos, producto X frente a producto Y, nivel de fidelidad o CLV).
* Inspeccionar análisis de canales cruzados y de múltiples contactos mediante Diagramas de Venn e Histogramas, y resultados de atribución de tendencias.
* Analizar visualmente secuencias de marketing clave: explore las rutas que generaron una conversión visualmente con las visualizaciones de visitas en el orden previsto y flujo de varios nodos.
* Generar métricas calculadas: Utilice todos los métodos de asignación de atribuciones que desee.

## En su lugar, utilice 

Para usar un panel **[!UICONTROL Atribución]**:

1. Cree un panel de **[!UICONTROL Atribución]**. Para obtener información sobre cómo crear un panel, consulte [Crear un panel](panels.md#create-a-panel).

1. Especifique [input](#panel-input) para el panel.

1. Observe la [salida](#panel-output) del panel.

### Entrada de panel

Puede configurar el panel Atribución con esta configuración de entrada:

1. Agregue una **[!UICONTROL métrica de éxito]** y una dimensión del **[!UICONTROL canal]** al que desee atribuir. Algunos ejemplos son Canales de marketing o dimensiones personalizadas, como las promociones internas.

   ![Ventana del panel Atribución que muestra varias dimensiones y métricas seleccionadas.](assets/attribution-panel.png)

1. Seleccione uno o más [modelos de atribución](#attribution-models) de **[!UICONTROL modelos incluidos]** y una [ventana retrospectiva](#lookback-window) de la **[!UICONTROL ventana retrospectiva]** que desee usar para la comparación.

1. Seleccione **[!UICONTROL Generar]** para generar las visualizaciones en el panel.

### Salida de panel

El panel **[!UICONTROL Atribución]** devuelve un conjunto completo de datos y visualizaciones que comparan la atribución para la dimensión y métrica seleccionadas.

![Visualizaciones del panel Atribución que comparan métricas y dimensiones seleccionadas.](assets/attr_panel_vizs.png)

### Visualizaciones de atribución

La siguiente visualización forma parte de la salida del panel.

* **Métrica total**: El número total de conversiones que ocurrieron durante la ventana de tiempo de generación de informes y que se atribuyen a la dimensión seleccionada.
* **Barra comparativa de la atribución**: Compara visualmente las conversiones atribuidas en cada uno de los elementos de dimensión de la dimensión seleccionada. Cada color de barra representa un modelo de atribución distinto.
* **Tabla comparativa de la atribución**: Muestra los mismos datos que el gráfico de barras, representados como una tabla. Al seleccionar distintas columnas o filas en esta tabla, se filtra el gráfico de barras, así como varias de las demás visualizaciones del panel. Esta tabla actúa de manera similar a cualquier otra tabla de forma libre en Workspace, lo que le permite agregar componentes como métricas, filtros o desgloses.
* **Diagrama de superposición**: una visualización de Venn que muestra los tres elementos de dimensión principales y la frecuencia con la que participan conjuntamente en una conversión. Por ejemplo, el tamaño de la superposición de burbujas indica con qué frecuencia ocurrieron las conversiones cuando una persona estuvo expuesta a ambos elementos de dimensión. Si se seleccionan otras filas en la Tabla de forma libre, se actualizará la visualización para reflejar su selección.
* **Detalles de rendimiento**: una visualización de dispersión para comparar visualmente hasta tres modelos de atribución.
* **Rendimiento de tendencias**: Muestra la tendencia de las conversiones atribuidas para el elemento de dimensión principal. Si se seleccionan otras filas en la Tabla de forma libre, se actualizará la visualización para reflejar su selección.
* **Flujo**: Permite ver en qué canales hay interacción con más frecuencia y en qué orden a través del recorrido de una persona.

## Modelos de atribución

{{attribution-models-details}}

## Ventana retroactiva

{{attribution-lookback-window}}

>[!MORELIKETHIS]
>
> [Crear un panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
