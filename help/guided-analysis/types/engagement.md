---
title: Análisis de participación
description: Comprenda la amplitud y profundidad de la participación de la característica.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 6%

---

# Análisis de la [!UICONTROL participación] {#engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_engagement_button"
>title="Participación"
>abstract="Comprenda la amplitud y profundidad de la participación de la característica."

<!-- markdownlint-enable MD034 -->


El análisis ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) **[!UICONTROL Engagement]** proporciona una perspectiva de la frecuencia con la que se usa una característica en comparación con la cantidad de personas que la usan. Este análisis funciona mejor cuando se comparan varias funciones entre sí. Ayuda a impulsar las decisiones de inversión al comprender cuáles son su núcleo, su potencia, sus características únicas y cuestionables.

Las funciones que trazan hacia la parte superior de esta visualización indican que se utilizan con frecuencia entre usuarios comprometidos. Las funciones que se representan a la derecha de esta visualización indican que se adoptan ampliamente entre los usuarios activos. La mediana de veces que se utiliza una función divide el gráfico horizontalmente. El porcentaje medio de usuarios activos divide el gráfico verticalmente. Las medianas se calculan en función de los eventos seleccionados en la consulta, no de todos los datos.

* Las características de la parte superior izquierda de la matriz son las características de **power**; no son ampliamente adoptadas, pero las utilizan con frecuencia usuarios comprometidos.
* Las características de la parte superior derecha de la matriz son las características de **alto impacto**; son ampliamente adoptadas y se utilizan con frecuencia.
* Las características de la parte inferior izquierda de la matriz son las características de **bajo impacto**; no se adoptan ampliamente ni se utilizan con frecuencia.
* Las características de la parte inferior derecha de la matriz son las características de **una sola vez**; se han adoptado ampliamente, pero no se utilizan con frecuencia.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)


## Casos prácticos

Los casos de uso de este análisis incluyen:

* **Participación por característica**: puede establecer una correlación directa entre la participación y la adopción de una característica específica. Comprender qué características se utilizan más puede ayudar a determinar en qué características invertir más.
* **Descubrir características que no se utilizan suficientemente**: Las características con usuarios activos bajos pero un uso alto pueden indicar una característica de energía, que es valiosa pero que no ha sido descubierta ni utilizada por la población en general. Considere la posibilidad de mejorar la capacidad de detección de estas funciones para que más usuarios las aprovechen.
* **Mejorar características populares**: Las características con usuarios activos altos pero con un uso bajo pueden indicar que una característica es muy solicitada pero no se utiliza lo suficiente. Estas situaciones presentan oportunidades para obtener más información de los usuarios sobre las mejoras que harían que la función fuera más valiosa para ellos.
* **Crear segmentos basados en características**: Ver el uso de características de esta manera para solicitar oportunidades de análisis adicionales. Cree un segmento para cualquier punto del gráfico para profundizar en ese grupo de usuarios y aplicar esas lecciones a su estrategia de participación del usuario.
* **Prueba A/B de adopción de características**: compare el uso de varias características en diferentes grupos de usuarios. Añada segmentos al carril de la consulta para determinar la diferencia en el uso de las funciones entre grupos de usuarios clave.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener una descripción general de la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Eventos]**: los eventos que desea medir. Cada evento representa el uso de una función determinada y se muestra como un punto dentro de la matriz. Se pueden incluir hasta diez eventos. La mediana se calcula en función de los eventos seleccionados.
* **[!UICONTROL Contado como]**: a lo largo del eje x, puede medir el porcentaje promedio de usuarios activos diarios, semanales, mensuales o trimestrales. El eje Y ajusta automáticamente el promedio de veces por usuario en función de la selección del eje X.
* **[!UICONTROL Segmentos]**: los segmentos que desea medir. Cada segmento seleccionado duplica el número de puntos trazados en el gráfico y las filas de la tabla. Se pueden incluir hasta tres segmentos.

>[!TIP]
>
>Si varios eventos representan el uso de una sola función, puede derivar un nuevo evento que represente la función en Vistas de datos.

### Ajustes del gráfico

El análisis [!UICONTROL Participación] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Medianas]**: Determine dónde se muestran las líneas medias y cómo se relacionan los puntos trazados con esas medianas.
   * **[!UICONTROL Estándar]**: mostrar el valor absoluto de uso y participación.
   * **[!UICONTROL Normalizado]**: mostrar los cambios relativos de cada mediana.
* **[!UICONTROL Superposición de eventos principales]**: vea el rendimiento de los eventos en comparación con los 20 eventos principales, según la actualización y relevancia de la empresa y el usuario (el mismo algoritmo aplicado al selector de eventos en el carril de consultas).

### Comparación del tiempo

{{apply-time-comparison}}

### Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver datos de tendencia. Este análisis trata [!UICONTROL Intervalo] de manera similar a [!UICONTROL Contado como] en el carril de consultas. No se admiten usuarios activos por hora.
* **[!UICONTROL Fecha]**: La fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
