---
title: Incluir valores de exclusión configuración de componentes
description: Incluya o excluya condicionalmente un elemento de dimensión según su valor.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 88%

---

# Incluir valores de exclusión configuración de componentes {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_includeexcludevalues"
>title="Incluir valores de exclusión"
>abstract="Filtre una métrica para contar solo los valores que coincidan con criterios específicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_includeexcludevalues"
>title="Incluir valores de exclusión"
>abstract="Limite una dimensión para incluir solo valores que coincidan con criterios específicos. Las inclusiones y exclusiones se realizan antes de la asignación y la segmentación en los informes. Determine si la lógica de segmento especificada distingue entre mayúsculas y minúsculas."

<!-- markdownlint-enable MD034 -->

Incluir valores de exclusión permite crear reglas que dependen del valor de un elemento de dimensión. Los valores que no cumplen los criterios establecidos se tratan en Analysis Workspace como si nunca hubieran existido, aunque los datos aún existan en el conjunto de datos subyacente.

![Ventana de vistas de datos que resalta la opción Incluir valores de exclusión](../assets/include-exclude.png)

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Establecer valores de inclusión y exclusión] | Casilla de verificación que permite habilitar condiciones en las que los datos se incluyen en una vista de datos. |
| [!UICONTROL Con distinción de mayúsculas y minúsculas] | Visible en tipos de datos de esquema de cadena. El valor predeterminado es Activado. Esta configuración solo se aplica a la lógica [!UICONTROL Incluir/excluir valores], no al valor resultante. Permite especificar si la regla distingue entre mayúsculas y minúsculas. |
| [!UICONTROL Coincidencias] | Le permite especificar qué valores desea tener en cuenta para la creación de informes antes de la atribución y segmentos (por ejemplo, usar solo valores que contengan la frase &quot;error&quot;). Puede especificar: **[!UICONTROL Si se cumplen todos los criterios]** o **[!UICONTROL Si se cumplen los criterios]**. Separe cada uno de los valores mediante un espacio. |
| [!UICONTROL Criterios] | Permite especificar la lógica de coincidencia que debe aplicarse a una regla de segmento específica.<ul><li>**Cadena**: [!UICONTROL Contiene la frase], [!UICONTROL Contiene cualquier término], [!UICONTROL Contiene todos los términos], [!UICONTROL No contiene ningún término], [!UICONTROL No contiene la frase], [!UICONTROL Es igual a], [!UICONTROL No es igual a], [!UICONTROL Comienza con], [!UICONTROL Finaliza con]</li><li>**Doble/entero**: [!UICONTROL Es igual a], [!UICONTROL No es igual a], [!UICONTROL Es mayor que], [!UICONTROL Es menor que], [!UICONTROL Es mayor o igual que], [!UICONTROL Es menor o igual que]</li><li>**Fecha**: [!UICONTROL Es igual a], [!UICONTROL No es igual a], [!UICONTROL Es posterior a], [!UICONTROL Es anterior a], [!UICONTROL Ocurre en]</li></ul> |
| [!UICONTROL Operando de coincidencia] | Permite especificar el operando de coincidencia al que se debe aplicar el operador de coincidencia.<ul><li>**Cadena**: Campo de texto</li><li>**Doble/entero**: Campo de texto con flechas arriba/abajo para valores numéricos</li><li>**Fecha**: Selector de granularidad de día (calendario)</li><li>**Fecha y hora**: Selector de granularidad de fecha y hora</li></ul> |
| [!UICONTROL Añadir regla] | Permite especificar un operador de coincidencia y un operador adicionales. |

{style="table-layout:auto"}
