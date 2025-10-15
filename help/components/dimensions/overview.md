---
title: Información general de dimensiones
description: Descubra qué son las dimensiones y cómo se utilizan en Customer Journey Analytics.
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 100%

---

# Información general sobre las dimensiones

Las dimensiones son un tipo de componente en Customer Journey Analytics que se utiliza para analizar datos. Por ejemplo, use dimensiones para crear informes en [Analysis Workspace](/help/analysis-workspace/home.md) o en [Report Builder](/help/report-builder/rb-overview.md).

Las dimensiones de Customer Journey Analytics son ilimitadas; los valores pueden ser numéricos, de texto, objetos, listas o combinaciones de todos ellos.

Un informe básico en Customer Journey Analytics muestra filas de dimensiones (normalmente valores de cadena) frente a una columna de métricas (normalmente valores numéricos).

Por ejemplo, si combina la dimensión Página con la métrica Personas, obtendría un informe de clasificación que mostraría las páginas más visitadas por personas:

| Página | Personas |
| --- | ---: |
| Página de inicio | 800 |
| Página de producto | 500 |
| Página de compra | 100 |

{style="table-layout:fixed"}

Cada dimensión representa una parte o faceta diferente del sitio. Puede combinar una o más de estas dimensiones con una o más métricas para crear un informe deseado.


## Creación de dimensiones

Los administradores de Customer Journey Analytics pueden [crear dimensiones dentro de una vista de datos](/help/data-views/create-dataview.md#components).

## Dimensiones estándar

Al crear una vista de datos, los siguientes componentes se añaden de forma predeterminada como dimensiones a la vista de datos:

{{standard-dimensions}}


## Agregar descripciones de dimensión

Los administradores de Customer Journey Analytics pueden añadir descripciones para dimensiones y otros componentes tanto dentro de la vista de datos como directamente dentro de Analysis Workspace. Para obtener información acerca de cómo añadir descripciones a dimensiones, consulte [Adición de descripciones de componentes](/help/components/add-component-descriptions.md).

>[!MORELIKETHIS]
>
>[Descubra datos del cliente más detallados con la función de profundidad de evento](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947?profile.language=es#M576)
>

