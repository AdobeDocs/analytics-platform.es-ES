---
title: Explicación de los subeventos y las matrices de objetos en las fuentes de datos
description: Descubra cómo las fuentes de datos de Customer Journey Analytics exportan subeventos desde matrices de esquemas, preservando la jerarquía en lugar de aplanarlos como lo hace Workspace.
hide: true
feature: Components
source-git-commit: afc1b55eb54b5f3342800489d0a7f63508ee8b10
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%
---
# Subeventos en fuentes de datos

{{release-limited-testing}}

En el esquema XDM, todo lo que sea una matriz (cadena u objeto) es un subevento. Los subeventos de Customer Journey Analytics se representan en exportaciones de fuentes de datos con su jerarquía.

En Adobe Analytics, los subeventos se representan como una sola columna.

Utilice la siguiente información para comprender cómo trabajar con subeventos en las fuentes de datos de Customer Journey Analytics.

## Subeventos en el esquema XDM, Workspace y fuentes de datos

Los subeventos se definen en el esquema XDM, ya sea como matrices de cadenas o matrices de objetos.

Estos subeventos se representan de forma diferente, en función de si los ve en Analysis Workspace o en las fuentes de datos.

| Ubicación | Representación de los subeventos |
| --- | --- |
| **Analysis Workspace** | Los objetos individuales de una matriz de objetos se pueden seleccionar como componentes individuales, independientes de cualquier jerarquía visible. |
| **Fuentes de datos** | Los objetos de una matriz de objetos se representan como un grupo, con su jerarquía intacta. |

## Añadir datos de subevento a una fuente de datos

Cuando intenta agregar una columna que es un subevento al crear una fuente de datos, aparece un cuadro de diálogo que le permite agregar todos los subeventos del mismo nivel. Todos estos eventos aparecerán en una sola columna de la salida de la fuente de datos.

## Visualización de datos de subevento en la salida de la fuente de datos

Los datos de subevento (como varios productos en un solo evento) aparecen de forma diferente en las fuentes de datos de Customer Journey Analytics y en las de Adobe Analytics. La siguiente tabla compara cómo cada producto representa los datos de subeventos.

| Producto | Aspecto de los datos de subeventos en las fuentes de datos | Ejemplo: lista de productos |
| --- | --- | --- |
| **Adobe Analytics** | Se aplana en una cadena delimitada en una sola columna. | Una lista de productos contiene varios productos agrupados en una sola cadena:<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Los subeventos mantienen la jerarquía definida en el esquema XDM. Permanecen agrupados en la misma columna, junto con su evento principal y subeventos del mismo nivel. | Una lista de productos mantiene su jerarquía que se define en el esquema XDM como una matriz:<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Datos de subevento de consulta en la salida de la fuente de datos

Dado que los datos de subevento [&#x200B; aparecen de forma diferente en las fuentes de datos de Customer Journey Analytics](#customer-journey-analytics-vs-adobe-analytics), las consultas que utiliza para ellos difieren de las que utiliza para las fuentes de datos de Adobe Analytics.

Los siguientes ejemplos muestran cómo buscar eventos que incluyen un producto específico. Los ejemplos utilizan la sintaxis de Google BigQuery. Otros almacenes de datos, como Snowflake y Databricks, admiten el mismo enfoque con diferencias de sintaxis menores.

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






