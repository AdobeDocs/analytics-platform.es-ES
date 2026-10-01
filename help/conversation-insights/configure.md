---
title: Crear O Editar Una Configuración De Perspectivas De Conversación
description: Obtenga información sobre cómo configurar las configuraciones de Perspectivas de conversación.
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 4a005c03e46547810de8d27fcf85a041ab59a4d6
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 15%
---
# Crear o editar configuraciones

Conversation Insights le permite analizar las conversaciones a partir de las experiencias de agente que ofrece a sus clientes. Estas experiencias del agente pueden basarse en modelos de lenguaje de gran tamaño (LLM) o en conversaciones humanas. Por ejemplo, un bot de chat que interactúa con un cliente o un centro de llamadas transcribe.
A través de Conversation Insights, puede comprender el impacto de los agentes en los resultados reales del usuario.

A través de la interfaz de configuración de Perspectivas de conversación puede crear o editar rápidamente una configuración y los artefactos asociados (conexión, vistas de datos, etc.).

Cuando crea o edita una configuración de Perspectivas de conversación, especifica la zona protegida y los conjuntos de datos de evento que contienen preguntas, respuestas y datos de comentarios. También puede seleccionar la conexión de Customer Journey Analytics a la que desea agregar estos conjuntos de datos. Y la vista de datos a la que desee agregar las métricas y dimensiones de Perspectivas de conversación.

Solo los administradores del sistema pueden crear o editar configuraciones de Perspectivas de conversación.

Puede crear o editar configuraciones desde la [interfaz de configuración de Perspectivas de conversación](./manage.md).

## Restaurar el conjunto de datos combinado que falta

Si edita una configuración y el conjunto de datos mezclado que se ha generado para la configuración ya no existe, seleccione **[!UICONTROL Restaurar]** para regenerar el conjunto de datos mezclado.


## Pasos de configuración

Para cada configuración:

1. En la sección **[!UICONTROL Detalles]**, especifique la siguiente información:

   ![Detalles de perspectivas de conversación](assets/conversation-insights-configuration-details.png)

   | Campo | Descripción |
   |---------|----------|
   | **[!UICONTROL Nombre]** | Especifique un nombre para la configuración. |
   | **[!UICONTROL Zona protegida]** | Seleccione el simulador para pruebas de Experience Platform que contiene los conjuntos de datos de mensajes, respuestas y eventos de comentarios que desea agregar a su conexión. |

1. En la sección **[!UICONTROL Conjuntos de datos]**, especifique la siguiente información:

   ![Conjuntos de datos de perspectivas de conversación](assets/conversation-insights-configuration-datasets.png)

   | Campo | Descripción |
   |---------|----------|
   | **[!UICONTROL Solicita el conjunto de datos de evento]** | Seleccione el conjunto de datos que contiene los datos de evento de mensajes. |
   | **[!UICONTROL Conjunto de datos de evento de respuestas]** | Seleccione el conjunto de datos que contiene los datos de evento de las respuestas. |
   | **[!UICONTROL Conjunto de datos de evento de comentarios]** | Seleccione el conjunto de datos que contiene los datos de evento de comentarios. |

1. En la sección **[!UICONTROL Conexión]**, si no hay ninguna conexión configurada, use **[!UICONTROL Seleccionar una conexión]** para seleccionar una conexión.

   ![Conexión de perspectivas de conversación](assets/conversation-insights-configuration-connection.png)

   Si ya se ha configurado una conexión, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para seleccionar otra conexión.

   ![Editar conexión de Perspectivas de conversación](assets/conversation-insights-configuration-edit-connection.png)

   En el diálogo **[!UICONTROL Seleccionar una conexión]**:

   ![Perspectivas de conversación selecciona la conexión](assets/conversation-insights-configuration-select-connection.png)

   1. Seleccione la casilla de verificación situada junto a la conexión a la que desea agregar los conjuntos de datos de mensajes, respuestas y eventos de comentarios.
   1. Seleccione **[!UICONTROL Usar conexión]**.

   * Para buscar en la lista de conexiones desde las que seleccionar, use el campo ![Buscar](/help/assets/icons/Search.svg).
   * Para configurar qué columnas mostrar en la tabla, seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). En el cuadro de diálogo **[!UICONTROL Personalizar tabla]**, seleccione las columnas que desea mostrar. Luego selecciona **[!UICONTROL Aplicar]**.

1. En la sección **[!UICONTROL Vistas de datos]**, si no hay ninguna vista de datos configurada, seleccione **[!UICONTROL Seleccionar vistas de datos]** para seleccionar vistas de datos.

   Si las vistas de datos ya están configuradas, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar selección de vista de datos]** para volver a configurar la selección de vistas de datos.

   En el diálogo **[!UICONTROL Seleccionar varias vistas de datos]**:

   ![Perspectivas de conversación: seleccione vistas de datos](assets/conversation-insights-configuration-select-data-views.png)

   1. Seleccione una o varias vistas de datos que desee utilizar para la configuración de Perspectivas de conversación.

   1. Seleccione **[!UICONTROL Usar vistas de datos]** para usar las vistas de datos. Seleccione Cancelar para cancelar.

   * Para buscar en la lista de vistas de datos entre las que seleccionar, use el campo ![Buscar](/help/assets/icons/Search.svg).
   * Para configurar qué columnas mostrar en la tabla, seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). En el cuadro de diálogo **[!UICONTROL Personalizar tabla]**, seleccione las columnas que desea mostrar. Luego selecciona **[!UICONTROL Aplicar]**.

