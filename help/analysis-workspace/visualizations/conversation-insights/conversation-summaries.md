---
description: Utilice la visualización de resúmenes de conversación para resumir las conversaciones.
title: Resúmenes de conversación
feature: Visualizations
role: User
hide: true
source-git-commit: 2cca5dfaec6be8f22308e09a023e9e57bec387b7
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 10%
---
# Resúmenes de conversación {#conversation-summaries}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_button"
>title="Resúmenes de conversación"
>abstract="Cree una visualización que resuma un grupo filtrado de conversaciones."

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_panel"
>title="Resúmenes de conversación"
>abstract="Resuma un grupo filtrado de conversaciones. Controle la longitud del resumen. Consulte las citas representativas de los clientes para validar la precisión de las señales extraídas. Seleccione una cita para abrir la reproducción completa de la conversación."


La visualización ![Resumir](/help/assets/icons/Summarize.svg) **[!UICONTROL Resúmenes de conversación]** permite resumir un grupo filtrado de conversaciones.

La visualización muestra un resumen de la métrica seleccionada (por ejemplo, Conversaciones) y subtemas o comentarios literales cuando se ha configurado la visualización para incluir subtemas.


## Crear y configurar {#conversation-summaries-create-configure}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_usenondefaultattributionmodel"
>title="Uso de modelos de atribución no predeterminados"
>abstract="Habilite un modelo de atribución no predeterminado para esta métrica."

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_usenondefaultattributionmodel_disabled"
>title="Uso de modelos de atribución no predeterminados"
>abstract="Los modelos de atribución no predeterminados no están disponibles para esta métrica."

Para crear y configurar una visualización de **[!UICONTROL resúmenes de conversación]**:

1. Agregar una visualización de ![Resumen](/help/assets/icons/Summarize.svg) **[!UICONTROL resúmenes de conversación]**. Consulte [Añadir una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. En la configuración de visualización **[!UICONTROL Resúmenes de conversación]**:

   1. Seleccione una **[!UICONTROL métrica]**. Por ejemplo: **[!UICONTROL conversaciones]**.
   1. De forma opcional, si desea usar un modelo [attribution](/help/analysis-workspace/attribution/models.md) no predeterminado en la métrica, seleccione **[!UICONTROL Usar modelo de atribución no predeterminado]** y seleccione **[!UICONTROL Modelo]**, **[!UICONTROL Contenedor]** y **[!UICONTROL Ventana retrospectiva]**.
   1. Opcionalmente, puede aplicar un segmento a la visualización. Seleccione un segmento del menú desplegable **[!UICONTROL Segmentos]**.

1. Seleccione **[!UICONTROL Build]** para generar la visualización. Seleccione **[!UICONTROL Restablecer]** para restablecer los valores predeterminados de configuración. Seleccione **[!UICONTROL Cancelar]** para cancelar la configuración.

Para reconfigurar la visualización de **[!UICONTROL resúmenes de conversación]**, seleccione ![Editar](/help/assets/icons/Edit.svg) junto a **[!UICONTROL Métrica: _métrica_]**o **[!UICONTROL Métrica:_métrica_]** | **[!UICONTROL Segmentos: _segmentos_]**.

## Utiliza

Para utilizar la visualización:

>[!BEGINTABS]

>[!TAB Subtemas]

![Subtemas](assets/conversation-summaries-subtopics.png)

>[!TAB Comentarios textuales]

![Comentarios textuales](assets/conversation-summaries-verbatimcomments.png)

>[!ENDTABS]

* Si ha [incluido subtemas](#settings), seleccione **[!UICONTROL Subtemas]** para mostrar subtemas o **[!UICONTROL comentarios literales]** para mostrar comentarios literales.
* Cuando haya seleccionado **[!UICONTROL Comentarios textuales]**, seleccione ![BúsquedaDeArchivos](/help/assets/icons/FileSearch.svg) para abrir una nueva visualización de [**[!UICONTROL Revisión de la conversación]**](./conversation-review.md) para la conversación específica de la que forma parte el comentario textual.

## Configuración

Están disponibles las siguientes [configuraciones de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) específicas.

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Longitud del resumen]** | Especifique la longitud del resumen. Puede seleccionar entre **[!UICONTROL Short]** o **[!UICONTROL Long]**. |
| **[!UICONTROL Incluir subtemas]** | Seleccione **[!UICONTROL Incluir subtemas]** para mostrar los subtemas en la visualización. Use **[!UICONTROL Número máximo de subtemas]** para configurar el número máximo de subtemas que se mostrarán. |
