---
title: Usar matrices de objetos
description: Descubra cómo Customer Journey Analytics informa sobre las jerarquías de datos.
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 61%

---

# Usar matrices de objetos

Algunos esquemas de la plataforma pueden tener matrices de objetos. Adobe Customer Journey Analytics admite la ingesta y generación de informes de matrices de objetos dentro de datos de evento, búsqueda y perfil. Uno de los ejemplos más comunes sería un carro de compras que tiene varios productos. Cada producto tiene un nombre, SKU, categoría, precio, cantidad y cualquier otra dimensión que desee rastrear. Todas estas facetas tienen requisitos diferentes, pero todas deben encajar en la misma visita.

En versiones anteriores de Adobe Analytics, esta función se realizaba con la variable `products`. Era una cadena concatenada separada por punto y coma (`;`) para distintas facetas de un producto, y con coma (`,`) para delinear productos. Era la única variable con compatibilidad limitada con “matrices de objetos”. Las variables de varios valores, como las variables de lista, podrían admitir el equivalente de matrices, pero no podrían admitir “matrices de objetos”. Customer Journey Analytics amplía este concepto al admitir jerarquías arbitrariamente profundas dentro de una sola fila de datos, una función que no está disponible en ninguna versión anterior de Adobe Analytics.

## Mismo ejemplo de evento

El siguiente evento es un objeto JSON que representa una compra hecha por un cliente de una lavadora y una secadora.

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

Al crear una vista de datos, están disponibles las siguientes dimensiones y métricas (según el esquema):

* **Dimensiones:**
   * ID
   * producto: SKU
   * producto: nombre
   * producto: order_id
   * producto: garantía: cobertura
   * producto: garantía: longitud
   * producto: garantía: nombre
   * producto: garantía: tipo
* **Métricas:**
   * producto: pedidos
   * producto: unidades
   * producto: ingresos
   * producto: garantía
   * producto: garantía: ingresos

### Mismos ejemplos de eventos (comportamiento de informes)

Solo con el evento anterior, las tablas siguientes muestran los informes de Workspace con algunas combinaciones de dimensión y métrica.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

Customer Journey Analytics analiza de forma selectiva la dimensión y las métricas del objeto en función de la tabla.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Si desea informar sobre los ingresos de la garantía, su proyecto tendría un aspecto similar al siguiente:

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

Customer Journey Analytics examina estas partes del evento para generar el informe:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

Como el secador no incluía una garantía, no está incluido en la tabla.

Dado que puede combinar cualquier dimensión con cualquier métrica, la siguiente tabla muestra cómo serían los datos con elementos de dimensión no especificados:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Existe un pedido de producto sin un nombre de garantía vinculado a él, por lo que el elemento de dimensión se atribuye a &#39;No especificado&#39;. La misma situación se aplica también al pedido de garantía del producto:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Observe los pedidos que no tienen un nombre vinculado a ellos. Son los pedidos atribuidos al elemento de dimensión &#39;No especificado&#39;.

### Combinación de métricas

Customer Journey Analytics no combina de forma nativa las métricas con nombres similares si se encuentran en diferentes niveles de objeto.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Sin embargo, puede crear una métrica calculada que combine las métricas deseadas:

Métrica calculada “Ingresos totales”: `[product : revenue] + [product : warranty : revenue]`

Al aplicar esta métrica calculada, se muestran los resultados deseados:

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |



## Limitaciones

Las limitaciones se aplican a matrices de datos utilizadas por Customer Journey Analytics y modeladas como parte de un esquema en Experience Platform. Consulte [Límites del modelo de datos](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-model-limits) y [Límites del tamaño de datos](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-size-limits) en las [Protecciones predeterminadas para la segmentación y los datos del perfil del cliente en tiempo real](https://experienceleague.adobe.com/es/docs/experience-platform/profile/guardrails).

