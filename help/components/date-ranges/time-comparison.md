---
description: La comparación de fechas de Analysis Workspace le permite tomar cualquier columna que contenga un intervalo de fechas y crear una comparación de fechas comunes, por ejemplo, año tras año, trimestre tras trimestre, mes tras mes, etc.
title: Comparación de fechas
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
source-git-commit: b196b8c05ba05a3f46d71c10fdcaa2ad8ef0dcd6
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 56%

---

# Comparación de fechas

La comparación de fechas de Analysis Workspace le permite tomar cualquier columna que contenga un intervalo de fechas y crear una comparación de fechas comunes, por ejemplo, año tras año, trimestre tras trimestre, mes tras mes, etc.

## Comparar periodos de tiempo

El análisis requiere contexto, y este lo proporciona a menudo un periodo de tiempo previo. Por ejemplo, la pregunta “¿En qué medida nos va mejor/peor que en este mismo momento del año pasado?” es fundamental para comprender su negocio. Las comparaciones de fechas incluyen automáticamente una columna “diferencia” que muestra el porcentaje de cambio en comparación con un periodo de tiempo concreto.

1. Cree una tabla de forma libre con cualquier dimensión y métrica que quiera comprobar a lo largo de un periodo de tiempo.
1. Haga clic con el botón derecho en una fila de la tabla y seleccione **[!UICONTROL Comparar periodos de tiempo]**.

   ![Fila de tabla con periodos de tiempo de comparación seleccionados](assets/compare-time.png)

   >[!NOTE]
   >
   >Esta opción del botón secundario está deshabilitada para filas de métricas, filas de intervalos de fechas y filas de dimensiones de tiempo.

1. Dependiendo de cómo haya establecido el intervalo de fechas de la tabla, dispone de estas opciones para la comparación:

   | Opción | Descripción |
   |---|---|
   | **[!UICONTROL Semana/mes/trimestre/año anterior a este intervalo de fechas]** | Compara la semana/mes/etc. inmediatamente anterior a este intervalo de fechas. |
   | **[!UICONTROL Esta semana/mes/trimestre/año del año pasado hasta este intervalo de fechas]** | Lo compara con el mismo intervalo de fechas hace un año. |
   | **[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]** | Le permite seleccionar un intervalo de fechas personalizado. |

   >[!NOTE]
   >
   >Al seleccionar una cantidad personalizada de días, por ejemplo, del 7 de octubre al 20 de octubre (un intervalo de 14 días), solo obtendrá dos opciones: **[!UICONTROL 14 días anteriores a este intervalo de fechas]** e **[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]**.

1. La comparación resultante tiene este aspecto:

   ![Tabla de forma libre que muestra una comparación de intervalos de fechas y un cambio porcentual.](assets/compare-time-result.png)

   Las filas en la columna Cambio porcentual aparecen en rojo para los valores negativos y en verde para los positivos.

1. (Opcional) Como en cualquier otro proyecto de Workspace, puede crear visualizaciones basadas en estas comparaciones de tiempo. Por ejemplo, aquí tiene un gráfico de barras:

   ![Gráfico de barras del proyecto Workspace.](assets/compare-time-barchart.png)

   Fíjese en que, para mostrar el cambio porcentual en el gráfico de barras, debe tener marcado el ajuste [!UICONTROL Porcentajes] en la [!UICONTROL Configuración de visualización].

## Agregar una columna Periodo de tiempo para comparar

Ahora puede agregar un periodo de tiempo a cada columna en una tabla, lo que permite agregar un periodo diferente al periodo en que está establecido el calendario. Esta es otra manera de comparar fechas.

1. Haga clic con el botón derecho en una columna de la tabla y seleccione **[!UICONTROL Agregar columna de período de tiempo]**.

   ![](assets/add-time-period-column.png)

1. Dependiendo de cómo haya establecido el intervalo de fechas de la tabla, dispone de estas opciones para la comparación:

   | Opción | Descripción |
   |---|---|
   | **[!UICONTROL Semana/mes/trimestre/año anterior a este intervalo de fechas]** | Agrega una columna con la semana/mes/etc. inmediatamente anterior a este intervalo de fechas. |
   | **[!UICONTROL Esta semana/mes/trimestre/año del año pasado hasta este intervalo de fechas]** | Agrega el mismo intervalo de fechas hace un año. |
   | **[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]** | Le permite seleccionar un intervalo de fechas personalizado. |

   >[!NOTE]
   >
   >Al seleccionar una cantidad personalizada de días, por ejemplo, del 7 de octubre al 20 de octubre (un intervalo de 14 días), solo obtendrá dos opciones: **[!UICONTROL 14 días anteriores a este intervalo de fechas]** e **[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]**.

1. El periodo de tiempo se insertará en la parte superior de la columna seleccionada:

   ![Tabla de forma libre que muestra ocurrencias para el período de calendario actual y el mes anterior.](assets/add-time-period-column2.png)

1. Puede agregar todas las columnas de tiempo que desee, así como combinar a voluntad distintos intervalos de fechas:

   ![Tabla de forma libre que muestra las ocurrencias de este mes, mes anterior, mes anterior hace un año y una semana del mes anterior hace un año.](assets/add-time-period-column4.png)

1. Además, puede ordenar en función de cualquier columna, lo que cambiará el orden de los días, dependiendo de la columna elegida.

## Alinear fechas de columnas para que comiencen en la misma fila {#section_5085E200082048CB899C3F355062A733}

Puede alinear las fechas de cada columna con todas a partir de la misma fila.

Por ejemplo, cuando alinea las fechas, si realiza una comparación mes a mes entre octubre y septiembre de 2016, la columna de la izquierda comenzará el 1 de octubre y la de la derecha, el 1 de septiembre:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Tenga en cuenta lo siguiente al utilizar esta opción:
>
>* Esta configuración está habilitada de forma predeterminada para todos los proyectos nuevos.
>
>* Esta configuración se aplica a toda la tabla. Por ejemplo, si cambia esta configuración para un desglose dentro de la tabla, cambiará la configuración de toda la tabla.
>

Para habilitar esta configuración, si aún no está habilitada:

1. En la tabla en la que desee alinear las fechas de la columna, seleccione el icono **Configuración** en el encabezado de la tabla.

1. En la ficha [!UICONTROL **Configuración**], seleccione **[!UICONTROL Alinear fechas de cada columna para que todas empiecen en la misma fila (se aplica a toda la tabla)]**.

![](assets/date-comparison-setting.png)
