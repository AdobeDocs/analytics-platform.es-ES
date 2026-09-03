---
title: Configuración del componente de agrupamiento de valores
description: Combine valores numéricos en una dimensión.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:00.872Z'
TQID: 'https://experienceleague.adobe.com/LHEk3h9utGW73kSo2-SgY5NgKi11uktKR0ucPxw9IcY'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 100%

---

# Configuración del componente de [!UICONTROL agrupamiento de valores] {#value-bucketing-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_value_bucketing"
>title="Creación de depósitos"
>abstract="Agrupe los valores en intervalos específicos. Estos intervalos aparecen como elementos de dimensión en los informes."

<!-- markdownlint-enable MD034 -->


Al crear o editar una vista de datos, la agrupación de valores permite combinar valores numéricos basados en un rango. Solo está disponible para dimensiones que utilizan tipos de datos de esquema entero o doble.

![Clasificación de valor](../assets/value-bucketing.png)

La agrupación de valores es útil cuando desea agrupar intervalos en lugar de tratar cada número único como un elemento de dimensión independiente. Por ejemplo, un bloque de entre 5 y 10 aparecerá como un elemento de línea de 5 a 10 en Analysis Workspace.

Si desea la flexibilidad al crear informes tanto en términos de dimensiones agrupadas como en no agrupadas, arrastre dos copias del componente a la lista de dimensiones disponibles. Habilite el agrupamiento en una dimensión y deshabilite en la otra.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Valor del cubo] | Casilla de verificación que permite activar el agrupamiento. |
| [!UICONTROL Menos de] | Límite superior del primer bloque de dimensiones. |
| [!UICONTROL Incluyendo] [!UICONTROL y menor que] | Límites de bloques subsiguientes. |
| [!UICONTROL Mayor o igual que] | Límite inferior del último bloque de dimensiones. |
| [!UICONTROL Añadir cubo] | Permite añadir otro bloque a la agrupación de dimensiones numéricas. Puede añadir hasta 20 bloques en una sola dimensión. |

{style="table-layout:auto"}
