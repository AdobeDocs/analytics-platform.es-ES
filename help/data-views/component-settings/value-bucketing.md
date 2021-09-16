---
title: Configuración del componente de agrupamiento de valores
description: Combinar valores numéricos en una dimensión.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 12%

---


# Configuración del componente Agrupación de valores

Al crear o editar una vista de datos, la agrupación de valores permite combinar valores numéricos basados en un rango. Solo está disponible para dimensiones que utilizan tipos de datos de esquema entero o doble.

La agrupación de valores es útil cuando desea agrupar intervalos en lugar de tratar cada número único como un elemento de dimensión independiente. Por ejemplo, un bloque de &quot;Entre 5 y hasta 10&quot; aparece como un elemento de línea de &quot;5 a 10&quot; en Analysis Workspace.

![Clasificación de valor](../assets/value-bucketing.png)

Si desea la flexibilidad de los informes tanto en una dimensión agrupada como en otra no agrupada, arrastre dos copias del componente a la lista de dimensiones disponibles. Habilite el agrupamiento en una dimensión y deshabilite en la otra.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Valor del cubo] | Casilla de verificación que permite activar el agrupamiento. |
| [!UICONTROL Menos de] | Límite superior del primer bloque de dimensiones. |
|  [!UICONTROL Inclusión y menor que] | Límites de bloques subsiguientes. |
| [!UICONTROL Mayor o igual que] | Límite inferior del último bloque de dimensiones. |
| [!UICONTROL Añadir cubo] | Permite añadir otro bloque a la agrupación de dimensiones numéricas. Puede añadir hasta 20 bloques en una sola dimensión. |
