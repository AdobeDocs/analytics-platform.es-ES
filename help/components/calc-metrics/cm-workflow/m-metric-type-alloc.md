---
description: Obtenga información sobre el tipo de métrica y la atribución
title: Tipo de métrica y atribución
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 304b8d85767d89ee60a6fb37a128194f60ca89d4
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 91%

---

# Tipo de métrica y atribución

Puede configurar el tipo de métrica y [modelo de atribución](#attribution-models) para una métrica en una definición de métrica calculada.

1. Seleccione ![Configuración](/help/assets/icons/Setting.svg) en el componente de la métrica.
1. En el cuadro de diálogo emergente:

   ![Tipo de métrica y atribución](assets/cm-type-alloc.png)

   * Especifique el **[!UICONTROL Tipo de métrica]**:

     | Tipo de métrica | Definición |
     |---|---|
     | **[!UICONTROL Estándar]** | Si una fórmula consiste en una única métrica estándar, muestra datos idénticos a su métrica no calculada homóloga. Las métricas estándar son útiles para crear métricas calculadas específicas de cada elemento de línea individual.  <p>Por ejemplo, ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Pedidos]** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sesiones]** toma los pedidos de ese elemento de línea específico y lo divide por el número de sesiones de ese elemento de línea específico. |
     | **[!UICONTROL Total general]** | Utilice **[!UICONTROL Total general]** para obtener el período de creación de informes en cada elemento de línea. Si una fórmula consiste en una única métrica total, muestra el mismo número total en cada elemento de línea. Las métricas de total general son útiles cuando desea crear métricas calculadas que se comparen con los datos totales. <p>Por ejemplo, ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Pedidos]** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sesiones totales]** muestra la proporción de pedidos en todas las sesiones, no solo las sesiones en el elemento de línea específico. En este ejemplo, especifique **[!UICONTROL Total general]** para la métrica ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sesiones]** en la métrica calculada, lo que la convertirá automáticamente en ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sesiones totales]**. |

   * Especifique **[!UICONTROL Atribución]**.

      1. Puede realizar lo siguiente:

         * Deshabilitar **[!UICONTROL Uso de modelos de atribución no predeterminados]** para usar el modelo de atribución de columna predeterminado, que es Último toque, con una ventana de retroactividad de 30 días.
         * Habilitar **[!UICONTROL Uso de modelos de atribución no predeterminados]**. En el cuadro de diálogo **[!UICONTROL Modelo de atribución de columna]**:

            * Seleccione un **[!UICONTROL Modelo]** de los [modelos de atribución](#attribution-models).
            * Seleccione un **[!UICONTROL contenedor]** de las opciones de [contenedor](#container).
            * Seleccione una **[!UICONTROL ventana retrospectiva]** de las opciones de la [ventana retrospectiva](#lookback-window). Si selecciona **[!UICONTROL Tiempo personalizado]**, puede definir el período de tiempo en **[!UICONTROL Minuto(s)]** hasta **[!UICONTROL Trimestre(s)]**.

      1. Seleccione **[!UICONTROL Aplicar]** para aplicar el modelo de atribución no predeterminado. Seleccione Cancelar para cancelar.

     Si ya ha definido un modelo de atribución no predeterminado, seleccione **[!UICONTROL Editar]** para modificar la selección.

Vea [Ejemplo](#example) para ver un ejemplo del uso de un modelo de atribución, un contenedor y una ventana retrospectiva.


## Modelos de atribución {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Uso de modelos de atribución no predeterminados"
>abstract="Habilite un modelo de atribución no predeterminado para la métrica seleccionada."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modelo"
>abstract="Seleccione un modelo de atribución para la métrica."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Último contacto"
>abstract="El 100 % del crédito se destina al último valor de dimensión visto por un visitante."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Primer contacto"
>abstract="El 100 % del crédito se destina al primer valor de dimensión visto por un visitante."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Lineal"
>abstract="El crédito se distribuye de manera uniforme en todos los valores de dimensión."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Participación"
>abstract="100 % de crédito a cada valor de dimensión visto por un visitante.<br/>Los totales de columna están sobreestimados."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Mismo contacto"
>abstract="El crédito se otorga solo a los valores de dimensión que se producen en el mismo evento que la conversión."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Mismo contacto"
>abstract="El crédito se otorga solo a los valores de dimensión que se producen en el mismo evento que la conversión."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="Forma de U"
>abstract="40 % de crédito al primer valor de dimensión, 40 % al último, 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Curva J"
>abstract="60 % de crédito al último valor de dimensión, 20 % al primero y 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="Curva J"
>abstract="60 % de crédito al último valor de dimensión, 20 % al primero y 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J inversa"
>abstract="60 % de crédito al primer valor de dimensión, 20 % al último, 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="J inversa"
>abstract="60 % de crédito al primer valor de dimensión, 20 % al último, 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Deterioro de tiempo"
>abstract="Los valores de dimensión más cercanos en el tiempo a una conversión obtienen la mayor cantidad de crédito."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personalizado"
>abstract="Defina su propia ponderación de atribución basada en la posición."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personalizado"
>abstract="Defina su propia ponderación de atribución basada en la posición."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorítmico"
>abstract="El crédito se determina de forma dinámica mediante un algoritmo estadístico."

{{attribution-models-details}}


## Contenedor {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Contenedor"
>abstract="Seleccione un contenedor para establecer el ámbito deseado para la atribución."

{{attribution-container}}


## Ventana de retroactividad {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Ventana de retroactividad"
>abstract="Este ajuste determina la ventana de atribución de datos que se aplicará a cada conversión."

{{attribution-lookback-window}}




## Ejemplo

{{attribution-example}}

>[!MORELIKETHIS]
>
>[Configuración de componentes de atribución](/help/data-views/component-settings/attribution.md)
>&#x200B;>[Métrica de participación](participation-metric.md)
>

