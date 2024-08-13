---
title: Configuración del componente de grupo de datos de resumen
description: Detalles y configuración de dimensiones de conjuntos de datos para garantizar que puede informar correctamente sobre los datos de resumen.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cba5904191b0602557903b5b9f32a2b793c8207d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# [!UICONTROL Configuración del componente del grupo de datos de resumen]

Un grupo de datos resumidos crea una asociación entre todas las dimensiones de la agrupación y se utiliza para combinar dimensiones de conjuntos de datos resumidos con otras dimensiones para la creación de informes.

![Configuración del componente de grupo de datos de resumen](/help/data-views/assets/summary-data-group.png)

Para crear una agrupación de dimensiones:

1. Seleccione una dimensión.
1. Seleccione ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL grupo de datos de resumen]**.
1. Habilitar **[!UICONTROL Crear agrupación]**.
1. Seleccione una dimensión de la lista desplegable **[!UICONTROL Dimension]** que desee agrupar con la dimensión seleccionada desde el primer paso. Tenga en cuenta que solo las dimensiones que ya haya agregado a la vista de datos están disponibles en la lista desplegable.
1. De manera opcional, habilite **[!UICONTROL Ocultar en creación de informes]** para ocultar la dimensión agrupada de la creación de informes. Habilitar esta opción es similar a configurar **[!UICONTROL Ocultar en informes]** en la dimensión agrupada por separado. Consulte [Configuración de componentes](overview.md) para obtener más información.
1. De manera opcional, para agregar dimensiones adicionales a la agrupación, seleccione ![Agregar](/help/assets/icons/Add.svg) **[!UICONTROL Agregar dimensión al grupo]**.<br/>Puede agregar hasta nueve dimensiones, ya que un grupo de datos de resumen tiene un límite de diez dimensiones.

## Misma configuración de componente

Al agrupar dimensiones, debe asegurarse de que la configuración de [!UICONTROL Subcadena], [!UICONTROL Comportamiento (minúsculas)] e [!UICONTROL Incluir valores de exclusión], para cada una de las dimensiones que forman parte del grupo, sea la misma. De lo contrario, cada dimensión del grupo puede devolver potencialmente resultados diferentes antes de la agrupación.
Por ejemplo:

1. Ha creado un grupo de datos de resumen para `campaign_code` (parte de datos de resumen) y `tracking_code` (parte de datos de evento).
1. Ha aplicado [!UICONTROL Comportamiento (minúsculas)] a `campaign_code`, pero no a la dimensión `tracking_code`.

Es posible que los valores de `tracking_code` se muestren como diferentes de `campaign_code`.

>[!IMPORTANT]
>
>Asegúrese de realizar la agrupación de dimensiones solo desde una dimensión y no aplique la agrupación desde varias dimensiones. Por ejemplo, si crea una agrupación agregando la dimensión `campaign_name` a la dimensión `tracking_code`, no cree también una agrupación para la dimensión `campaign_name`.
>


