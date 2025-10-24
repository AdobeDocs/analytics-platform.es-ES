---
title: Configuración de componentes de atribución
description: Permite establecer la atribución predeterminada para una métrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 7d354ce65f72838c007d2b9faf02848d86fd7c0f
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 93%

---

# Configuración de componentes de atribución {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Atribución"
>abstract="Configure el modelo de atribución predeterminado aplicado a una métrica en los informes."

<!-- markdownlint-enable MD034 -->


La atribución le permite personalizar cómo los elementos de dimensión obtienen crédito por los eventos de éxito.

Por ejemplo:

1. Una persona que visita su sitio hace clic en un vínculo de búsqueda de pago a una de sus páginas de producto. Después, añade el producto al carro de compras, pero no lo compra.
2. Al día siguiente, ve una publicación en los medios sociales de uno de sus amigos. Hace clic en el vínculo y, a continuación, completa la compra.

En algunos informes, es posible que desee atribuir el pedido a la búsqueda de pago. En otros informes, es posible que desee atribuir el pedido a los medios sociales. La atribución permite controlar este aspecto del sistema de informes.

## Definición del modelo de atribución predeterminado de un componente

Puede establecer un modelo de atribución predeterminado para una métrica determinada actualizando la configuración de la métrica en la vista de datos. Al hacerlo, se anula el modelo de atribución de la métrica cada vez que se utiliza en Analysis Workspace.

>[!NOTE]
>
>Tenga en cuenta lo siguiente cuando habilite la atribución en una métrica:
>
>* **Al usar el componente en un informe con *una sola dimensión*:** la atribución del componente ignora el modelo de asignación cuando se usa un modelo de atribución no predeterminado.
>
>* **Al usar el componente en un informe con *varias dimensiones*:** la atribución del componente retiene el modelo de asignación cuando se usa un modelo de atribución no predeterminado.
>
>   Solo hay varias dimensiones disponibles cuando [se exportan datos a la nube](/help/analysis-workspace/export/export-cloud.md).
>
> Para obtener más información sobre la asignación, consulte [Configuración del componente de persistencia](/help/data-views/component-settings/persistence.md).

Para actualizar el modelo de atribución predeterminado de un componente:

1. Vaya a la vista de datos que contiene el componente cuyo modelo de atribución predeterminado desea actualizar.

1. Seleccione el componente y expanda la sección **[!UICONTROL Atribución]** a la derecha de la pantalla.

   ![Ventana de vistas de datos que resalta la opción Establecer atribución](../assets/attribution-settings.png)

1. Seleccione [!UICONTROL **Establecer atribución**] y, a continuación, seleccione la ventana [modelo de atribución](#attribution-models), [contenedor](#container) y [retrospectiva](#lookback-window).



1. Seleccione [!UICONTROL **Guardar y continuar**].

>[!TIP]
>
>Si su organización requiere que una métrica tenga varias configuraciones de atribución, puede realizar una de las siguientes acciones:
>
> * Copie la métrica en la vista de datos con cada configuración de atribución deseada. Puede incluir la misma métrica varias veces en una vista de datos, lo que otorga a cada métrica una configuración diferente. Asegúrese de etiquetar cada métrica de forma adecuada para que los analistas comprendan la diferencia entre estas métricas al generar informes.
>
> * Anule la métrica en Analysis Workspace. En [Configuración de columna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) de una métrica, seleccione **[!UICONTROL Usar modelo de atribución no predeterminado]** para cambiar el modelo de atribución y la ventana de retroactividad de la métrica para ese informe específico.

## Modelos de atribución {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="Modelo"
>abstract="Seleccione un modelo de atribución para la métrica."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}

## Contenedor

{{attribution-container}}

## Período de retroactividad

{{attribution-lookback-window}}

## Ejemplo

{{attribution-example}}
