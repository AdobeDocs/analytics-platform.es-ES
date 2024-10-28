---
title: Análisis de tendencias
description: Medir la participación del usuario a lo largo del tiempo.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Análisis [!UICONTROL Tendencias] {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_trends_button"
>title="Tendencias"
>abstract="Medir la participación del usuario a lo largo del tiempo."

<!-- markdownlint-enable MD034 -->

El análisis ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Trends]** proporciona información valiosa sobre el rendimiento del producto o el comportamiento de los usuarios a lo largo del tiempo. El eje horizontal de este informe es un intervalo de tiempo, mientras que el eje vertical mide los eventos deseados.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Casos prácticos

Los casos de uso de este análisis incluyen:

* **Evaluar el rendimiento del producto**: Las tendencias permiten evaluar el rendimiento general del producto durante un período determinado. Al analizar métricas como la participación del usuario, la adopción o las tasas de conversión, puede identificar si el rendimiento del producto mejora, se estanca o disminuye.
* **Adopción de características**: las tendencias le permiten comprender cómo adoptan los usuarios las nuevas características o actualizaciones que usted publique. Puede determinar qué funciones son populares y qué funciones requieren mejora. Esta información le permite tomar decisiones basadas en datos sobre qué funciones priorizar los esfuerzos de desarrollo.
* **Comportamiento del usuario**: las tendencias pueden proporcionar una perspectiva del comportamiento del usuario a lo largo del tiempo. Al examinar las acciones específicas que realizan los usuarios, puede identificar patrones en los que estos pueden abandonarlos. Puede combinar información de este análisis con [Embudo](funnel.md) para obtener aún más información sobre el comportamiento.
* **Pruebas A/B y experimentación**: si ejecuta pruebas A/B en su producto, puede usar Tendencias para medir qué pruebas son las más exitosas a lo largo del tiempo.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener una descripción general de la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Vista]**: cambie entre este análisis y [Frecuencia](frequency.md).
* **[!UICONTROL Eventos y métricas]**: Los eventos o métricas que desea medir. Cada selección se representa como una serie de gráficos y una fila de tabla. Los eventos y las métricas no se pueden combinar en la consulta. Una vez que haya realizado la primera selección, las selecciones de consulta restantes deben ser del mismo tipo. Puede incluir hasta cinco selecciones.
* **[!UICONTROL Contado como]**: El método de conteo que desea aplicar a los eventos seleccionados. Las opciones incluyen Eventos, Sesiones, Usuarios, Porcentaje de usuarios, Eventos por sesión y Eventos por usuario. Las opciones Contadas como solo son aplicables a las consultas de evento y se eliminan para las consultas de métricas.
* **[!UICONTROL Segmentos]**: los segmentos que desea medir. Cada segmento seleccionado duplica el número de series de gráficos y filas de tabla. Se pueden incluir hasta cinco segmentos.
* **[!UICONTROL Breakdown property]**: desglosa la serie de gráficos y las filas de tabla según los valores de la propiedad seleccionada. Se admite una sola propiedad de desglose. Los 20 valores principales aparecen en la tabla y se pueden ver hasta diez valores en el gráfico. Puede ocultar o exponer una fila del gráfico alternando el icono ![Mostrar u ocultar](../assets/hide-in-chart.png).

### Ajustes del gráfico

El análisis [!UICONTROL Tendencias] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: El tipo de visualización que desea utilizar. Las opciones incluyen Línea, Barra, Barra apilada y Área apilada.

### Superposiciones

Agregue datos adicionales al gráfico. Cuando hay más de una serie visible en el gráfico, las superposiciones solo aparecen al pasar el ratón por encima.

* **[!UICONTROL Detección de anomalías]**: Ejecuta [detección de anomalías](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) en el análisis de tendencias. Los valores atípicos aparecen como puntos sobre los que puede situarse para obtener más información.
* **[!UICONTROL Superposición de línea de tendencia]**: agrega una línea de tendencia al gráfico, lo que ayuda a mostrar un patrón más claro en los datos.
   * [!UICONTROL Lineal]: Crea una línea de regresión recta. Ideal para datos lineales simples que aumentan o disminuyen a una velocidad constante. Ecuación: `y = a + b * x`
   * [!UICONTROL Logarítmico]: Crea una línea de regresión curva. Ideal para datos que aumentan o disminuyen rápidamente y luego se vuelven más nivelados. Ecuación: `y = a + b * log(x)`
   * [!UICONTROL Promedio móvil]: Crea una línea de tendencia suave basada en un conjunto de promedios. Un promedio móvil utiliza una cantidad determinada de puntos de datos anteriores (definida por su selección), los promedia y utiliza el promedio como punto en la línea. Algunos ejemplos son un promedio móvil de siete días o un promedio móvil de cuatro semanas. Las opciones de promedio móvil disponibles dependen del intervalo y el intervalo de fechas seleccionados.

### Comparación del tiempo

{{apply-time-comparison}}


### Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener diferentes intervalos que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **[!UICONTROL Fecha]**: La fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->