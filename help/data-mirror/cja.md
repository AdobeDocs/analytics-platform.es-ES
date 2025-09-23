---
title: Configuración de Customer Journey Analytics
description: Obtenga información sobre cómo configurar conexiones de Customer Journey Analytics, vistas de datos y proyectos para Experience Platform Data Mirror para Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: b585187f112c2081a8e51bd84d9f95e75ceebdc3
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---

# Configuración de Customer Journey Analytics

{{release-limited-testing}}

Para utilizar la función Experience Platform Data Mirror para Customer Journey Analytics, debe crear o actualizar conexiones, vistas de datos y proyectos de Workspace para utilizar datos basados en modelos.

## Conexiones

En su conexión, agregue los conjuntos de datos basados en modelos que representan los datos de las soluciones nativas del almacén de datos. Estos conjuntos de datos no tienen el tipo de conjunto de datos Modelo.

Cuando se agrega un conjunto de datos basado en un modelo que contiene datos reflejados de una solución nativa del almacén de datos, esos datos suelen ser datos de evento. Asegúrese de seleccionar la configuración correcta para el conjunto de datos. Por ejemplo, seleccione el tipo de conjunto de datos correcto, el campo para la identidad y el campo para la marca de tiempo.


## Vistas de datos

Defina los campos del esquema basado en modelos como componentes (métricas y dimensiones) en la vista de datos. Los campos reflejados de datos están disponibles en la subcarpeta **[!UICONTROL Campos ad hoc y basados en modelos]** de la carpeta **[!UICONTROL Conjuntos de datos de eventos]**. Use funcionalidades, como [campos derivados](/help/data-views/derived-fields/derived-fields.md) o [configuración de componentes](/help/data-views/component-settings/overview.md), para modificar los componentes basados en campos basados en modelos.


## Proyectos de Workspace

Configure proyectos de Workspace que utilicen métricas y dimensiones de los datos basados en modelos. Componentes que, en última instancia, se basan en los datos de su solución nativa de Data Warehouse. Y se actualizan en función de la funcionalidad de reflejo de datos que haya configurado.

>[!MORELIKETHIS]
>
>[Guía de inicio rápido de Data Mirror: crear reflejos y utilizar datos basados en modelos](model-based.md)
>
