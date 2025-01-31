---
description: Aprenda a editar la configuración de columna para configurar el formato de columna, aunque algunas opciones de formato pueden ser condicionales.
title: Configuración de columna
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 21%

---

# [!UICONTROL Configuración de columna]

[!UICONTROL Configuración de columna] le permite configurar el formato de columna, aunque algunas opciones de formato pueden ser condicionales.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuración de fila y columna en una tabla de forma libre](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]


Para obtener acceso a [!UICONTROL Configuración de columna], seleccione ![Configuración de columna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) en el encabezado de la columna.

![Configuración de columna](assets/column-settings.png)


Puede editar la configuración de varias columnas a la vez. Seleccione varias columnas y seleccione ![Setting](/help/assets/icons/Setting.svg) en cualquiera de las columnas seleccionadas. Cualquier cambio que realice se aplicará a todas las columnas que tengan celdas seleccionadas.

| Opción | Descripción |
| --- | --- |
| **[!UICONTROL Mostrar total]** | Mostrar una suma de la columna del lado del cliente. Este total **no** anula la duplicación de métricas como sesiones o personas. |
| **[!UICONTROL Mostrar total general]** | Mostrar una suma de la columna del lado del servidor. El total general anula la duplicación de métricas como sesiones o personas. |
| **[!UICONTROL Mostrar minigráfico]** | Mostrar un gráfico de líneas en el encabezado de la columna. |
| **[!UICONTROL Número]** | Determine si una celda muestra u oculta el valor numérico de la métrica. Por ejemplo, si la métrica es Visualizaciones de la página, el valor numérico es el número de visualizaciones de la página para el elemento de fila. |
| **[!UICONTROL Porcentaje]** | Determine si una celda muestra u oculta el valor porcentual de la métrica. Por ejemplo, si la métrica es Vistas de página, el valor porcentual es el número de vistas de página para el elemento de fila, dividido por el total de vistas de página para la columna.  Nota: Es posible garantizar que los porcentajes superiores al 100 % sean precisos. El límite superior puede moverse al 1000 % para evitar que el ancho de las columnas sea demasiado grande. |
| **[!UICONTROL Mostrar anomalías]** | Determine si la detección de anomalías se ejecuta en los valores de esta columna. |
| **[!UICONTROL Mostrar previsión]** | Determine si los valores de previsión se muestran en esta columna. |
| **[!UICONTROL Justificar el texto del encabezado]** | Ajuste el texto del encabezado en las tablas improvisadas para que los encabezados sean más legibles y las tablas se puedan compartir con mayor facilidad. El ajuste es útil para el procesamiento de PDF y para las métricas con nombres largos. Está activada de forma predeterminada. |
| **[!UICONTROL La interpretación de cero no tiene valor]** | Determine, para las celdas con un valor 0, si desea mostrar un 0 o una celda en blanco. Esta interpretación es útil cuando se ven los datos de cada día de un mes y algunos días están en el futuro.  En lugar de mostrar 0 para las fechas futuras, se muestran celdas en blanco. Los gráficos también respetan esta configuración (es decir, los gráficos no muestran una línea o barra con valores 0). |
| **[!UICONTROL Contexto]** | Determine si una celda muestra u oculta todo el formato de la celda, incluidos el gráfico de barras y el formato condicional. |
| **[!UICONTROL Gráfico de barras]** | Muestra un gráfico de barras horizontal que representa el valor de la celda en relación con el total de la columna. |
| **[!UICONTROL Formato condicional]** | Utilice un formato condicional. Consulte la [sección](#conditional-formatting) a continuación. |
| **[!UICONTROL Vista previa de celdas de tabla]** | Vista previa de cómo aparece cada celda con las opciones de formato seleccionadas actualmente aplicadas. |
| **[!UICONTROL Uso de modelos de atribución no predeterminados]** | Utilice un modelo de atribución no predeterminado. Consulte la [sección](#use-non-default-attribution-model) a continuación. |

## Formato condicional {#conditional-formatting}

El formato condicional aplica formato que puede definir a los límites superior, medio e inferior. La aplicación de formato condicional en tablas improvisadas también está habilitada automáticamente en los desgloses, a menos que los límites [!UICONTROL Personalizados] estén seleccionados.

![Formato condicional](./assets/conditional-formatting.png)

| Opciones de formato condicional | Descripción |
| --- | --- |
| **[!UICONTROL límites porcentuales de uso]** | Cambie el rango de límite en función de los porcentajes, no en función de los valores absolutos. El rango de límite de porcentaje funciona para métricas que solo están basadas en porcentajes (como la Tasa de salida hacia otro sitio) y para métricas que tienen un recuento y un porcentaje (como las Vistas de la página). |
| **[!UICONTROL Generado automáticamente]** | Calcule automáticamente los límites superior/medio/inferior en función de los datos. El límite superior es el valor máximo de esta columna. El límite inferior es el valor más bajo y el punto medio es la media entre los límites superior e inferior. |
| **[!UICONTROL Personalizado]** | Asigne manualmente **[!UICONTROL límite superior]**, **[!UICONTROL punto medio]** y **[!UICONTROL límite inferior]**. Los límites proporcionan la flexibilidad para determinar si el valor de una columna es bueno, medio o malo. |
| **[!UICONTROL Paleta de formato condicional]** | Aplique un conjunto de colores preconfigurado a las celdas. En función de cuál de los cuatro esquemas de color disponibles seleccione, se asignan distintos colores a valores altos, valores medios y valores bajos. <br> Sustituir una dimensión en la tabla restablece los límites de formato condicional. Cuando se sustituye una métrica se vuelven a calcular los límites de dicha columna (donde las métricas se encuentran en el eje X y las dimensiones se encuentran en el eje Y). |

## Uso de modelos de atribución no predeterminados {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel"
>title="Uso de modelos de atribución no predeterminados"
>abstract="Habilite un modelo de atribución no predeterminado para las columnas seleccionadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel_disabled"
>title="Uso de modelos de atribución no predeterminados"
>abstract="El modo de atribución no predeterminado no está disponible para esta métrica."

<!-- markdownlint-enable MD034 -->



Puede anular el modelo de atribución predeterminado configurado en [Vistas de datos](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Tenga en cuenta lo siguiente al actualizar la atribución de un componente a un modelo de atribución no predeterminado:
>
>* **Al usar el componente en un informe con *una sola dimensión*:** La atribución del componente ignora el modelo de asignación cuando se usa un modelo de atribución no predeterminado.
>
>* **Al usar el componente en un informe con *varias dimensiones*:** La atribución del componente retiene el modelo de asignación cuando se usa un modelo de atribución no predeterminado.
>
>   Solo hay varias dimensiones disponibles cuando [se exportan datos a la nube](/help/analysis-workspace/export/export-cloud.md).
>
> Para obtener más información acerca de la asignación, vea [Configuración del componente de persistencia](/help/data-views/component-settings/persistence.md).

Para utilizar un modelo de atribución no predeterminado para una métrica en una Analysis Workspace:

1. Seleccione **[!UICONTROL Usar modelo de atribución no predeterminado]**. Cuando ya esté seleccionado, use **[!UICONTROL Editar]** para editar el modelo de atribución. O bien, anule la selección para volver al modelo de atribución predeterminado.

   ![Las opciones de Configuración de columna que resaltan la opción Configuración de datos: utilice un modo de atribución no predeterminado.](assets/attribution-checkbox.png)

2. En **[!UICONTROL Modelo de atribución de columna]**, seleccione un **[!UICONTROL Modelo]** y una **[!UICONTROL ventana retrospectiva]**. La ventana retrospectiva determina la ventana de atribución de datos que se aplica a cada conversión.

   ![Las opciones del modelo de atribución de columnas que muestran Lineal seleccionado.](assets/attribution-select.png)


### Modelos de atribución

{{attribution-models-details}}

### Ventana retroactiva

{{attribution-lookback-window}}



>[!MORELIKETHIS]
>
>* [Administración de fuentes de datos](/help/analysis-workspace/visualizations/t-sync-visualization.md)
