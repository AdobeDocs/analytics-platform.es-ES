---
title: Vista de crecimiento neto
description: ¿Está ganando o perdiendo usuarios?
feature: Guided Analysis
source-git-commit: 4cae5968e2ae1b6048522b9eb065d4b6e2272938
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 1%

---

# [!UICONTROL Crecimiento neto] vista

El **[!UICONTROL Crecimiento neto]** tipo de vista proporciona perspectivas sobre la tasa a la que gana o pierde usuarios durante un periodo específico. El eje horizontal es un intervalo de tiempo, mientras que el eje vertical es la medida del crecimiento.

Cada punto de datos representa el crecimiento neto, que se calcula mediante la siguiente fórmula:

`([New users] + [Return users]) / [Dormant users]`

El resultado de esta fórmula es una proporción. Un crecimiento neto de `1` representa un equilibrio; el producto ganó el mismo número de usuarios que perdió. Un crecimiento neto bueno que `1` representa un crecimiento positivo; había más usuarios nuevos y recurrentes que usuarios inactivos. Del mismo modo, un crecimiento neto menor que `1` representa una pérdida; había más usuarios inactivos que nuevos usuarios + que devolvían.

Similar a la [Activo](active.md) Tipo de vista, los usuarios se definen de la siguiente manera:

* **[!UICONTROL Nuevo]**: el usuario estuvo activo durante el periodo actual, pero no anteriormente. Consulte hasta dónde llega el análisis para determinar un nuevo usuario pasando el puntero sobre &#39;[!UICONTROL Nuevos usuarios]&#39; en la leyenda del gráfico. El intervalo de retrospectiva se determina dinámicamente en función del intervalo de fechas y del intervalo seleccionados.
* **[!UICONTROL Volver]**: el usuario estaba activo en el periodo actual y no en el periodo inmediatamente anterior, pero anteriormente estaba activo en algún momento. Consulte hasta dónde llega el análisis para determinar un usuario de retorno pasando el puntero sobre &#39;[!UICONTROL Devolver usuarios]&#39; en la leyenda del gráfico. El intervalo de retrospectiva se determina dinámicamente en función del intervalo de fechas y del intervalo seleccionados.
* **[!UICONTROL Inactivo]**: el usuario estuvo activo en el periodo inmediatamente anterior, pero no lo está en el periodo actual. Los usuarios inactivos no se contabilizan en el número total de usuarios activos.

>[!NOTE]
>
>Los usuarios repetidos no se tienen en cuenta en este cálculo, ya que no representan ninguna ganancia o pérdida de usuarios.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Evaluación del rendimiento**: le permite evaluar el rendimiento general del producto en términos de adquisición de nuevos usuarios. Al rastrear las tendencias de crecimiento, puede comprender mejor si su producto atrae y retiene a los usuarios a un ritmo deseado.
* **Análisis de adquisición de usuarios**: le permite evaluar la eficacia de sus estrategias de adquisición de usuarios. El análisis de las fuentes de crecimiento de los usuarios, como motores de búsqueda, campañas u otros canales de marketing, permite identificar las fuentes de crecimiento más significativas para poder asignar los recursos en consecuencia.
* **Análisis de pérdida**: El crecimiento neto incluye la desgaste en su fórmula (usuarios inactivos). Puede evaluar el estado general de su base de usuarios a lo largo del tiempo. Si el crecimiento neto es sistemáticamente inferior a `1`Además, indica una alta cantidad de desgaste que podría impulsar la implementación de estrategias de retención.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Eventos]**: el evento que desea medir. Dado que este tipo de vista se basa en el usuario, cualquier usuario que interactúe con el evento una vez dentro del periodo se contará como un usuario activo. Puede incluir un evento en una consulta.
* **[!UICONTROL People]**: El segmento que desea medir. Puede incluir un segmento en una consulta.

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener diferentes intervalos que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
