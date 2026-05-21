---
title: Análisis de la cronología
description: Observe los eventos de sesión a nivel de usuario a lo largo del tiempo para encontrar patrones de experiencia.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
TQID: https://experienceleague.adobe.com/17wzuDrTYs5VGC85jXh3eacQKO0-590t0K-XfggT6D4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 594
ht-degree: 97%

---

# Análisis de la [!UICONTROL cronología] {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="Cronología"
>abstract="Observe los eventos a nivel de la sesión a lo largo del tiempo."

<!-- markdownlint-enable MD034 -->

El análisis de ![Cronología](/help/assets/icons/Timeline.svg) **[!UICONTROL Cronología]** le permite observar los eventos de sesión a nivel de usuario a lo largo del tiempo para encontrar patrones de experiencia y contar mejores historias de usuario. El carril izquierdo le permite filtrar la secuencia por valores de propiedad y segmentos. El carril derecho le permite seleccionar en una lista aleatoria de usuarios que cumplen los criterios de filtro. El área central muestra la secuencia para el usuario seleccionado por sesión, que consta de la marca de tiempo, los valores de propiedad y la duración. La duración no está disponible para el último evento de una sesión determinada.


>[!NOTE]
>
>El análisis de [!UICONTROL Cronología] requiere que el componente estándar **[!UICONTROL ID de persona]** esté disponible en la [vista de datos](/help/data-views/component-reference.md#optional). El administrador de Customer Journey Analytics administra la inclusión del ID de persona en una vista de datos, lo que proporciona a su organización un control completo de la privacidad sobre quién puede acceder a estos datos.
><br/>Si una vista de datos no tiene añadido el componente [!UICONTROL ID de persona], se mostrará el siguiente mensaje:
>
>* **Administradores**: *la propiedad PersonID es necesaria para este análisis. Añada el ID de persona a la vista de datos.*
>* **No administradores**: *la propiedad PersonID es necesaria para este análisis. Póngase en contacto con el administrador de Customer Journey Analytics para añadir el ID de persona a la vista de datos.*

>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/timeline)



## Casos de uso

Los casos de uso de este análisis incluyen:

* **Exploración de la fricción**: si encuentra una caída pronunciada en el análisis [Análisis de canal](funnel.md), puede crear un segmento de esos usuarios y aplicarlo en este análisis para investigar las posibles causas.
* **Comportamiento del error**: si los usuarios encuentran un error en el producto, puede explorar qué hacían los usuarios antes o después de ver ese error.
* **Validación de la recopilación de datos**: los administradores de datos pueden filtrar este análisis en su propio ID de persona para validar que la implementación de su organización funcione según lo esperado.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener información general sobre la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Dimension]**: dimensión para la que desea ver los valores secuenciados. La secuencia en el centro muestra los valores de la dimensión seleccionada. También puede aplicar filtros para reducir la secuencia a datos más relevantes. Los operadores válidos para el filtro incluyen [!UICONTROL Es igual a], [!UICONTROL No es igual a], [!UICONTROL Comienza por], [!UICONTROL Termina por], [!UICONTROL Contiene], [!UICONTROL No contiene], [!UICONTROL Existe] y [!UICONTROL No existe].
* **[!UICONTROL Segmentos]**: el segmento que desea analizar. El segmento seleccionado filtra los datos para centrarse únicamente en las personas que cumplen los criterios del segmento. Si desea reducir el análisis a un ID de persona específico, puede filtrar ese ID de persona en el panel derecho. Se admite un segmento para este análisis.

### Configuración del gráfico

El análisis de [!UICONTROL Cronología] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Mostrar como]**: muestra los valores de propiedad deseados.
   * [!UICONTROL Mostrar todo]: muestra todos los valores de propiedad de una sesión.
   * [!UICONTROL Resaltar]: resalta visualmente los valores de propiedad de una sesión que coinciden con los filtros de la consulta.
   * [!UICONTROL Solo vista]: muestra solo los valores de propiedad de una sesión que coinciden con los filtros de la consulta.

### Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: la granularidad de la fecha por la que desea ver datos de tendencia. Este valor no afecta a los análisis sin tendencias, como la Cronología.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
