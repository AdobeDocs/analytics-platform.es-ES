---
description: Obtenga más información sobre
title: Tipo de métrica y atribución
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 7f3412dc852ccae1ad5e122c200da5567ba89e87
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 37%

---

# Tipo de métrica y atribución

Si selecciona el icono de engranaje junto a una métrica, puede especificar el tipo de métrica y el modelo de atribución.

## Tipo de métrica

Para especificar el tipo de métrica al crear una métrica calculada:

1. Seleccione el icono de engranaje situado junto a la métrica cuyo tipo desee seleccionar.

   ![](assets/cm_type_alloc.png)

1. Elija entre las siguientes opciones:

   | Tipo de métrica | Definición |
   |---|---|
   | Estándar | Estas métricas son las mismas métricas utilizadas en los informes de [!DNL Analytics] estándares. Si una fórmula consiste en una única métrica estándar, muestra datos idénticos a los de su métrica no calculada homóloga. Las métricas estándar son útiles para crear métricas calculadas específicas para cada elemento de línea individual. Por ejemplo, [Pedidos] / [Sesiones] toma pedidos para ese elemento de línea específico y lo divide por el número de sesiones para ese elemento de línea específico. |
   | Total general | Utilice el total general para el período de informe de cada elemento de línea. Si una fórmula consiste en una única métrica de total general, muestra el mismo número de total general en cada elemento de línea. Las métricas de total general son útiles para crear métricas calculadas que se comparan con los datos totales del sitio. Por ejemplo, [Pedidos] / [Total de sesiones] muestra la proporción de pedidos en comparación con TODAS las sesiones del sitio, no solo las sesiones del elemento de línea específico. |

## Atribución

Para obtener información sobre la atribución en Customer Journey Analytics, consulte [Configuración del componente de atribución](/help/data-views/component-settings/attribution.md).