1. Para finalizar la configuración:

   * Seleccione **[!UICONTROL Descartar]** para una nueva configuración que no se haya creado.

   * Seleccione **[!UICONTROL Guardar para más tarde]** para una nueva configuración que desee guardar pero para la que no desee crear el artefacto (por ejemplo, actualizaciones de vistas de datos). Puede volver a consultar la configuración más tarde y finalizar la creación real de la configuración.

   * Seleccione **[!UICONTROL Crear]** para crear la nueva configuración.

   * Seleccione **[!UICONTROL Guardar]** para guardar la configuración modificada.

   * Seleccione **[!UICONTROL Restaurar]** para restaurar la configuración y regenerar un nuevo conjunto de datos combinado para la configuración.

   * Seleccione **[!UICONTROL Exit]** para omitir cualquier cambio en la configuración.


## Verificación de vista de datos

Las vistas de datos que configuró en [Pasos de configuración](#configuration-steps) tienen **[!UICONTROL Perspectivas de conversación]** como valor para **[!UICONTROL Integraciones]** en [Vistas de datos](/help/data-views/manage-dataviews.md).

Para cada una de las vistas de datos configuradas:

* **Contenedores**: La [pestaña Contenedores](/help/data-views/create-dataview.md#containers) contiene un nuevo **[!UICONTROL Nombre de contenedor]**: **[!UICONTROL conversación]** con **[!UICONTROL Nombre para mostrar]**: **[!UICONTROL Contenedor]** como un **[!UICONTROL Sistema]** **[!UICONTROL Tipo de contenedor]** adicional.
* **Componentes**: verá carpetas de campo de esquema adicionales. Por ejemplo: agentExperience y conversación. Además, se añaden automáticamente los siguientes componentes:

  | Métricas | Tipo de datos del esquema | Ruta de esquema |
  |---|---|---|
  | Comentarios de clientes | Cadena | eventType |
  | Opiniones positivas | Cadena | Campos derivados |
  | Recomendaciones | Cadena | eventType |
  | Turnos | Cadena | eventType |

  | Dimensiones | Tipo de datos del esquema | Ruta de esquema |
  |---|---|---|
  | ID de agente | Cadena | `agenticExperience.agents.agentID` |
  | Nombre del agente | Cadena | `agenticExperience.agents.name` |
  | Nombre del conserje | Cadena | `agenticExperience.name` |
  | Versión del conserje | Cadena | `agenticExperience.version` |
  | ID de conversación | Cadena | `conversation.conversationID` |
  | Nombre de la conversación | Cadena | `conversation.conversationName` |
  | Nombre de la señal de conversación | Cadena | `conversation.signals.name` |
  | Valor booleano de resumen de conversación | Booleano | `conversation.signals.values.booleanValue` |
  | Confianza del resumen de conversación | Doble | `conversation.signals.values.confidence` |
  | Clave de metadatos de resumen de conversación | Cadena | `conversation.signals.values.metadata.key` |
  | Valor del número de resumen de conversación | Doble | `conversation.signals.values.numberValue` |
  | Cualificadores de resumen de conversación | Cadena | `conversation.signals.values.qualifiers` |
  | Señales de tono de conversación | Cadena | `conversation.signals.attributes.tones.values` |
  | Entorno | Cadena | `agenticExperience.environment` |
  | Clasificación de comentarios | Cadena | Campos derivados |
  | Clasificación de valoración de comentarios | Cadena | `conversation.feedback.rating.classification` |
  | Objetivo de la sección de comentarios | Cadena | `conversation.feedback.raw.purpose` |
  | Fuente de los comentarios | Cadena | `conversation.feedback.source` |
  | Frase | Cadena | `conversation.signals.attributes.subjects.values.phrase` |
  | Texto sin formato de respuesta | Cadena | `conversation.response.raw.text` |
  | Fuente de la respuesta | Cadena | `conversation.response.source` |
  | Clasificación de sentimientos | Cadena | Campos derivados |
  | Nombre de la habilidad | Cadena | `agenticExperience.agents.skills.name` |
  | Versión de habilidad | Cadena | `agenticExperience.agents.skills.version` |
  | Valor | Cadena | `agenticExperience.agents.skills.parameters.value` |


<!--

1. In the Data views dialog, select the checkbox next to one or more data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting.

1. Select **[!UICONTROL Use data views]**.

1. Select **[!UICONTROL Create]** to create the configuration.

   >[!IMPORTANT]
   >
   >Because the profile dataset is updated once per day, audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration.


1. After 24 hours, [view audience dimensions in the data view](#view-audience-dimensions-in-the-data-view) to verify that the audience dimensions are available in the data views that you selected. 


 
## View audience dimensions in the data view

After you [create an audience analysis configuration](#create-an-audience-analysis-configuration), you can verify that audience dimensions were added to the data views that you selected during the configuration.

To view audience dimensions in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the audience analysis dimensions in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Audience Name]**

   * **[!UICONTROL Audience Origin]**

   * **[!UICONTROL Exited Audience Origin]**

   * **[!UICONTROL Exited Audience Name]**

   Note that each of these dimensions was added to the profile dataset that is associated with the merge policy that you selected during the audience analysis configuration, and each was added to the new lookup dataset that was created.

   ![Audience dimensions available in the data view](assets/audience-analysis-dataview-dataset.png)

1. Use the audience analysis dimensions in Analysis Workspace. 

   Users who have access to use the data view in Analysis Workspace can now see the new dimensions and use them in their analyses. For information about how to use the audience analysis dimensions in Analysis Workspace, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

-->