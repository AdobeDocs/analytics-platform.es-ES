---
description: Utilice las visualizaciones Número de resumen y Cambio de resumen para mostrar puntos de datos importantes en un proyecto.
title: Número de resumen y cambio de resumen
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 51%

---

# Número de resumen y Cambio de resumen

## Número de resumen {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Número de resumen"
>abstract="Cree una visualización que muestre los totales y subtotales."

<!-- markdownlint-enable MD034 -->

Utilice la visualización ![Resumir](/help/assets/icons/123.svg) **[!UICONTROL Número de resumen]** para resaltar un número elevado que sea importante en un proyecto. Esta visualización se comporta de las siguientes maneras, utilizando la fuente de datos asociada:

* Selecciona el total de la columna en caso de que no se haya seleccionado ninguna celda.
* Si se selecciona una única celda, se muestra el resumen de esta.
* Si se selecciona más de una celda, se muestra la primera celda seleccionada.
* Si se selecciona la columna, se usa el valor de la primera celda de la columna.

![Visualización del número de resumen](asses/../assets/summary-number.png)

Como parte de la configuración de visualización, hay disponibles opciones específicas de Número de resumen.

| Opción | Definición |
|--- |--- |
| **[!UICONTROL Valor abreviado]** | Seleccione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente el valor numérico. Cuando esté seleccionada, introduzca un número para definir la cantidad de abreviaturas. Por ejemplo:<br/><table><tr><td>**Valor original**</td><td>**Valor de abreviatura**</td><td>**Resultado**</td></tr><tr><td>12.011.141,25 $</td><td>No seleccionado</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Seleccionado, establecido en `0`</td><td align="right">$12 MILLONES</td></tr><tr><td>12.011.141,25 $</td><td> Seleccionado, establecido en `1`</td><td  align="right">12 MILLONES DE DÓLARES</td></tr><tr><td>12.011.141,25 $</td><td>Seleccionado, establecido en `2`</td><td align="right">12,01 MILLONES DE USD</td></tr><tr><td>12.011.141,25 $</td><td>Seleccionado, establecido en `3`</td><td align="right">$12.011 MILLONES</td></tr></table> |
| **[!UICONTROL Valor de resumen por]** | Elija mostrar el máximo, el mínimo, la media, la mediana o la suma para una selección de datos. |

## Cambio de resumen {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Cambio de resumen"
>abstract="Cree una visualización que muestre el delta (cambio) entre dos números"

<!-- markdownlint-enable MD034 -->


Use la visualización ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Cambio de resumen]** para mostrar el delta (cambio) entre dos números. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

Esta visualización se comporta de las siguientes maneras:

* Si no se selecciona ninguna celda, compara los valores de las dos primeras celdas de la columna.
* Si se selecciona una celda, muestra 0, ya que compara el valor de celda con ella misma.
* Si se seleccionan dos celdas, la primera celda seleccionada se toma como numerador y la segunda como denominador.
* Si se seleccionan más de dos celdas, solo se tienen en cuenta las dos primeras para la comparación.
* Si se selecciona un intervalo de celdas, se compara la primera celda con la última seleccionada en el intervalo.
* Si se selecciona la columna, se compara el primer valor consigo mismo, lo que da como resultado un cambio de 0.


![Visualización de cambio de resumen que muestra el delta entre dos números.s](assets/summary-change.png)


Como parte de la configuración de visualización, hay **[!UICONTROL opciones de cambio de resumen]** específicas disponibles.

| Opción | Definición |
|--- |--- |
| **[!UICONTROL Mostrar cambio porcentual]** | Mostrar el cambio porcentual entre los 2 números. |
| **[!UICONTROL Mostrar diferencia en bruto]** | Muestra la diferencia en bruto entre los 2 números. También puede abreviar valores y mostrar hasta 3 decimales con esta opción. |
| **[!UICONTROL Valor abreviado]** | Seleccione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente el valor cambiado. Cuando esté seleccionada, introduzca un número para definir la cantidad de abreviaturas. Por ejemplo:<br/><table><tr><td>**Valor original**</td><td>**Valor de abreviatura**</td><td>**Resultado**</td></tr><tr><td>12.011.141,25 $</td><td>No seleccionado</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Seleccionado, establecido en `0`</td><td align="right">$12 MILLONES</td></tr><tr><td>12.011.141,25 $</td><td> Seleccionado, establecido en `1`</td><td  align="right">12 MILLONES DE DÓLARES</td></tr><tr><td>12.011.141,25 $</td><td>Seleccionado, establecido en `2`</td><td align="right">12,01 MILLONES DE USD</td></tr><tr><td>12.011.141,25 $</td><td>Seleccionado, establecido en `3`</td><td align="right">$12.011 MILLONES</td></tr></table> |

>[!MORELIKETHIS]
>
>[Agregar una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configuración de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menú contextual de visualización ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
