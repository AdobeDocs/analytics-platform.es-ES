---
title: Administrar configuración de perspectivas de conversación
description: Obtenga información sobre cómo administrar las configuraciones de Perspectivas de conversación.
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
autotag-review: '2026-10-02T07:03:36.851Z'
TQID: 'https://experienceleague.adobe.com/D2nrhtN2SaHoAw0PU7yJtabvx-q0L5FHtBFu1sORfaI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: d7a261eb-f9ac-4dd6-bd60-1637efcd3d36
    internal-label: ''
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: b58d1768aef87f01bb3c20b01102d08a17e973ef
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 6%
---
# Administrar configuraciones

Después de [crear configuraciones de Perspectivas de conversación](/help/conversation-insights/configure.md), puede ver, editar o eliminar estas configuraciones.

Solo los administradores del sistema pueden administrar las configuraciones de Perspectivas de conversación.

Para obtener información acerca de Perspectivas de conversación, vea [Información general sobre Perspectivas de conversación](/help/conversation-insights/overview.md).


## Ver y filtrar configuraciones existentes

Para ver las configuraciones existentes de Perspectivas de conversación:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Configuración de perspectivas de conversación]**.

   ![Información general sobre configuraciones de Conversation Insights](assets/conversation-insights-configurations.png)

   Las siguientes columnas de información están disponibles para cada configuración:

   * **[!UICONTROL Nombre]**: Nombre de la configuración de Perspectivas de conversación.
   * **[!UICONTROL Creado por]**: El usuario que creó la configuración.

   * **[!UICONTROL espacio aislado]**: El espacio aislado de Experience Platform que contiene el conjunto de datos de perfil que agregó a su conexión.

   * **[!UICONTROL Conexión]**: La conexión que agregó a su configuración.

   * **[!UICONTROL Fecha de creación]**: La fecha y hora en que se creó la configuración.

   * **[!UICONTROL Última modificación]**: Fecha en la que se modificó la configuración por última vez.

   * **[!UICONTROL Estado]**: El estado de la configuración. Entre los posibles valores están:
     ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Completo]**, ![StatusBlue](/help/assets/icons/StatusBlue.svg) **[!UICONTROL Pendiente]** o ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**.

   Para configurar qué columnas mostrar en la tabla, seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). En el cuadro de diálogo **[!UICONTROL Personalizar tabla]**, seleccione las columnas que desea mostrar. Luego selecciona **[!UICONTROL Aplicar]**.

1. (Opcional) Para filtrar la lista de configuraciones, seleccione ![Filtrar](/help/assets/icons/Filter.svg) y, a continuación, filtre por cualquiera de los siguientes criterios:

   * **[!UICONTROL Conexión]**

   * **[!UICONTROL Creado por]**

   * **[!UICONTROL Zona protegida]**

   * **[!UICONTROL Estado]**

## Crear una configuración

Para crear una nueva configuración de Perspectivas de conversación:

1. Seleccione **[!UICONTROL Crear configuración]**.
1. Use el cuadro de diálogo [**[!UICONTROL Crear configuración]**](./configure.md) para configurar las perspectivas de conversación.

## Editar una configuración

Para editar una configuración existente de Perspectivas de conversación:

1. Realice una de las siguientes acciones:

   * Seleccione el nombre de la configuración que desea editar.
   * Seleccione la casilla de verificación situada junto a la configuración que desee editar y, a continuación, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** en la barra de acciones azul.
   * Seleccione ![Más](/help/assets/icons/More.svg) para la configuración que desee editar. En el menú contextual, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.

1. Utilice el cuadro de diálogo [**[!UICONTROL Configuración / _nombre de la configuración_]**](./configure.md) para administrar las perspectivas de conversación.

## Eliminar una configuración

Para eliminar una configuración de Perspectivas de conversación existente:

1. Realice una de las siguientes acciones:

   * Seleccione la casilla de verificación situada junto a la configuración que desee eliminar y, a continuación, seleccione ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** en la barra de acciones azul.
   * Seleccione ![Más](/help/assets/icons/More.svg) para la configuración que desee editar. En el menú contextual, seleccione ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]**.

1. En el cuadro de diálogo **[!UICONTROL Eliminar configuración]**, seleccione **[!UICONTROL Eliminar]** para eliminar la configuración. Seleccione **[!UICONTROL Cancelar]** para cancelar.
