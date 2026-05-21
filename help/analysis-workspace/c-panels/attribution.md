---
title: Panel de atribución
description: Aprenda a utilizar e interpretar el panel de atribución en Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
TQID: https://experienceleague.adobe.com/sMLOCsAtZVm-fyHPTkPl-ftUHt3k7DvjPrDYPAuAQTw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5520579-b31f-4df7-9281-f0d9f91e2edc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 689
ht-degree: 90%

---

# Panel de atribución {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Atribución"
>abstract="Compare y visualice rápidamente cualquier número de los modelos de atribución utilizando la métrica de éxito, el canal y la ventana retroactiva."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panel de Attribution IQ"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Panel de atribución"
>abstract="Compare y visualice rápidamente cualquier número de los modelos de atribución de una métrica de éxito. Seleccione el canal (dimensión), los modelos que desea incluir y la ventana retrospectiva."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panel de Attribution IQ"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artículo documenta el panel Atribución en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Vea [Panel Atribución](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/panels/attribution) para la_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** versión de este artículo._

>[!ENDSHADEBOX]

El panel **[!UICONTROL Atribución]** es una forma sencilla de generar un análisis comparando varios modelos de atribución. El panel le proporciona un espacio de trabajo dedicado para utilizar y comparar modelos de atribución.

Customer Journey Analytics mejora la atribución al permitir lo siguiente:

* Definir la atribución más allá del contenido multimedia de pago: cualquier dimensión, métrica, canal o evento puede aplicarse a modelos (por ejemplo, búsqueda interna), no solo campañas de marketing.
* Utilizar la comparación de modelos de atribución sin límites: compare dinámicamente todos los modelos que desee.
* Evitar cambios de implementación: con el procesamiento de tiempo de los informes y las sesiones según el contexto, el contexto del recorrido del cliente puede incorporarse y aplicarse en tiempo de ejecución.
* Construir la sesión más adecuada para su escenario de atribución.
* Desglosar la atribución por segmentos: compare fácilmente el rendimiento de sus canales de marketing en cualquier segmento importante (por ejemplo, clientes nuevos frente a repetidos, producto X frente a producto Y, nivel de lealtad o CLV).
* Inspeccionar análisis de canales cruzados y de múltiples contactos mediante Diagramas de Venn e Histogramas, y resultados de atribución de tendencias.
* Analizar visualmente secuencias de marketing clave: explore las rutas que generaron una conversión visualmente con las visualizaciones de visitas en el orden previsto y flujo de varios nodos.
* Generar métricas calculadas: Utilice todos los métodos de asignación de atribuciones que desee.

## Utiliza

Para usar un panel **[!UICONTROL Atribución]**:

1. Cree un panel **[!UICONTROL Atribución]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.

### Entrada de panel

Puede configurar el panel Atribución con esta configuración de entrada:

1. Añada una **[!UICONTROL métrica de éxito]** y una dimensión del **[!UICONTROL canal]** que desee atribuir. Algunos ejemplos son Canales de marketing o dimensiones personalizadas, como las promociones internas.

   ![Ventana del panel Atribución que muestra varias dimensiones y métricas seleccionadas.](assets/attribution-panel.png)

1. Seleccione uno o más [modelos de atribución](#attribution-models) de **[!UICONTROL modelos incluidos]**, el [contenedor](#container) de **[!UICONTROL Contenedor]** y una [ventana retrospectiva](#lookback-window) de la **[!UICONTROL ventana retrospectiva]** que desee usar para la comparación.

1. Seleccione **[!UICONTROL Generar]** para generar las visualizaciones en el panel.

### Salida del panel

El panel **[!UICONTROL Atribución]** devuelve un conjunto completo de datos y visualizaciones que comparan la atribución para la dimensión y la métrica seleccionadas.

![Visualizaciones del panel Atribución que comparan métricas y dimensiones seleccionadas.](assets/attr_panel_vizs.png)

### Visualizaciones de atribución

La siguiente visualización forma parte de la salida del panel.

* **Métrica total**: El número total de conversiones que ocurrieron durante la ventana de tiempo de creación de informes y que se atribuyen a la dimensión seleccionada.
* **Barra comparativa de la atribución**: Compara visualmente las conversiones atribuidas en cada uno de los elementos de dimensión de la dimensión seleccionada. Cada color de barra representa un modelo de atribución distinto.
* **Tabla comparativa de la atribución**: Muestra los mismos datos que el gráfico de barras, representados como una tabla. Al seleccionar distintas columnas o filas en esta tabla, se segmenta el gráfico de barras, así como varias de las demás visualizaciones del panel. Esta tabla actúa de manera similar a cualquier otra tabla de forma libre en Workspace, lo que le permite añadir componentes como métricas, segmentos o desgloses.
* **Diagrama de superposición**: Un diagrama de Venn que muestra los tres elementos de dimensión principales y la frecuencia con la que participan conjuntamente en una conversión. Por ejemplo, el tamaño del solapamiento de burbujas indica con qué frecuencia ocurrieron las conversiones cuando una persona estuvo expuesta a ambos elementos de dimensión. Si se seleccionan otras filas en la Tabla de forma libre adyacente, se actualizará la visualización para reflejar su selección.
* **Detalles de rendimiento**: una visualización de puntos para comparar visualmente hasta tres modelos de atribución.
* **Rendimiento de tendencias**: Muestra la tendencia de las conversiones atribuidas para el elemento de dimensión principal. Si se seleccionan otras filas en la Tabla de forma libre adyacente, se actualizará la visualización para reflejar su selección.
* **Flujo**: le permite ver con qué canales se interactúa con más frecuencia y en qué orden a lo largo del recorrido de una persona.

## Modelo de atribución

{{attribution-models-details}}

## Contenedor

{{attribution-container}}

## Ventana de retroactividad

{{attribution-lookback-window}}

## Ejemplo

{{attribution-example}}

>[!MORELIKETHIS]
>
> [Crear un panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
