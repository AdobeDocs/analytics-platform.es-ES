---
title: Análisis de la cronología
description: Observe los eventos de sesión a nivel de usuario a lo largo del tiempo para encontrar patrones de experiencia.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 100%

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
>&#x200B;><br/>Si una vista de datos no tiene añadido el componente [!UICONTROL ID de persona], se mostrará el siguiente mensaje:
>
>* **Administradores**: *la propiedad PersonID es necesaria para este análisis. Añada el ID de persona a la vista de datos.*
>* **No administradores**: *la propiedad PersonID es necesaria para este análisis. Póngase en contacto con el administrador de Customer Journey Analytics para añadir el ID de persona a la vista de datos.*

>[!VIDEO](https://video.tv.adobe.com/v/3435770/?quality=12&learn=on&captions=spa)



## Casos prácticos

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
