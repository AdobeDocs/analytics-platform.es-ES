---
title: Usar CJA con matrices de objetos
description: Comprender cómo CJA informa sobre las jerarquías de datos.
translation-type: tm+mt
source-git-commit: b7cd74f3fe2f0222e78452f58a7c387f6e0c86d2
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# Usar CJA con matrices de objetos

Algunos esquemas de plataforma pueden tener matrices de objetos. Uno de los ejemplos más comunes sería un carro de compras, que contiene múltiples productos. Cada producto tiene un nombre, SKU, categoría, precio, cantidad y cualquier otra dimensión que desee rastrear. Todas estas facetas tienen requisitos separados, pero todas deben encajar en la misma visita.

En versiones anteriores de Adobe Analytics, esta función se realizaba mediante la `products` variable. Era una cadena concatenada separada por punto y coma (`;`) para separar facetas de un producto, mientras que comas (`,`) delineaba productos. Era la única variable con compatibilidad limitada con &quot;matrices de objetos&quot;. Las variables de varios valores, como las variables de lista, podrían admitir el equivalente de matrices, pero no podrían admitir &quot;matrices de objetos&quot;. CJA amplía este concepto al admitir jerarquías arbitrariamente profundas dentro de una sola fila de datos, una función que no está disponible en ninguna versión anterior de Adobe Analytics.

## Mismo ejemplo de visita individual

La siguiente visita es un objeto JSON que representa una compra hecha por un cliente de una lavadora y una secadora.

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
   * product : SKU
   * product : name
   * product : order_id
   * product : garantía: cobertura
   * producto : garantía: length
   * product : garantía: name
   * product : garantía: type
* **Métricas:**
   * product : pedidos
   * product : unidades
   * product : ingresos
   * product : garantía
   * product : garantía: ingresos

### Los mismos ejemplos de visitas (comportamiento de sistema de informes)

Utilizando solo la visita anterior, las tablas siguientes muestran los informes de Workspace con algunas combinaciones de dimensión y métrica.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA analiza de forma selectiva la dimensión y las métricas del objeto en función de la tabla.

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

CJA mira estas partes de la visita para generar el informe:

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

Dado que puede combinar cualquier dimensión con cualquier métrica, la siguiente tabla muestra cómo se harían los datos con valores de dimensión no especificados:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Existe un pedido de producto sin un nombre de garantía vinculado a él, por lo que el valor de dimensión se atribuye a &#39;No especificado&#39;. La misma situación se aplica también al pedido de garantía del producto:

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
