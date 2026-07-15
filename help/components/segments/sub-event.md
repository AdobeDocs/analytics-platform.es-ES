---
title: Análisis de subeventos
description: Descubra cómo el análisis de subeventos le permite filtrar productos individuales u otros contenedores dentro de un evento en Customer Recorrido Analytics, lo que elimina el sangrado de atribución en los informes de productos.
feature: Segmentation
hide: true
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 9%

---

# Análisis de subeventos

{{release-limited-testing}}

El análisis de subeventos permite analizar los datos de eventos en un nivel más granular que el nivel de evento. En lugar de filtrar todo el evento, puede segmentar contenedores individuales dentro de los eventos. Por ejemplo:

- Segmentación en una categoría de producto específica sin incluir todos los demás productos comprados en el mismo pedido
- ¿Desea segmentar una categoría de recursos específica en los datos de análisis de contenido?
- Segmentación en un canal de medios específico dentro de los datos de análisis de medios.


En Customer Journey Analytics, puede definir contenedores dentro de una vista de datos para la que desea utilizar el análisis de subeventos. Sin el análisis de subeventos, la segmentación en un atributo de elemento de contenedor devuelve todos los eventos, sesiones, personas, cuentas (globales) [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, grupos compradores [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, oportunidades [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} u otros [contenedores](/help/data-views/create-dataview.md#containers-1) que haya definido. El resultado es una atribución incorrecta y métricas de ingresos infladas. El análisis de subeventos establece el ámbito del filtro en filas de contenedor individuales dentro de un evento y resuelve estos problemas.

En el análisis de subeventos, la lógica de exclusión se comporta de forma diferente a la exclusión estándar a nivel de evento en el contenedor. Cuando excluye atributos de elementos dentro del contenedor, el segmento devuelve eventos que **tienen elementos** dentro del contenedor, pero que no coinciden con los criterios de exclusión. El segmento no devuelve ningún evento sin elementos.


## Ejemplo

Desea medir únicamente los ingresos de la categoría de trajes profesionales. Sin análisis de subeventos, la aplicación de un segmento para trajes profesionales incluye ingresos de cada producto en cualquier pedido (evento) que contenga al menos un producto con la categoría de trajes profesionales. Con el análisis de subeventos, el filtro se aplica al nivel de producto y solo se devuelven ingresos para los productos de la categoría de trajes profesionales.

También desea medir los ingresos en línea de todas las demás categorías, excepto la categoría de trajes profesionales.

>[!BEGINTABS]

>[!TAB Análisis de eventos]

En el generador de segmentación o como parte de un **[!UICONTROL segmento rápido]**, especificas **[!UICONTROL Incluir]** el **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL es igual a]** **[!UICONTROL Trajes profesionales]** en el contenedor de **[!UICONTROL Eventos]**.

![Panel que muestra la segmentación en el nivel de evento para los trajes profesionales de la categoría de productos](./assets/product-category-segmentation-events.png)

Como resultado, se tienen en cuenta todos los pedidos que contienen al menos **[!UICONTROL Trajes profesionales]** **[!UICONTROL product_category]**, y los ingresos de otros productos de esos pedidos se incluyen en la métrica **[!UICONTROL Ingresos]**.Cuando se informa sobre categorías, se informa de todos los demás valores de **[!UICONTROL product_category]** que formaban parte de un pedido que incluía un producto con **[!UICONTROL Trajes profesionales]** **[!UICONTROL product_category]**.

>[!TAB Análisis de subeventos]

En el generador de segmentación o como parte de un **[!UICONTROL segmento rápido]**, especifica que **[!UICONTROL se incluya]** el **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL es igual a]** **[!UICONTROL Trajes profesionales]** en el contenedor de **[!UICONTROL Productos]**.

![Panel que muestra la segmentación en el nivel de subevento para los trajes profesionales de la categoría de productos](./assets/product-category-segmentation-subevents.png)

Como resultado, se tienen en cuenta todos los pedidos que contienen al menos **[!UICONTROL Trajes profesionales]** **[!UICONTROL product_category]**, y solo se incluyen los ingresos de los productos que pertenecen a los **[!UICONTROL Trajes profesionales]** **[!UICONTROL product_category]** para la métrica **[!UICONTROL Ingresos]**.Cuando se informa sobre categorías, solo se informa sobre **[!UICONTROL Grupos profesionales]** **[!UICONTROL Rproduct_category]**.

>[!TAB Análisis de subeventos (excluir)]

En el generador de segmentación o como parte de un **[!UICONTROL segmento rápido]**, especificas **[!UICONTROL Excluir]** el **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL es igual a]** **[!UICONTROL Trajes profesionales]** en el contenedor de **[!UICONTROL Productos]**.

![Panel que muestra la segmentación en el nivel de subvisita para excluir la categoría de productos Hombres](./assets/product-category-segmentation-subevents-exclude.png)

Para excluir en el nivel de producto, se incluyen los eventos que contienen al menos un producto y, a continuación, la exclusión en el nivel de subevento se aplica dentro de ese ámbito. Esta exclusión difiere de la exclusión de nivel de evento, que excluye todo el evento.

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
