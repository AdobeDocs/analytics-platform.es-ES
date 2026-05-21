---
title: Información general de dimensiones
description: Descubra qué son las dimensiones y cómo se utilizan en Customer Journey Analytics.
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
TQID: https://experienceleague.adobe.com/bMM7desF2wr71h-SR1mzD7-oSwm-8cPvmeU7SeM7-fU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 253
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

