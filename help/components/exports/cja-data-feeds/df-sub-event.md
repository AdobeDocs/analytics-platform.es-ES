---
title: Explicación de los subeventos y las matrices de objetos en las fuentes de datos
description: Descubra cómo las fuentes de datos de Customer Journey Analytics exportan subeventos desde matrices de esquemas, preservando la jerarquía en lugar de aplanarlos como lo hace Workspace.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: a4fdb1f8d49b42b6de21881e0c8392995124c1ea
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 2%
---
# Subeventos en fuentes de datos

{{release-limited-testing}}

Los [subeventos](/help/components/segments/sub-event.md) de Customer Journey Analytics le permiten analizar datos de evento en un nivel más granular que el nivel de evento.

Utilice la siguiente información para comprender cómo trabajar con subeventos en las fuentes de datos de Customer Journey Analytics.

## Comprender los subeventos

### Subeventos en el esquema XDM

En el esquema XDM, cada elemento de una matriz (una matriz de cadenas o una matriz de objetos) es un subevento.

Para ver un evento con subeventos dentro del esquema XDM en Adobe Experience Platform, seleccione [!UICONTROL **Esquemas**] y, a continuación, expanda un evento que contenga subeventos.

En el ejemplo siguiente, `Product list items` es una matriz de objetos que contiene varios subeventos.

![Esquema XDM que contiene una matriz de objetos y subeventos](assets/df-sub-event-schema.png)

### Ejemplo de subevento: productos en un evento de compra

Un cliente compra dos productos en un único pedido: un taladro inalámbrico y dos baterías de taladro. Su implementación envía un único evento de compra que incluye ambos productos en la matriz de objetos `productListItems`:

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

Este evento contiene dos subeventos, uno para cada objeto de la matriz `productListItems`. La siguiente tabla muestra qué campos pertenecen al evento y cuáles a sus subeventos.

| Nivel | Campos | Lo que describen los campos |
| --- | --- | --- |
| **Evento** | `eventType`, `timestamp`, `commerce.purchases.value` | La compra en su conjunto. Cada campo tiene un valor para el evento. La métrica **Pedidos** cuenta `1` para este evento, independientemente de cuántos productos contenga. |
| **Subevento** | `SKU`, `name`, `quantity`, `priceTotal` en cada objeto `productListItems` | Un producto individual en la compra. Cada campo tiene un valor por producto. Por ejemplo, `quantity` es `1` para la perforadora inalámbrica y `2` para el paquete de baterías de perforación. |

{style="table-layout:auto"}

>[!NOTE]
>
>Los subeventos solo incluyen los datos que se envían con el evento. Customer Journey Analytics no reconstruye el contenido del carro de compras de eventos anteriores, como adiciones al carro de compras o cierres de compra. Para que los productos aparezcan como subeventos de un evento de compra, la implementación debe incluirlos en `productListItems` en ese evento de compra.

## Añadir datos de subevento a una fuente de datos

Cuando intenta agregar una columna que es un subevento al crear una fuente de datos, aparece un cuadro de diálogo que le solicita que agregue cualquiera de los subeventos del mismo nivel. En la salida de la fuente de datos, todos estos eventos aparecen en una sola columna.

## Visualización de datos de subevento en la salida de la fuente de datos

### Diferencias de subeventos entre Analysis Workspace y las fuentes de datos

Los subeventos se representan de forma diferente entre Analysis Workspace y las fuentes de datos en Customer Journey Analytics.

| Ubicación | Representación de los subeventos |
| --- | --- |
| **Analysis Workspace (en Customer Journey Analytics)** | Se pueden seleccionar como componentes individuales, separados de cualquier jerarquía visible. |
| **Fuentes de datos (en Customer Journey Analytics)** | Se representa como un grupo, con su jerarquía intacta. |

### Diferencias de subeventos entre Adobe Analytics y Customer Journey Analytics

Los datos de subeventos (como varios detalles del producto en un único evento de compra) aparecen de forma diferente en las fuentes de datos de Customer Journey Analytics y en las de Adobe Analytics. La siguiente tabla compara cómo cada producto representa los datos de subeventos.

| Producto | Aspecto de los datos de subeventos en las fuentes de datos | Ejemplo: lista de productos |
| --- | --- | --- |
| **Adobe Analytics** | Se aplana en una cadena delimitada en una sola columna. | Una lista de productos contiene varios productos agrupados en una sola cadena:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Los subeventos conservan la jerarquía definida en el esquema XDM. Cuando se agrupan en la misma columna, muestran su jerarquía relacional a su evento principal y a los subeventos del mismo nivel. | Una lista de productos mantiene su jerarquía que se define en el esquema XDM como una matriz:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Diferencias con respecto a Adobe Analytics

