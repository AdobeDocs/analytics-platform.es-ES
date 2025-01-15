---
description: Panel que muestra los elementos de dimensión siguientes o anteriores de una dimensión específica.
title: Panel de elemento siguiente o anterior
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: bf5853a1d23d6e648024016a64dc67d09da3fbb4
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 36%

---

# Panel de elemento siguiente o anterior {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Elemento siguiente o anterior"
>abstract="Cree un panel para comprender las dimensiones anteriores de las que provienen las personas o la siguiente dimensión a la que se dirigen."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Elemento siguiente o anterior"
>abstract="Analice cuáles son los lugares más habituales de los que proceden o a los que se dirigen los visitantes.<br/><br/>**Dimensión**: seleccione una dimensión. Por ejemplo, **Página**.<br/>**Elemento de dimensión**: seleccione un elemento de dimensión específico. Por ejemplo, **Página principal**.<br/>**Dirección**: seleccione **Siguiente** para ver los elementos de dimensión que aparecen justo después del elemento de dimensión seleccionado. Seleccione **Anterior** para ver los elementos de dimensión que conducen al elemento de dimensión seleccionado.<br/>**Contenedor**: seleccione **Sesión** para ver los elementos de dimensión siguientes o anteriores de la misma sesión, o **Persona** para ver el elemento de dimensión siguiente o anterior de la misma persona."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*Este artículo documenta el panel Elemento siguiente o anterior en **Customer Journey Analytics**.<br/>Ver [panel de elemento siguiente o anterior](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) para la versión de **Adobe Analytics**de este artículo.*

>[!ENDSHADEBOX]

El panel **[!UICONTROL Elemento siguiente o anterior]** contiene varias tablas y visualizaciones para identificar el elemento de dimensión siguiente o anterior de una dimensión específica. Por ejemplo, es posible que desee explorar a qué páginas fueron más a menudo los clientes después de visitar la página de inicio.

## Utiliza

Para usar un panel **[!UICONTROL Elemento siguiente o anterior]**:

1. Crear un panel de **[!UICONTROL elemento siguiente o anterior]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.

### Entrada de panel

Puede configurar el panel [!UICONTROL Elemento siguiente o anterior] con esta configuración de entrada:

![Panel de elemento siguiente o anterior](assets/next-or-previous-item.png)

| Entrada | Descripción |
| --- | --- |
| **[!UICONTROL Dimensión]** | Seleccione la dimensión para la que desea explorar los elementos siguientes o anteriores. |
| **[!UICONTROL Elemento de dimensión]** | Seleccione el elemento de dimensión específico en el centro de la consulta siguiente/anterior. |
| **[!UICONTROL Dirección]** | Especifique si está buscando el elemento de dimensión [!UICONTROL Siguiente] o [!UICONTROL Anterior]. |
| **[!UICONTROL Contenedor]** | Seleccione el contenedor [!UICONTROL Sesión] o [!UICONTROL Persona] (predeterminado) para determinar el ámbito de la consulta. |

{style="table-layout:auto"}

Seleccione **[!UICONTROL Generar]** para generar el panel.

### Salida de panel

El panel [!UICONTROL Elemento siguiente o anterior] devuelve un conjunto completo de datos y visualizaciones para ayudarle a comprender mejor qué ocurrencias siguen o preceden a elementos de dimensión específicos.


![Salida de panel siguiente/anterior](assets/next-or-previous-item-output.png)


| Visualización | Descripción |
| --- | --- |
| **[!UICONTROL Barra horizontal]** | Enumera los elementos siguientes (o anteriores) en función del elemento de dimensión seleccionado. Al pasar el ratón por encima de una barra individual, se resalta el elemento correspondiente de la tabla de forma libre. |
| **[!UICONTROL Número de resumen]** | Número de resumen de alto nivel de todas las ocurrencias de elementos de dimensión siguientes o anteriores para el mes actual (hasta ahora). |
| **[!UICONTROL Tabla de forma libre]** | Enumera los elementos siguientes (o anteriores) en función del elemento de dimensión seleccionado, en formato de tabla. Por ejemplo, cuáles eran las páginas más populares (por ocurrencias) a las que se dirigían los visitantes después (o antes) de la página principal o de la página de Workspace. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Crear un panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
