---
title: Configuración del componente de agrupamiento de valores
description: Combine valores numéricos en una dimensión.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# Configuración del componente de [!UICONTROL agrupamiento de valores]

Al crear o editar una vista de datos, la agrupación de valores permite combinar valores numéricos basados en un rango. Solo está disponible para dimensiones que utilizan tipos de datos de esquema entero o doble.

La agrupación de valores es útil cuando desea agrupar intervalos en lugar de tratar cada número único como un elemento de dimensión independiente. Por ejemplo, un bloque de entre 5 y 10 aparecerá como un elemento de línea de 5 a 10 en Analysis Workspace.

![Clasificación de valor](../assets/value-bucketing.png)

Si desea la flexibilidad al crear informes tanto en términos de dimensiones agrupadas como en no agrupadas, arrastre dos copias del componente a la lista de dimensiones disponibles. Habilite el agrupamiento en una dimensión y deshabilite en la otra.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Valor del cubo] | Casilla de verificación que permite activar el agrupamiento. |
| [!UICONTROL Menos de] | Límite superior del primer bloque de dimensiones. |
| [!UICONTROL Incluyendo] [!UICONTROL y menor que] | Límites de bloques subsiguientes. |
| [!UICONTROL Mayor o igual que] | Límite inferior del último bloque de dimensiones. |
| [!UICONTROL Añadir cubo] | Permite añadir otro bloque a la agrupación de dimensiones numéricas. Puede añadir hasta 20 bloques en una sola dimensión. |

{style=&quot;table-layout:auto&quot;}
