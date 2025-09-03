---
title: Usar vinculación
description: Cómo usar la vinculación
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 4bca14492374939cd1ea6508c774720db61a6283
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 3%

---

# Usar vinculación

Puede habilitar la vinculación en uno o varios conjuntos de datos de evento que haya configurado como parte de la conexión. El número de conjuntos de datos de evento que puede habilitar para la vinculación viene determinado por el paquete de Customer Journey Analytics con licencia.

Puede habilitar la vinculación como parte de la [configuración del conjunto de datos](/help/connections/create-connection.md#dataset-settings) para un conjunto de datos de evento al [crear una conexión](/help/connections/create-connection.md) o al [editar una conexión](/help/connections/manage-connections.md#edit-a-connection).

Para habilitar la vinculación, en la sección del conjunto de datos de evento del cuadro de diálogo **[!UICONTROL Agregar conjuntos de datos]** o **[!UICONTROL Editar conjunto de datos]**:

![Opciones de vinculación de identidad al habilitar la vinculación de identidad](assets/identity-stitching-ui.png)

1. Seleccione **[!UICONTROL Habilitar vinculación de identidad]**.

   Si habilita la vinculación para un conjunto de datos de evento existente, el cuadro de diálogo **[!UICONTROL Cambiar ID de persona]** muestra las implicaciones de un cambio del ID de persona debido al uso de la vinculación. Seleccione **[!UICONTROL Continuar]** para continuar.

   El cuadro de diálogo **[!UICONTROL Habilitar vinculación de identidad]** resume las consecuencias de vincular identidades. Seleccione **[!UICONTROL Continuar]** para continuar.

1. Seleccione un ID persistente del menú desplegable **[!UICONTROL ID persistente]**.

   Si selecciona **[!UICONTROL mapa de identidad]** para el ID persistente, debe seleccionar un área de nombres Existen dos opciones:

   * Habilitar **[!UICONTROL Usar el área de nombres de identidad principal]** para usar el área de nombres de identidad principal.
   * Seleccione un área de nombres del menú desplegable **[!UICONTROL Área de nombres]**.

1. Seleccione un ID de persona en el menú desplegable **[!UICONTROL ID de persona]**.

   Si selecciona **[!UICONTROL mapa de identidad]** para el ID de persona, debe seleccionar un área de nombres. Existen dos opciones:

   * Habilitar **[!UICONTROL Usar el área de nombres de identidad principal]** para usar el área de nombres de identidad principal.
   * Seleccione un área de nombres del menú desplegable **[!UICONTROL Área de nombres]**.

   Si selecciona **[!UICONTROL Gráfico de identidad]** para el ID de persona, debe seleccionar un área de nombres. Antes de eso, se muestra el cuadro de diálogo **[!UICONTROL Cambiar al gráfico de identidad]** para asegurarse de que ha finalizado la configuración del gráfico de identidad antes de usar el gráfico de identidad para la vinculación. Seleccione **[!UICONTROL Continuar]** para continuar.

   * Seleccione un área de nombres del menú desplegable **[!UICONTROL Área de nombres]**.


1. Seleccione una ventana retrospectiva en el menú desplegable **[!UICONTROL Ventana retrospectiva]**. Las opciones son **[!UICONTROL 1 día]**, **[!UICONTROL 7 días]**, **[!UICONTROL 14 días]** o **[!UICONTROL 30 días]**.
