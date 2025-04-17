---
description: Descubra cómo se calculan los totales de Workspace.
title: Totales de Workspace
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 78%

---

# Totales de Workspace {#workspace-totals}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Total general"
>abstract="El total general no es compatible con tablas o desgloses con filas estáticas"

<!-- markdownlint-enable MD034 -->


En las tablas de forma libre, aparece una fila total en cada nivel de desglose y puede mostrar dos totales:

![Tabla de forma libre que resalta el total general y el total de la tabla.](assets/total-row.png)

* **[!UICONTROL Total de tabla]** ➊: este total suele ser igual o un subconjunto del [!UICONTROL total general]. El total refleja cualquier segmento de tabla aplicado en la tabla de forma libre, incluida la opción [!UICONTROL Incluir ninguno].
* **[!UICONTROL Total general]** (**[!UICONTROL de]** *número*) ➋: este total representa todos los eventos que se han recopilado. Cuando se aplica un segmento en el nivel de panel o en la tabla de forma libre, este total se ajusta para reflejar todos los eventos que coinciden con los criterios del segmento.




## Mostrar totales

En ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Configuración de columna]** hay opciones para **[!UICONTROL Mostrar totales]** y **[!UICONTROL Mostrar total general]**. Si esta configuración no está activada, los totales se eliminarán de la tabla, lo que puede ser útil en los casos en los que los totales no tengan sentido.


Los totales de [Filas estáticas](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) se comportan de forma diferente y se controlan mediante ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Configuración de la fila]**.

| Opción | Descripción |
|---|---|
| **[!UICONTROL Mostrar la suma de las filas actuales como el total]** | Muestra una suma del lado del cliente de las filas de la tabla. Este total **no** anula la duplicación de métricas como sesiones o personas. |
| **[!UICONTROL Mostrar el total general]** | Mostrar una suma del lado del servidor. Este total anula la duplicación de métricas como sesiones o personas. |

Consulte [Elementos de dimensión dinámicos o estáticos en tablas de forma libre](column-row-settings/manual-vs-dynamic-rows.md).


## Preguntas frecuentes

| Preguntas | Respuesta |
|---|---|
| ¿En qué *total* se basan los porcentajes de la columna gris? | Este *total* depende de la selección de la configuración **[!UICONTROL Porcentajes]** en **[!UICONTROL Configuración de la fila]**:<ul><li>Calcular porcentajes por columna: esta configuración es la predeterminada. Los porcentajes se basan en el total de la tabla.</li><li>Calcular porcentajes por fila: los porcentajes se basan en el total general.</li></ul> |
| ¿Cómo afecta la configuración **[!UICONTROL Incluir &quot;Sin valor&quot;]** a los totales? | Si la opción **[!UICONTROL Incluir &quot;Sin valor&quot;]** está desactivada, la fila **[!UICONTROL Sin valor]** se quitará de la tabla, el Total de la tabla y se trasladará a cualquier métrica calculada que utilice los tipos de métrica [*Total*](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| Cuando se aplican segmentos de tabla personalizados a una tabla de forma libre, ¿tienen en cuenta todas mis métricas calculadas y el formato condicional para el segmento? | Actualmente no. **[!UICONTROL Incluir &quot;Ningún valor&quot;]** se tiene en cuenta, pero los segmentos de tabla personalizados no afectan a lo siguiente:<ul><li>El rango máximo/mínimo de columna que utiliza el formato condicional abarca todos los datos.</li><li>Las métricas calculadas que aprovechan los tipos de métricas **[!UICONTROL Total general]**.</li><li>Las métricas calculadas con funciones que se calculan en las filas de una tabla de forma libre, por ejemplo: Suma de la columna, Máximo de columna, Mínimo de columna, Recuento, Media, Mediana, Percentil, Cuartil, Recuento de filas, Desviación estándar, Variación, Acumulativo, Promedio acumulado, Variantes de regresión, Puntuación T, Prueba T, Puntuación Z, Prueba Z.</li></ul> |
| En Métricas calculadas, ¿qué refleja el tipo de métrica **[!UICONTROL Total general]**? | **[!UICONTROL Total general]** sigue haciendo referencia a **[!UICONTROL Total general]** y no refleja segmentos aplicados a una tabla o al **[!UICONTROL Total de tabla]**. |
| ¿Qué total se muestra cuando los datos se copian y pegan desde una tabla de forma libre o se descargan mediante CSV? | La fila total reflejará únicamente el **[!UICONTROL Total de la tabla]** y respeta la configuración de la columna **[!UICONTROL Mostrar totales]**. |
