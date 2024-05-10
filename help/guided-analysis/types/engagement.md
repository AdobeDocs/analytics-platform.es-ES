---
title: Vista de participación
description: Comprenda la amplitud y la anchura de la participación de las funciones.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# [!UICONTROL Participación] vista

El **[!UICONTROL Participación]** La vista de proporciona una perspectiva de la frecuencia con la que se utiliza una función en comparación con la cantidad de personas que la utilizan. Este análisis funciona mejor cuando se comparan varias funciones entre sí.

Las funciones que se representan en la parte superior de esta visualización indican que se visita con frecuencia entre las personas que la utilizan. Las características que se representan a la derecha de esta visualización indican que la mayor proporción de usuarios que interactúan con la característica. La mediana de veces que se utiliza una función divide el gráfico horizontalmente. El porcentaje medio de usuarios activos diarios divide el gráfico verticalmente.

* Las funciones de la parte superior izquierda de la matriz significan que una función no se ha adoptado ampliamente. Sin embargo, entre las personas que lo utilizan, lo hacen con frecuencia.
* Las funciones de la parte superior derecha de la matriz significan que una función se adopta ampliamente y se utiliza con frecuencia.
* Las funciones de la parte inferior derecha de la matriz significan que una función se adopta ampliamente, pero no se utiliza con frecuencia.
* Las funciones de la parte inferior izquierda de la matriz significan que una función no se adopta ampliamente ni se utiliza con frecuencia.

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Participación por función**: puede establecer una correlación directa entre la participación y la adopción de una función específica. Comprender qué funciones se utilizan más puede ayudar a determinar qué funciones priorizar para mejorar.
* **Descubra las funciones infrautilizadas**: funciones con usuarios activos diarios bajos, pero un uso elevado, pueden indicar una función oculta, pero valiosa. Considere la posibilidad de exponer este tipo de funciones a más usuarios.
* **Mejora de funciones populares**: las funciones con usuarios activos altos pero un uso bajo pueden indicar que una función es muy solicitada pero no se utiliza suficientemente. Considere la posibilidad de invertir en mejorar estas funciones para que se utilicen con más frecuencia.
* **Creación de segmentos basados en funciones**: El análisis de la frecuencia con la que se utiliza una función respecto a la cantidad de usuarios que la adoptan puede ayudar a determinar los tipos de usuarios que adoptan una función determinada. Puede crear segmentos basados en usuarios que utilicen una función de forma informal o en usuarios que utilicen esa función con frecuencia.
* **Prueba A/B de adopción de funciones**: Compare el uso de varias funciones mediante segmentos. Añada los segmentos de cada cohorte en el carril de consulta para determinar la diferencia en el uso de las funciones fácilmente.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Eventos]**: los eventos que desea medir. Estos eventos suelen representar el uso de una función determinada. Cada selección se representa como un punto dentro de la matriz. Se pueden incluir hasta diez eventos.
* **[!UICONTROL Contabilizado como]**: determine los detalles de cómo cuenta los usuarios el eje x. Puede medir el porcentaje promedio de usuarios activos diarios, semanales, mensuales o trimestrales. El eje Y ajusta automáticamente el promedio de veces por usuario en función de la selección del eje X.
* **[!UICONTROL Segmentos]**: los segmentos que desea medir. Cada segmento seleccionado duplica el número de puntos trazados en el gráfico y las filas de la tabla. Se pueden incluir hasta tres segmentos.

## Ajustes del gráfico

El [!UICONTROL Participación] La vista ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Medianas]**: Determine dónde se muestran las líneas medias y cómo se relacionan los puntos trazados con esas medianas.
   * **[!UICONTROL Standard]**: Mostrar el valor absoluto de uso y participación.
   * **[!UICONTROL Normalizado]**: mostrar los cambios relativos de cada mediana.
* **[!UICONTROL Superposición de eventos principales]**: vea el comportamiento de los eventos en comparación con los eventos más comunes.

## Comparación del tiempo

{{apply-time-comparison}}

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencia. Este tipo de vista trata [!UICONTROL Intervalo] de manera similar a [!UICONTROL Contabilizado como] en el carril de consultas. No se admiten usuarios activos por hora.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
