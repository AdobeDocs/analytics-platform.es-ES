---
title: Configuración de componentes de comportamiento
description: Especifique cómo se comporta una dimensión o métrica en los informes.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 4%

---


# Configuración de componentes de comportamiento

La configuración de comportamiento está disponible tanto en dimensiones como en métricas. La configuración disponible depende del tipo de componente y del tipo de datos de esquema.

![Configuración de comportamiento](../assets/behavior-settings.png)

## Configuración de comportamiento del Dimension

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Minúsculas] | Anula la duplicación de filas que tienen el mismo valor pero mayúsculas y minúsculas diferentes. Si se habilita, todas las instancias de una dimensión con el mismo valor se informan como minúsculas. Por ejemplo, los datos contienen los valores `"liverpool"`, `"Liverpool"` y `"LIVERPOOL"` en una dimensión de cadena. Si [!UICONTROL Lower case] está habilitado, los tres valores se combinan en `"liverpool"`. Si está desactivado, los tres valores se tratan como diferentes. |

![Dimensión que distingue entre mayúsculas y minúsculas](../assets/case-sens-workspace.png)

>[!NOTE]
>
>Si habilita [!UICONTROL Lower case] en una dimensión de conjunto de datos de consulta, pueden existir varios valores de búsqueda para el mismo identificador. Si se produce este conflicto, CJA utiliza el primer valor de intercalación ASCII (los valores en mayúsculas preceden a los valores en minúsculas). Adobe recomienda evitar el uso de conjuntos de datos de búsqueda que contienen el mismo valor cuando [!UICONTROL Lower case] está habilitado.

## Configuración del comportamiento de las métricas

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Contar valores] | Visible en los tipos de datos de esquema entero y doble. Aumente la métrica en la cantidad especificada. Por ejemplo, aumenta una métrica en 50 si el valor de la columna es `50`. |
| [!UICONTROL Contar instancias] | Visible en los tipos de datos de esquema entero y doble. Aumente la métrica en uno, independientemente del valor. La presencia de cualquier valor aumenta la métrica. Por ejemplo, aumenta una métrica en 1 si el valor de la columna es `50`. |
| [!UICONTROL Valores para contar] | Visible en tipos de datos de esquema booleanos. Permite determinar si la métrica aumenta contando `true`, `false` o ambos. |

Puede generar las métricas &quot;Pedidos&quot; e &quot;Ingresos&quot; en Analysis Workspace utilizando la misma columna de conjunto de datos de evento con comportamientos diferentes. Arrastre la columna del conjunto de datos &quot;Ingresos&quot; a la vista de datos dos veces y establezca uno en &quot;Contar valores&quot; y el otro en &quot;Contar instancias&quot;. La métrica &quot;Pedidos&quot; cuenta las instancias, mientras que la métrica &quot;Ingresos&quot; cuenta los valores.
