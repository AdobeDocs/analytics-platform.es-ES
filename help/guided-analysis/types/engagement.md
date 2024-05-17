---
title: Vista de participación
description: Comprenda la amplitud y profundidad de la participación de las funciones.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: a4c35466b225d44130bb55204e2fdb155fa7dee6
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 3%

---

# [!UICONTROL Participación] vista

El **[!UICONTROL Participación]** La vista de proporciona una perspectiva de la frecuencia con la que se utiliza una función en comparación con la cantidad de personas que la utilizan. Este análisis funciona mejor cuando se comparan varias funciones entre sí. Ayuda a impulsar las decisiones de inversión al comprender cuáles son su núcleo, su potencia, sus características únicas y cuestionables.

Las funciones que trazan hacia la parte superior de esta visualización indican que se utilizan con frecuencia entre usuarios comprometidos. Las funciones que se representan a la derecha de esta visualización indican que se adoptan ampliamente entre los usuarios activos. La mediana de veces que se utiliza una función divide el gráfico horizontalmente. El porcentaje medio de usuarios activos divide el gráfico verticalmente. Las medianas se calculan en función de los eventos seleccionados en la consulta, no de todos los datos.

* Las funciones de la parte superior izquierda de la matriz son las siguientes **poder** funciones; no se adoptan ampliamente, pero los utilizan con frecuencia usuarios comprometidos.
* Las funciones de la parte superior derecha de la matriz son las siguientes **alto impacto** características; son ampliamente adoptados y utilizados con frecuencia.
* Las funciones de la parte inferior izquierda de la matriz son las siguientes **bajo impacto** características; no son ampliamente adoptados o utilizados con frecuencia.
* Las funciones de la parte inferior derecha de la matriz son las siguientes **único** características; son ampliamente adoptados, pero no se utilizan con frecuencia.

![Captura de pantalla Participación](../assets/feature-matrix.png)

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Participación por función**: puede establecer una correlación directa entre la participación y la adopción de una función específica. Comprender qué características se utilizan más puede ayudar a determinar en qué características invertir más.
* **Descubra las funciones infrautilizadas**: Las funciones con usuarios activos bajos, pero un uso alto, pueden indicar una función de energía que es valiosa, pero que no descubre ni utiliza la población en general. Considere la posibilidad de mejorar la capacidad de detección de estas funciones para que más usuarios las aprovechen.
* **Mejora de funciones populares**: las funciones con usuarios activos altos pero un uso bajo pueden indicar que una función es muy solicitada pero no se utiliza suficientemente. Estas situaciones presentan oportunidades para obtener más información de los usuarios sobre las mejoras que harían que la función fuera más valiosa para ellos.
* **Creación de segmentos basados en funciones**: visualización del uso de funciones de esta manera para ofrecer oportunidades de análisis adicionales. Cree un segmento para cualquier punto del gráfico para profundizar en ese grupo de usuarios y aplicar esas lecciones a su estrategia de participación del usuario.
* **Prueba A/B de adopción de funciones**: compare el uso de varias funciones entre diferentes grupos de usuarios. Añada segmentos al carril de la consulta para determinar la diferencia en el uso de las funciones entre grupos de usuarios clave.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Eventos]**: los eventos que desea medir. Cada evento representa el uso de una función determinada y se muestra como un punto dentro de la matriz. Se pueden incluir hasta diez eventos. La mediana se calcula en función de los eventos seleccionados.
* **[!UICONTROL Contabilizado como]**: A lo largo del eje x, puede medir el porcentaje promedio de usuarios activos diarios, semanales, mensuales o trimestrales. El eje Y ajusta automáticamente el promedio de veces por usuario en función de la selección del eje X.
* **[!UICONTROL Segmentos]**: los segmentos que desea medir. Cada segmento seleccionado duplica el número de puntos trazados en el gráfico y las filas de la tabla. Se pueden incluir hasta tres segmentos.

>[!TIP]
>
>Si varios eventos representan el uso de una sola función, puede derivar un nuevo evento que represente la función en Vistas de datos.

## Ajustes del gráfico

El [!UICONTROL Participación] La vista ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Medianas]**: Determine dónde se muestran las líneas medias y cómo se relacionan los puntos trazados con esas medianas.
   * **[!UICONTROL Standard]**: Mostrar el valor absoluto de uso y participación.
   * **[!UICONTROL Normalizado]**: mostrar los cambios relativos de cada mediana.
* **[!UICONTROL Superposición de eventos principales]**: vea el rendimiento de los eventos en comparación con los 20 eventos principales, en función de la actualización y relevancia de la empresa y el usuario (el mismo algoritmo aplicado al selector de eventos en el carril de consultas).

## Comparación del tiempo

{{apply-time-comparison}}

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencia. Este tipo de vista trata [!UICONTROL Intervalo] de manera similar a [!UICONTROL Contabilizado como] en el carril de consultas. No se admiten usuarios activos por hora.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
