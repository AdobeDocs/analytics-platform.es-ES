---
title: Configuración de componentes de atribución
description: Permite establecer la atribución predeterminada para una métrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 29%

---

# Configuración de componentes de atribución {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_attribution"
>title="Atribución"
>abstract="Configure el modelo de atribución predeterminado aplicado a una métrica en los informes."

<!-- markdownlint-enable MD034 -->


La atribución permite personalizar la forma en que los elementos de dimensión obtienen crédito por los eventos de éxito.

![Ventana de vistas de datos que resalta la opción Establecer atribución](../assets/attribution-settings.png)

Por ejemplo:

1. Una persona del sitio hace clic en un vínculo de búsqueda de pago a una de las páginas del producto. Agregan el producto al carro de compras, pero no lo compran.
2. Al día siguiente, ven una publicación en los medios sociales de uno de sus amigos. Hace clic en el vínculo y, a continuación, completa la compra.

En algunos informes, es posible que desee atribuir el pedido a la búsqueda de pago. En otros informes, es posible que desee atribuir el pedido a los medios sociales. La atribución permite controlar este aspecto del sistema de informes.

## Definición del modelo de atribución predeterminado de un componente

Puede establecer un modelo de atribución predeterminado para una métrica determinada actualizando la configuración de la métrica en la vista de datos. Al hacerlo, se anula el modelo de atribución de la métrica cada vez que se utiliza en Analysis Workspace.

>[!NOTE]
>
>Tenga en cuenta lo siguiente al habilitar la atribución en una métrica:
>
>* **Al usar el componente en un informe con *una sola dimensión*:** La atribución del componente ignora el modelo de asignación cuando se usa un modelo de atribución no predeterminado.
>
>* **Al usar el componente en un informe con *varias dimensiones*:** La atribución del componente retiene el modelo de asignación cuando se usa un modelo de atribución no predeterminado.
>
>   Solo hay varias dimensiones disponibles cuando [se exportan datos a la nube](/help/analysis-workspace/export/export-cloud.md).
>
> Para obtener más información acerca de la asignación, vea [Configuración del componente de persistencia](/help/data-views/component-settings/persistence.md).

Para actualizar el modelo de atribución predeterminado de un componente:

1. Vaya a la vista de datos que contiene el componente cuyo modelo de atribución predeterminado desea actualizar.

1. Seleccione el componente y, a continuación, expanda la sección Atribución en el lado derecho de la pantalla.

   ![Ventana de vistas de datos que resalta la opción Establecer atribución](../assets/attribution-settings.png)

1. Seleccione [!UICONTROL **Establecer atribución**] y, a continuación, seleccione el modelo de atribución en el menú desplegable [!UICONTROL **Modelo de atribución**].

   Consulte [Modelos de atribución](#attribution-models) para obtener más información sobre cada modelo de atribución.

1. Seleccione [!UICONTROL **Guardar y continuar**].

>[!TIP]
>
>Si su organización requiere que una métrica tenga varias configuraciones de atribución, puede realizar una de las siguientes acciones:
>
> * Copie la métrica en la vista de datos con cada configuración de atribución deseada. Puede incluir la misma métrica varias veces en una vista de datos, lo que otorga a cada métrica una configuración diferente. Asegúrese de etiquetar cada métrica de forma adecuada para que los analistas comprendan la diferencia entre estas métricas al generar informes.
>
> * Anule la métrica en Analysis Workspace. En la [configuración de columna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) de una métrica, seleccione **[!UICONTROL Usar modelo de atribución no predeterminado]** para cambiar el modelo de atribución y la ventana retrospectiva de la métrica para ese informe específico.

## Modelos de atribución {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataviews_component_attribution_attributionmodels"
>title="Modelo"
>abstract="Seleccione un modelo de atribución para la métrica."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}


## Ventana retroactiva

{{attribution-lookback-window}}



## Ejemplo de atribución {#attribution-example}

Consideremos el siguiente ejemplo:

1. El 15 de septiembre, una persona llega a su sitio a través de un anuncio de búsqueda de pago y luego lo abandona.
1. El 18 de septiembre, la persona regresa a su sitio a través de un vínculo de medios sociales que obtuvo de un amigo. Agregan varios artículos al carro, pero no compran nada.
1. El 24 de septiembre, su equipo de marketing les enviará un correo electrónico con un cupón para algunos de los artículos del carrito. Aplican el cupón, pero visitan otros sitios para ver si hay otros cupones disponibles. Encontraron otro a través de un anuncio y finalmente hicieron una compra por valor de 50 dólares.

Según la ventana retrospectiva y el modelo de atribución, los canales reciben crédito diferente. A continuación se muestran algunos ejemplos:

* Con **primer contacto** y una **ventana retrospectiva de sesión**, la atribución solo se fijará en la tercera visita. Entre el correo electrónico y la visualización, el correo electrónico fue el primero, por lo que el correo electrónico recibe un 100% de crédito por la compra de 50 dólares.

* Con **primer contacto** y una **ventana retrospectiva de persona**, la atribución se fijará en las tres visitas. La búsqueda de pago fue la primera, así que recibe un 100% de crédito por la compra de 50 dólares.

* Con **linear** y una ventana retrospectiva de **sesión**, el crédito se divide entre el correo electrónico y la visualización. Cada uno de estos canales recibe un crédito de 25 dólares.
Con **linear** y una **ventana retrospectiva de persona**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización. Cada canal recibe un crédito de 12,50 dólares por esta compra.

* Con **J-shape** y una **ventana retrospectiva de persona**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización.

   * Se otorga un crédito del 60 % a la visualización, es decir, 30 dólares.
   * El 20 % de crédito se asigna a la búsqueda de pago, 10 dólares en este caso.
   * El 20% restante se divide entre el medio social y el correo electrónico, lo que otorga 5 dólares a cada uno.

* Con **Deterioro de tiempo** y una **ventana retrospectiva de persona**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización. Con la semivida de 7 días predeterminada:

   * Diferencia de cero días entre el punto de contacto de visualización y la conversión. `2^(-0/7) = 1`
   * Diferencia de cero días entre el punto de contacto del correo electrónico y la conversión. `2^(-0/7) = 1`
   * Diferencia de seis días entre el punto de contacto social y la conversión. `2^(-6/7) = 0.552`
   * Diferencia de nueve días entre el punto de contacto de búsqueda de pago y la conversión. `2^(-9/7) = 0.41`
   * La normalización de estos valores resulta en lo siguiente:

      * Visualización: 33,8 %, 16,88 dólares
      * Correo electrónico: 33,8 % 16,88 dólares
      * Medio social: 18,6 %, 9,32 dólares
      * Búsqueda de pago: 13,8 %, 6,92 dólares

Los eventos de conversión que generalmente tienen números enteros se dividen si el crédito pertenece a más de un canal. Por ejemplo, si dos canales contribuyen a un pedido mediante un modelo de atribución lineal, ambos canales obtienen 0,5 de ese pedido. Estas métricas parciales se suman en todas las personas y luego se redondean al entero más cercano para los informes.


