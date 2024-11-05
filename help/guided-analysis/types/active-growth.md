---
title: Análisis activo del crecimiento
description: Identifique quién es nuevo, retenido, retornado o inactivo.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 5%

---

# Análisis del [!UICONTROL crecimiento activo] {#active-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_activegrowth_button"
>title="Crecimiento activo"
>abstract="Identifique quién es nuevo, retenido, retornado o inactivo."

<!-- markdownlint-enable MD034 -->


El análisis ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Crecimiento activo]** proporciona información sobre el crecimiento y la adquisición de usuarios durante un período específico. El eje horizontal es un intervalo de tiempo, mientras que el eje vertical es una medida de usuarios. Los usuarios se dividen en cuatro categorías:

* **[!UICONTROL Nuevo]**: el usuario estaba activo durante el período actual, pero no anteriormente. Vea hasta dónde llega el análisis pasando el puntero sobre _[!UICONTROL Nuevos usuarios]_ en la leyenda del gráfico. El intervalo de retrospectiva se determina dinámicamente en función del intervalo de fechas y del intervalo seleccionados.
* **[!UICONTROL Repetir]**: el usuario estaba activo en el período actual y en el anterior.
* **[!UICONTROL Devolver]**: el usuario estaba activo en el período actual y no estaba activo en el período inmediatamente anterior, pero anteriormente estaba activo en algún momento. Vea hasta dónde llega el análisis pasando el puntero sobre _[!UICONTROL Devolver usuarios]_ en la leyenda del gráfico. El intervalo de retrospectiva se determina dinámicamente en función del intervalo de fechas y del intervalo seleccionados.
* **[!UICONTROL Inactivo]**: el usuario estaba activo en el período inmediatamente anterior, pero no lo está en el período actual. Los usuarios inactivos no se contabilizan en el número total de usuarios activos.

Todos los usuarios activos (nuevos + repetidos + devueltos) aparecen como un tono de verde azulado encima del eje horizontal, mientras que todos los usuarios inactivos aparecen en naranja debajo del eje horizontal.


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Casos prácticos

Los casos de uso de este análisis incluyen:

* **Retención y pérdida de usuarios:** Proporciona una clara visualización de los períodos de retención de usuarios alta o baja. Reconocer estos períodos de retención alta o baja puede ayudarle a tomar decisiones sobre productos para fomentar una retención alta o ayudar a minimizar la pérdida.
* **Evaluación de la campaña**: Ver una campaña específica puede ayudarle a comprender cuánto tráfico generó y en qué medida ayudó a los usuarios a seguir participando.
* **Análisis del ciclo de vida del usuario**: Analizar el crecimiento activo del usuario a lo largo del ciclo de vida del usuario puede ayudar a identificar fases específicas en las que disminuye la participación del usuario. Por ejemplo, si hay una alta proporción de usuarios latentes para personas en una fase de incorporación, puede indicar problemas de uso o la necesidad de mejorar la orientación interna del producto.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener una descripción general de la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Vista]**: cambie entre este análisis y [Crecimiento neto](net-growth.md).
* **[!UICONTROL Eventos]**: El evento que desea medir. Dado que este análisis se basa en el usuario, un usuario que interactúa con el evento una vez dentro del periodo se cuenta como un usuario activo. Puede incluir un evento en una consulta.
* **[!UICONTROL Contado como]**: El método de conteo que desea aplicar a los eventos seleccionados. Las opciones incluyen [!UICONTROL Número de usuarios] y [!UICONTROL Porcentaje de usuarios].
* **[!UICONTROL Segmentos]**: Segmento por el que desea filtrar los datos. Puede incluir un segmento en una consulta.

### Ajustes del gráfico

El análisis [!UICONTROL Crecimiento activo] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: El tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Barra apilada] y [!UICONTROL Área apilada].

### Comparación del tiempo

{{apply-time-comparison}}

### Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener intervalos diferentes, que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **[!UICONTROL Fecha]**: La fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
