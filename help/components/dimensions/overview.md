---
title: Información general de dimensiones
description: Descubra cuáles son las dimensiones y cómo se utilizan en Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 1564c91616015311393a643fe7fcecd429cf3a36
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 37%

---

# Información general de dimensiones

Los Dimension son un tipo de componente en Customer Journey Analytics que se utiliza para analizar datos. Por ejemplo, usa dimensiones al crear informes en [Analysis Workspace](/help/analysis-workspace/home.md) o en [Report Builder](/help/report-builder/report-buider-overview.md).

Las dimensiones de Customer Journey Analytics son un número ilimitado; los valores pueden ser numéricos, de texto, de objetos, de listas o de mezclas de todos.

Un informe básico en Customer Journey Analytics muestra filas de dimensiones (normalmente valores de cadena) frente a una columna de métricas (normalmente valores numéricos).

Por ejemplo, si combina la dimensión “Página” con la métrica “Visitas”, obtendrá un informe de clasificación que muestre las páginas más visitadas:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

Cada dimensión representa una parte o faceta diferente del sitio. Puede combinar una o más de estas dimensiones con una o más métricas para crear un informe deseado.

## Creación de dimensiones

Los administradores de Customer Journey Analytics pueden [crear dimensiones dentro de una vista de datos](/help/data-views/create-dataview.md#components).

## Agregar descripciones de dimensión

Los administradores de Customer Journey Analytics pueden agregar descripciones para dimensiones y otros componentes dentro de la vista de datos o directamente en Analysis Workspace. Para obtener información acerca de cómo añadir descripciones a dimensiones, consulte [Adición de descripciones de componentes](/help/components/add-component-descriptions.md).