### Diferencias en la salida entre las fuentes de datos de Adobe Analytics y Customer Journey Analytics

Los datos de subeventos (como varios detalles del producto en un único evento de compra) aparecen de forma diferente en las fuentes de datos de Customer Journey Analytics y en las de Adobe Analytics. La siguiente tabla compara cómo cada producto representa los datos de subeventos.

| Producto | Aspecto de los datos de subeventos en las fuentes de datos | Ejemplo: lista de productos |
| --- | --- | --- |
| **Adobe Analytics** | Se aplana en una cadena delimitada en una sola columna. | Una lista de productos contiene varios productos agrupados en una sola cadena:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Los subeventos conservan la jerarquía definida en el esquema XDM. Cuando se agrupan en la misma columna, muestran su jerarquía relacional a su evento principal y a los subeventos del mismo nivel. | Una lista de productos mantiene su jerarquía que se define en el esquema XDM como una matriz:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Diferencias entre los subeventos de Analysis Workspace y la salida de las fuentes de datos

Los subeventos se representan de forma diferente entre Analysis Workspace y las fuentes de datos en Customer Journey Analytics.

| Ubicación | Representación de los subeventos |
| --- | --- |
| **Analysis Workspace** | Se pueden seleccionar como componentes individuales, separados de cualquier jerarquía visible. |
| **Fuentes de datos** | Se representa como un grupo, con su jerarquía intacta. |


## Visualización de datos de subevento en la salida de la fuente de datos

Los datos de subeventos (como varios detalles del producto en un único evento de compra) aparecen de forma diferente en las fuentes de datos de Customer Journey Analytics y en las de Adobe Analytics. La siguiente tabla compara cómo cada producto representa los datos de subeventos.

| Producto | Aspecto de los datos de subeventos en las fuentes de datos | Ejemplo: lista de productos |
| --- | --- | --- |
| **Adobe Analytics** | Se aplana en una cadena delimitada en una sola columna. | Una lista de productos contiene varios productos agrupados en una sola cadena:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Los subeventos conservan la jerarquía definida en el esquema XDM. Cuando se agrupan en la misma columna, muestran su jerarquía relacional a su evento principal y a los subeventos del mismo nivel. | Una lista de productos mantiene su jerarquía que se define en el esquema XDM como una matriz:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Datos de subevento de consulta en la salida de la fuente de datos

Dado que los datos de subevento [ aparecen de forma diferente en las fuentes de datos de Customer Journey Analytics](#view-sub-event-data-in-data-feed-output), las consultas que utiliza para ellos difieren de las que utiliza para las fuentes de datos de Adobe Analytics.

Los siguientes ejemplos muestran cómo buscar eventos que incluyen un producto específico. Los ejemplos utilizan la sintaxis de Google BigQuery. Otros almacenes de datos, como Snowflake y Databricks, admiten el mismo enfoque con diferencias de sintaxis menores.

+++ Consulta de datos de producto en fuentes de datos de Customer Journey Analytics

En las fuentes de datos de Customer Journey Analytics, los mismos dos productos aparecen como una matriz de objetos en la columna `product_list_items`. No se requiere análisis de delimitador:

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

La forma de escribir la consulta depende de si desea una fila por evento o una fila por producto coincidente.

**Devuelve una fila por evento**

Para filtrar eventos sin cambiar el número de filas, use `UNNEST` dentro de una subconsulta `EXISTS`:

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

Esta consulta devuelve una fila para cada evento coincidente, con la matriz `product_list_items` completa intacta, independientemente de la cantidad de productos que coincidan en la matriz.

**Devolver una fila por cada producto coincidente**

Para devolver una fila para cada producto coincidente, mueva `UNNEST` a la cláusula `FROM` externa:

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

Un evento con más de un producto coincidente aparece como varias filas y las columnas del evento, como `row_id`, se repiten en cada fila. Utilice este método solo cuando necesite detalles de nivel de producto. Para contar eventos en los resultados, use `COUNT(DISTINCT row_id)` en lugar de contar filas.

Este método se aplica a cualquier campo de matriz del esquema XDM, no solo a los productos.

+++

+++ Consulta de datos de producto en fuentes de datos de Adobe Analytics

En las fuentes de datos de Adobe Analytics, un evento con dos productos comprados juntos aparece como una sola cadena delimitada en la columna `product_list`:

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

Para buscar eventos que incluyan un taladro inalámbrico, analice esta cadena con una expresión regular:

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++






