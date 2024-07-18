---
title: Vista de tendencias de conversión
description: Rastree los cambios en la tasa de conversión a lo largo del tiempo.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# [!UICONTROL Vista de tendencias de conversión]

La vista **[!UICONTROL Tendencias de conversión]** proporciona una visualización de tendencias de las tasas de conversión a lo largo del tiempo. El eje horizontal es un intervalo de tiempo, mientras que el eje vertical representa la tasa de conversión.

>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Rastrear esfuerzos de optimización**: después de identificar los cuellos de botella clave que desea mejorar mediante [Fricción](friction.md), puede usar esta vista para rastrear cómo esas optimizaciones afectan la tasa de conversión a lo largo del tiempo.
* **Evaluación de pruebas A/B**: Evalúe la eficacia de pruebas A/B o experimentos realizados en el contexto de un embudo. Al comparar las tasas de conversión entre diferentes variaciones, puede determinar fácilmente qué pruebas proporcionan tasas de conversión más altas, lo que lleva a decisiones basadas en datos sobre qué variaciones implementar de forma permanente.
* **Evaluación de campañas a lo largo del tiempo**: mida la eficacia de las campañas de marketing a lo largo del tiempo. Puede crear un segmento que se centre en los usuarios que hayan utilizado una campaña determinada y comparar sus tasas de conversión con las de otras campañas. También puede comparar las tasas de conversión actuales con campañas similares que se ejecutaron en el pasado.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Vista]**: cambie entre este tipo de vista y [Fricción](friction.md).
* **[!UICONTROL Pasos]**: Los puntos de contacto del evento que desea rastrear. Cada barra del gráfico representa un paso. Se pueden incluir hasta diez pasos.
* **[!UICONTROL Contado como]**: El método de conteo que desea aplicar a los eventos seleccionados. Las opciones incluyen [!UICONTROL Usuarios] y [!UICONTROL Sesiones].
* **[!UICONTROL Segmentos]**: Los segmentos con los que desea comparar el canal. Cada segmento seleccionado divide cada paso en varias barras. Cada color representa un segmento diferente. Se pueden incluir hasta tres segmentos.

## Ajustes del gráfico

La vista [!UICONTROL Tendencias de conversión] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: El tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Línea].
* **[!UICONTROL Conversión de]**: Determina el cálculo de porcentaje de un paso a otro. Las opciones incluyen calcular la conversión desde el [!UICONTROL Primer paso] o [!UICONTROL Paso anterior].

>[!NOTE]
>
>La columna **Average** de la tabla de vista de tendencias de conversión difiere de la columna **Total** de la tabla [Vista de fricción](friction.md). La primera es una media de las columnas de intervalo (por ejemplo, la media de las tasas de conversión diarias), mientras que la segunda es un cálculo agregado en todo el intervalo de fechas.

## Comparación del tiempo

{{apply-time-comparison}}

![Comparación temporal de tendencias de conversión](../assets/conversion-trends-compare.png){style="border:1px solid gray"}

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener intervalos diferentes, que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **[!UICONTROL Fecha]**: La fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
