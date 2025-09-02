---
title: Configuración del componente Grupo de datos de resumen
description: Detalles y cómo configurar dimensiones de conjuntos de datos para garantizar que puede informar correctamente sobre los datos de resumen.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 89%

---

# Configuración del componente [!UICONTROL Grupo de datos de resumen] {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="Grupo de datos de resumen"
>abstract="Un grupo de datos de resumen crea una asociación entre todas las dimensiones de la agrupación y se utiliza para combinar dimensiones de conjuntos de datos de resumen con otras dimensiones para la creación de informes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="Ocultar en la creación de informes"
>abstract="Si selecciona esta opción, se habilitará **[!UICONTROL Ocultar componente en la creación de informes]** para esa dimensión y se evitará que el componente se muestre en Analysis Workspace y otras herramientas de creación de informes de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->



Un grupo de datos de resumen crea una asociación entre todas las dimensiones de la agrupación y se utiliza para combinar dimensiones de conjuntos de datos de resumen con otras dimensiones para la creación de informes.

![Configuración del componente Grupo de datos de resumen](/help/data-views/assets/summary-data-group.png)

Para crear una agrupación de dimensiones:

1. Seleccione una dimensión
1. Seleccione ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Grupo de datos de resumen]**.
1. Habilite **[!UICONTROL Crear agrupación]**.
1. Seleccione una dimensión del menú desplegable **[!UICONTROL Dimension]** que desee agrupar con la dimensión seleccionada desde el primer paso. Tenga en cuenta que solo las dimensiones que ya haya añadido a la vista de datos están disponibles en el menú desplegable.
1. De manera opcional, habilite **[!UICONTROL Ocultar en la creación de informes]** para ocultar la dimensión agrupada de la creación de informes. Habilitar esta opción es similar a configurar **[!UICONTROL Ocultar en la creación de informes]** en la dimensión agrupada por separado. Consulte [Configuración de componentes](overview.md) para obtener más información.
1. De manera opcional, para añadir dimensiones adicionales a la agrupación, seleccione ![Añadir](/help/assets/icons/Add.svg) **[!UICONTROL Añadir dimensión al grupo]**.<br/>Puede añadir hasta nueve dimensiones, ya que un grupo de datos de resumen tiene un límite de diez dimensiones.

## Misma configuración de componentes

Al agrupar dimensiones, debe asegurarse de que la configuración de [!UICONTROL Subcadena], [!UICONTROL Comportamiento (minúsculas)] e [!UICONTROL Incluir valores de exclusión], para cada una de las dimensiones que forman parte del grupo, sea la misma. De lo contrario, cada dimensión del grupo puede devolver potencialmente resultados diferentes antes de la agrupación.
Por ejemplo:

1. Ha creado un grupo de datos de resumen para `campaign_code` (parte de datos de resumen) y `tracking_code` (parte de datos de evento).
1. Ha aplicado [!UICONTROL Comportamiento (minúsculas)] a `campaign_code`, pero no a la dimensión `tracking_code`.

Los valores de `tracking_code` pueden mostrarse potencialmente como diferentes de `campaign_code`.

>[!IMPORTANT]
>
>Asegúrese de realizar la agrupación de dimensiones solo desde una dimensión y no aplique la agrupación desde varias dimensiones. Por ejemplo, si crea una agrupación añadiendo la dimensión `campaign_name` a la dimensión `tracking_code`, no cree también una agrupación para la dimensión `campaign_name`.
>
