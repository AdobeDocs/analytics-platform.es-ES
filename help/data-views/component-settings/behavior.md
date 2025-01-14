---
title: Configuración de componentes de comportamiento
description: Especifique cómo se comporta una dimensión o métrica en la creación de informes.
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 90%

---

# Configuración de componentes de comportamiento {#behavior-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_behavior"
>title="Comportamiento"
>abstract="Determine cómo se añaden los elementos de línea de esta dimensión.<br/><br/>**Parámetros **<br/>**Minúsculas**: permite especificar si los valores de cadena del campo deben estar en minúsculas."

<!-- markdownlint-enable MD034 -->


La configuración de comportamiento está disponible tanto en dimensiones como en métricas. La disponibilidad de la configuración depende del tipo de componente y del tipo de datos de esquema.

![Configuración de comportamiento](../assets/behavior-settings.png)

## Configuración de comportamiento de dimensión

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Minúsculas] | Anula la duplicación de filas que tienen el mismo valor pero mayúsculas y minúsculas diferentes. Si se habilita, todas las instancias de una dimensión con el mismo valor se informan como minúsculas. Por ejemplo, los datos contienen los valores `"liverpool"` `"Liverpool"` y `"LIVERPOOL"` en una dimensión de cadena. Si las [!UICONTROL minúsculas] están habilitadas, los tres valores se combinan en `"liverpool"`. Si está desactivado, los tres valores se tratan como diferentes. |

{style="table-layout:auto"}

>[!NOTE]
>
>Si habilita las [!UICONTROL minúsculas] en una dimensión del conjunto de datos de consulta, pueden existir varios valores de búsqueda para el mismo identificador. Si se produce este conflicto, Customer Journey Analytics utiliza el primer valor de intercalación ASCII (los valores en mayúsculas preceden a los valores en minúsculas). Adobe recomienda evitar el uso de conjuntos de datos de búsqueda que contienen el mismo valor cuando las [!UICONTROL minúsculas] está habilitadas.

![Dimensión que distingue entre mayúsculas y minúsculas](../assets/case-sens-workspace.png)

## Configuración del comportamiento de las métricas

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Contar valores] | Visible en los tipos de datos de esquema entero y doble. Aumente la métrica en la cantidad especificada. Por ejemplo, aumenta una métrica en 50 si el valor de la columna es `50`. |
| [!UICONTROL Contar instancias] | Visible en los tipos de datos de esquema entero y doble. Aumente la métrica en uno, independientemente del valor. La presencia de cualquier valor aumenta la métrica. Por ejemplo, aumenta una métrica en 1 si el valor de la columna es `50`. |
| [!UICONTROL Valores para contar] | Visible en tipos de datos de esquema booleanos. Permite determinar si la métrica aumenta contando `true`, `false` o ambos. |

{style="table-layout:auto"}

Puede generar las métricas Pedidos e Ingresos en Analysis Workspace utilizando la misma columna de conjunto de datos de evento con comportamientos diferentes. Arrastre la columna del conjunto de datos Ingresos a la vista de datos dos veces y establezca uno en Contar valores y el otro en Contar instancias. La métrica Pedidos cuenta las instancias, mientras que la métrica Ingresos cuenta los valores.
