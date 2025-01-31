---
title: Análisis de tendencias de conversión
description: Rastree los cambios en la tasa de conversión a lo largo del tiempo.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 7%

---

# Análisis de [!UICONTROL tendencias de frecuencia] {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="Tendencias de conversión"
>abstract="Haga un seguimiento de los cambios en las tasas de conversión a lo largo del tiempo."

<!-- markdownlint-enable MD034 -->


El análisis ![Tendencias de conversión](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL Tendencias de conversión]** proporciona una visualización de tendencias de las tasas de conversión a lo largo del tiempo. El eje horizontal es un intervalo de tiempo, mientras que el eje vertical representa la tasa de conversión.


>[!VIDEO](https://video.tv.adobe.com/v/3421662/?quality=12&learn=on)


## Casos prácticos

Los casos de uso de este análisis incluyen:

* **Rastrear esfuerzos de optimización**: después de identificar los cuellos de botella clave que desea mejorar mediante el análisis [Embudo](funnel.md), puede usar este análisis para rastrear cómo esas optimizaciones afectan la tasa de conversión a lo largo del tiempo.
* **Evaluación de pruebas A/B**: Evalúe la eficacia de pruebas A/B o experimentos realizados en el contexto de un embudo. Al comparar las tasas de conversión entre diferentes variaciones, puede determinar fácilmente qué pruebas proporcionan tasas de conversión más altas, lo que lleva a decisiones basadas en datos sobre qué variaciones implementar de forma permanente.
* **Evaluación de campañas a lo largo del tiempo**: mida la eficacia de las campañas de marketing a lo largo del tiempo. Puede crear un segmento que se centre en los usuarios que hayan utilizado una campaña determinada y comparar sus tasas de conversión con las de otras campañas. También puede comparar las tasas de conversión actuales con campañas similares que se ejecutaron en el pasado.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener una descripción general de la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Vista]**: cambiar entre este análisis y [Canal](funnel.md).
* **[!UICONTROL Pasos]**: Los puntos de contacto del evento que desea rastrear. Cada barra del gráfico representa un paso. Se pueden incluir hasta diez pasos.
* **[!UICONTROL Contabilizado como]**: método de contabilización que desea aplicar a los eventos seleccionados. Las opciones incluyen [!UICONTROL Usuarios] y [!UICONTROL Sesiones].
* **[!UICONTROL Segmentos]**: Los segmentos con los que desea comparar el canal. Cada segmento seleccionado divide cada paso en varias barras. Cada color representa un segmento diferente. Se pueden incluir hasta tres segmentos.

### Ajustes del gráfico

El análisis [!UICONTROL Tendencias de conversión] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: El tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Línea].
* **[!UICONTROL Conversión de]**: Determina el cálculo de porcentaje de un paso a otro. Las opciones incluyen calcular la conversión desde el [!UICONTROL Primer paso] o [!UICONTROL Paso anterior].

>[!NOTE]
>
>La columna **Average** de la tabla de análisis de tendencias de conversión difiere de la columna **Total** de la tabla [Análisis de canal](funnel.md). La primera es una media de las columnas de intervalo (por ejemplo, la media de las tasas de conversión diarias), mientras que la segunda es un cálculo agregado en todo el intervalo de fechas.

### Comparación del tiempo

{{apply-time-comparison}}


### Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener intervalos diferentes, que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **[!UICONTROL Fecha]**: La fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
