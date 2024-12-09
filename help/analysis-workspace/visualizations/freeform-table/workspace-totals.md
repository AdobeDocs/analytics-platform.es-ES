---
description: Descubra cómo se calculan los totales de Workspace.
title: Totales de Workspace
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 18%

---

# Totales de Workspace {#workspace-totals}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_grandtotal"
>title="Total general"
>abstract="El total general no es compatible con tablas o desgloses con filas estáticas"

<!-- markdownlint-enable MD034 -->


En las tablas de forma libre, aparece una fila total en cada nivel de desglose y puede mostrar dos totales:

![Tabla de forma libre que resalta el total general y el total de tabla.](assets/total-row.png)

* **[!UICONTROL Total de tabla]** ➊: Este total suele ser igual o un subconjunto de [!UICONTROL Total general]. El total refleja cualquier filtro de tabla aplicado en la tabla de forma libre, incluida la opción [!UICONTROL Incluir ninguno].
* **[!UICONTROL Total general]** (**[!UICONTROL de]** *número*) ➋: este total representa todos los eventos que se han recopilado. Cuando se aplica un filtro en el nivel de panel o en la tabla de forma libre, este total se ajusta para reflejar todos los eventos que coinciden con los criterios de filtro.




## Mostrar totales

En ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Configuración de columna]**, hay opciones para **[!UICONTROL Mostrar totales]** y **[!UICONTROL Mostrar total general]**. Si esta configuración no está marcada, los totales se eliminan de la tabla, lo que puede ser útil en casos en los que los totales no tengan sentido.


Los totales de [Fila estática](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) se comportan de manera diferente y se controlan usando ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Configuración de fila]**.

| Opción | Descripción |
|---|---|
| **[!UICONTROL Mostrar la suma de las filas actuales como el total]** | Mostrar una suma del lado del cliente de las filas de la tabla. Este total **no** anula la duplicación de métricas como sesiones o personas. |
| **[!UICONTROL Mostrar total general]** | Mostrar una suma del lado del servidor. Este total anula la duplicación de métricas como sesiones o personas. |

Ver [elementos de dimensión dinámicos o estáticos en tablas improvisadas](column-row-settings/manual-vs-dynamic-rows.md).


## Preguntas frecuentes

| Preguntas | Respuesta |
|---|---|
| ¿En qué *total* se basan los porcentajes de la columna gris? | Este *total* depende de la selección de configuración de **[!UICONTROL Porcentajes]** en **[!UICONTROL Configuración de fila]**:<ul><li>Calcular porcentajes por columna: esta configuración es la predeterminada. Los porcentajes se basan en el total de la tabla.</li><li>Calcular porcentajes por fila: los porcentajes se basan en el total general.</li></ul> |
| ¿Cómo afecta la configuración **[!UICONTROL Incluir &quot;Sin valor&quot;]** a los totales? | Si la opción **[!UICONTROL Incluir &quot;Sin valor&quot;]** está desmarcada, la fila **[!UICONTROL Sin valor]** se quita de la tabla, el total de la tabla y se traslada a cualquier métrica calculada que use [*Total* tipos de métrica](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| Cuando se aplican filtros de tabla personalizados a una tabla de forma libre, ¿tienen en cuenta todas mis métricas calculadas y el formato condicional para el filtro? | Actualmente no. **[!UICONTROL Incluir &quot;Ningún valor&quot;]** se tiene en cuenta, pero los filtros de tabla personalizados no afectan a lo siguiente:<ul><li>El rango máximo/mínimo de columna que utiliza el formato condicional se ve en todos los datos.</li><li>Métricas calculadas que aprovechan **[!UICONTROL total general]** tipos de métricas.</li><li>Métricas calculadas con funciones que calculan en filas de una tabla de forma libre: Suma de columna, Máximo de columna, Mínimo de columna, Recuento, Media, Mediana, Percentil, Cuartil, Recuento de filas, Desviación estándar, Variación, Acumulativo, Promedio acumulado, Variantes de regresión, Puntuación T, Prueba T, Puntuación Z y Prueba Z.</li></ul> |
| En Métricas calculadas, ¿qué refleja el tipo de métrica **[!UICONTROL Total general]**? | **[!UICONTROL Total general]** sigue haciendo referencia a **[!UICONTROL Total general]** y no refleja los filtros aplicados a una tabla o al **[!UICONTROL Total de tabla]**. |
| ¿Qué total se muestra cuando los datos se copian y pegan desde una tabla de forma libre o se descargan mediante CSV? | La fila total refleja solamente el **[!UICONTROL total de la tabla]** y respeta la configuración de la columna **[!UICONTROL Mostrar totales]**. |
