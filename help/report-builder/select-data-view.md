---
title: Selección De Una Vista De Datos En Report Builder
description: Obtenga información sobre cómo seleccionar una vista de datos en Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
TQID: https://experienceleague.adobe.com/auDJxQ6x6fqNVbDuN9reSffP9iUISZ7QgEflGWApc8A
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 1%

---

# Seleccione una vista de datos

Puede seleccionar una vista de datos del menú desplegable o seleccionar una vista de datos de una celda y actualizar automáticamente el bloque de datos con una nueva vista de datos.

## Seleccionar vista de datos de una celda

Al seleccionar una vista de datos de una celda, es más fácil actualizar los bloques de datos con distintas vistas de datos. En lugar de crear informes completamente nuevos con bloques de datos independientes, puede actualizar los bloques de datos con una vista de datos seleccionada de una celda.

Seleccionar una vista de datos de una celda es útil cuando tiene lo siguiente:

* Varias vistas de datos que son similares o idénticas entre sí en estructura.
* Formatos de bloque de datos complicados que incluyen componentes y diseños personalizados.

Para seleccionar una vista de datos de una celda, primero genere un bloque de datos y asigne varias vistas de datos a una celda fuera del bloque de datos. A continuación, utilice la vista de datos **[!UICONTROL de la celda]** para actualizar los bloques de datos de diferentes vistas de datos.

1. Cree un bloque de datos. Para obtener información sobre cómo crear un bloque de datos, consulte [Crear un bloque de datos](/help/report-builder/create-a-data-block.md).

1. Seleccione ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) en **[!UICONTROL Vistas de datos]**.

1. Seleccione una celda con ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) fuera del bloque de datos.

1. Agregue una o más vistas de datos de **[!UICONTROL Seleccione las vistas de datos que desee agregar a la vista de datos de la celda]** arrastrando y soltando. También puede seleccionar una vista de datos para agregarla a la lista **[!UICONTROL Vistas de datos incluidas]**.

   * Puede usar ![Buscar](/help/assets/icons/Search.svg) **[!UICONTROL _Seleccionar vistas de datos_]** para buscar vistas de datos.
   * Use ![MoreSmall](/help/assets/icons/MoreSmall.svg) para abrir un menú contextual y poder mover las vistas de datos hacia arriba o hacia abajo en la lista **[!UICONTROL Vistas de datos incluidas]**.
   * Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) para eliminar una vista de datos de la lista **[!UICONTROL Vistas de datos incluidas]**.

   ![Seleccionar vista de datos de una celda](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Aplicar]** para aplicar las vistas de datos seleccionadas a la celda seleccionada.


## Cambiar la vista de datos de una celda

1. Seleccione la ubicación de la celda de vista de datos en la hoja.
1. En Report Builder Hub, seleccione el vínculo **[!UICONTROL Vistas de datos de la celda]** en **[!UICONTROL Edición rápida]**.
1. Seleccione una vista de datos del menú desplegable **[!UICONTROL Vista de datos]**.

   ![Cambiar vista de datos de una celda](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Opcional, seleccionar **[!UICONTROL Actualizar bloque(s) de datos al cambiar]**.

1. Seleccione **[!UICONTROL Aplicar]**. Report Builder actualiza el bloque de datos en función de la vista de datos seleccionada.
