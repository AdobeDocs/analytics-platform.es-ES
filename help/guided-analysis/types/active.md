---
title: Vista activa
description: Identifique quién es nuevo, retenido, que regresa o está inactivo.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Guided Analysis
keywords: análisis de productos
role: User
source-git-commit: 60f1c20b4188b5363619af49b85373d081db6cc3
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 1%

---

# [!UICONTROL Activo] vista

El **Activo** La vista de proporciona perspectivas sobre el crecimiento y la adquisición de usuarios durante un periodo específico. El eje horizontal es un intervalo de tiempo, mientras que el eje vertical es una medida de usuarios. Los usuarios se dividen en cuatro categorías:

* **[!UICONTROL Nuevo]**: el usuario estuvo activo durante el periodo actual, pero no anteriormente. Ver hasta dónde llega el análisis pasando el puntero sobre &#39;[!UICONTROL Nuevos usuarios]&#39; en la leyenda del gráfico. El intervalo de retrospectiva se determina dinámicamente en función del intervalo de fechas y del intervalo seleccionados.
* **[!UICONTROL Repetir]**: el usuario estaba activo en el periodo actual y en el anterior.
* **[!UICONTROL Volver]**: el usuario estaba activo en el periodo actual y no en el periodo inmediatamente anterior, pero anteriormente estaba activo en algún momento. Ver hasta dónde llega el análisis pasando el puntero sobre &#39;[!UICONTROL Devolver usuarios]&#39; en la leyenda del gráfico. El intervalo de retrospectiva se determina dinámicamente en función del intervalo de fechas y del intervalo seleccionados.
* **[!UICONTROL Inactivo]**: el usuario estuvo activo en el periodo inmediatamente anterior, pero no lo está en el periodo actual. Los usuarios inactivos no se contabilizan en el número total de usuarios activos.

Todos los usuarios activos (nuevos + repetidos + devueltos) aparecen como un tono de verde azulado encima del eje horizontal, mientras que todos los usuarios inactivos aparecen en naranja debajo del eje horizontal.

>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Retención y pérdida de usuarios:** Proporciona una visualización clara de los períodos de retención de usuarios alta o baja. Reconocer estos períodos de retención alta o baja puede ayudarle a tomar decisiones sobre productos para fomentar una retención alta o ayudar a minimizar la pérdida.
* **Evaluación de campaña**: Ver una campaña específica puede ayudarle a comprender cuánto tráfico generó y en qué medida ayudó a los usuarios a seguir participando.
* **Análisis del ciclo vital de usuario**: El análisis del crecimiento activo del usuario a lo largo del ciclo vital de este puede ayudar a identificar fases específicas en las que disminuye la participación del usuario. Por ejemplo, si hay una alta proporción de usuarios latentes para personas en una fase de incorporación, puede indicar problemas de uso o la necesidad de mejorar la orientación interna del producto.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Ver]**: cambie entre este tipo de vista y [Crecimiento neto](net-growth.md).
* **[!UICONTROL Eventos]**: el evento que desea medir. Dado que este tipo de vista se basa en el usuario, cualquier usuario que interactúe con el evento una vez dentro del periodo se contará como un usuario activo. Puede incluir un evento en una consulta.
* **[!UICONTROL Contabilizado como]**: La métrica que desea medir. Las opciones incluyen [!UICONTROL Cantidad de usuarios] y [!UICONTROL Porcentaje de usuarios].
* **[!UICONTROL Segmentos]**: Segmento por el que desea filtrar los datos. Puede incluir un segmento en una consulta.

## Ajustes del gráfico

El [!UICONTROL Activo] La vista ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: el tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Barra apilada] y [!UICONTROL Área apilada].

## Comparación del tiempo

{{apply-time-comparison}}

![Comparación del tiempo activo](../assets/active-compare.png)

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener diferentes intervalos que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
