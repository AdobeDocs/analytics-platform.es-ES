---
title: Integración de Adobe Journey Optimizer con Customer Journey Analytics
description: Incorpore datos generados por Adobe Journey Optimizer y analícelos usando Analysis Workspace dentro de Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: eda523204ec40a5660621cfd9e96ba77b61aa22c
workflow-type: tm+mt
source-wordcount: '3036'
ht-degree: 69%

---

# Integración de Journey Optimizer con Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/get-started/get-started) le ayuda a ofrecer experiencias conectadas, contextualizadas y personalizadas. Esto ayuda a exponer a los clientes al siguiente paso de su recorrido del cliente.

Puede configurar los datos generados por Journey Optimizer para realizar análisis avanzados en Customer Journey Analytics. Puede configurar esta integración automáticamente. Si es necesario, puede realizar personalizaciones adicionales y manuales de los conjuntos de datos, dimensiones o métricas disponibles en la conexión o en las vistas de datos.

## Configuración automática de la integración con Journey Optimizer

{{release-limited-testing-section}}

Journey Optimizer admite el uso de Customer Journey Analytics como motor de creación de informes. Consulte [Introducción a la nueva interfaz de creación de informes](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channel-report/report-gs-cja) en la documentación de Journey Optimizer.

Cuando haya habilitado la creación de informes de Customer Journey Analytics para Journey Optimizer, se crean automáticamente una [conexión](/help/connections/overview.md) y [vista de datos](/help/data-views/data-views.md) para la zona protegida específica.

### Conexión

La conexión tiene el nombre **[!UICONTROL Conexión habilitada de AJO (*nombre de zona protegida*)]** y tiene los siguientes valores predeterminados para la configuración y los conjuntos de datos:

| **Configuración de la conexión** | Valor |
|---|---| 
| [!UICONTROL Nombre de la conexión] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Descripción de la conexión] | [!UICONTROL *Describa su conexión aquí*] |
| [!UICONTROL Etiquetas] | [!UICONTROL *Seleccionar etiquetas*] |


| **Configuración de datos** | Valor |
|---|---| 
| [!UICONTROL Activar la ventana de datos móviles] | Habilitado. [!UICONTROL Número de meses seleccionado] `13`. |
| [!UICONTROL Zona protegida] | [!UICONTROL *nombre de la zona protegida*] (deshabilitado; no se puede modificar esta configuración). |
| [!UICONTROL Cantidad promedio de eventos diarios] | menos de 1 millón (deshabilitado; no se puede modificar esta configuración). |


| Nombre del conjunto de datos | Esquema | Tipo de conjunto de datos | Tipo de fuente de datos | Identificación de la persona | Clave | Clave de coincidencia | Importar datos nuevos | Datos de relleno |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL Conjunto de datos de entidad de AJO] | [!UICONTROL Esquema de registro de entidad de AJO] | [!UICONTROL Búsqueda] | [!UICONTROL Otro] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Estado verde](assets/../../connections/assets/status-green.svg) Activado | ![Estado gris](assets/../../connections/assets/status-gray.svg) Desactivado |
| [!UICONTROL Eventos de paso de recorrido] | [!UICONTROL Esquema de evento de paso de recorrido para Journey Orchestration] | [!UICONTROL Evento] | [!UICONTROL Otro] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![Estado verde](assets/../../connections/assets/status-green.svg) Activado | ![Estado gris](assets/../../connections/assets/status-gray.svg) Desactivado |
| [!UICONTROL Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO] | [!UICONTROL Esquema de evento de experiencia de seguimiento de correo electrónico AJO] | [!UICONTROL Evento] | [!UICONTROL Otro] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Estado verde](assets/../../connections/assets/status-green.svg) Activado | ![Estado gris](assets/../../connections/assets/status-gray.svg) Desactivado |
| [!UICONTROL Conjunto de datos de evento de comentarios de mensajes AJO] | [!UICONTROL Esquema de evento de comentarios de mensajes AJO] | [!UICONTROL Evento] | [!UICONTROL Otro] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Estado verde](assets/../../connections/assets/status-green.svg) Activado | ![Estado gris](assets/../../connections/assets/status-gray.svg) Desactivado |
| [!UICONTROL Conjunto de datos de evento de experiencia de seguimiento push AJO] | [!UICONTROL Esquema de evento de experiencia de seguimiento push AJO] | [!UICONTROL Evento] | [!UICONTROL Otro] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Estado verde](assets/../../connections/assets/status-green.svg) Activado | ![Estado gris](assets/../../connections/assets/status-gray.svg) Desactivado |


### Vista de datos

La vista de datos tiene el nombre **Habilitar vista de datos AJO (*nombre de zona protegida*)**.

- En la pestaña **[!UICONTROL Configurar]**, los siguientes valores están configurados de forma predeterminada.

  | Configuración | Valor |
  |---|---|
  | [!UICONTROL Conexión] | Conexión habilitada de AJO (*nombre de zona protegida*) |
  | [!UICONTROL Nombre] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL ID externo] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (derivado del nombre) |
  | [!UICONTROL Descripción] | `undefined` |

  {style="table-layout:fixed"}

  | Compatibilidad | Valor |
  |---|---|
  | [!UICONTROL Establecer como vista de datos predeterminada en Adobe Journey Optimizer] | Habilitado (predeterminado).<br/><br/>Esta opción de configuración le permite designar una vista de datos para utilizarla con Journey Optimizer, sin necesidad de realizar una configuración manual. Para obtener información sobre cómo activar esta opción de configuración (si no está activada de forma predeterminada), consulte la sección [Compatibilidad](/help/data-views/create-dataview.md#compatibility) en [Creación o edición de una vista de datos](/help/data-views/create-dataview.md). <br/><br/>Cuando deshabilita la opción, un cuadro de diálogo le preguntará si desea continuar cambiando la vista de datos predeterminada. Al seleccionar **[!UICONTROL Continuar]**, debe seleccionar otra vista de datos como vista de datos predeterminada. Seleccionar **[!UICONTROL Confirmar]** para confirmar la selección. Seleccionar **[!UICONTROL Cancelar]** para cancelar el cambio de la vista de datos predeterminada. |

  | Contenedores | Valor |
  |---|---|
  | [!UICONTROL Nombre de contenedor de persona] | `Person` |
  | [!UICONTROL Nombre de contenedor de sesión] | `Session` |
  | [!UICONTROL Nombre de contenedor de evento] | `Event` |

  | Calendario | Valor |
  |---|---|
  | [!UICONTROL Zona horaria] | Zona horaria conforme a su ubicación |
  | [!UICONTROL Tipo de calendario] | Gregoriano |
  | [!UICONTROL Primer mes del año] | Enero |
  | [!UICONTROL Primer día de la semana] | Domingo |


- En la pestaña **Componentes**:
   - Todas las métricas y dimensiones que tienen [!UICONTROL (AJO)] anexados a su nombre se añaden automáticamente como parte de esta configuración automática.
   - Algunas de las métricas o dimensiones que se han agregado automáticamente se basan en campos derivados. Estos campos derivados se crean específicamente para esta integración. Por ejemplo, la métrica [!UICONTROL Clics en páginas de aterrizaje (AJO)] se basa en el campo derivado [!UICONTROL Clics en páginas de aterrizaje].
   - Algunas de las métricas o dimensiones tienen una configuración adicional. Por ejemplo, [!UICONTROL Queja de spam (AJO)] tiene la configuración [!UICONTROL Formato] e [!UICONTROL Incluir valores de exclusión] aplicada.
   - Todas las métricas y dimensiones agregadas automáticamente tienen una etiqueta de contexto llamada `:`*`name_of_metric_or_dimension`*. Por ejemplo, la métrica [!UICONTROL Clics en página de aterrizaje (AJO)] tiene la etiqueta de contexto `:Landing page clicks (AJO)`.

- En la pestaña **[!UICONTROL Configuración]**, no no se aplican valores de configuración específicos

>[!IMPORTANT]
>
>Modificar cualquiera de los valores configurados automáticamente para la conexión y la vista de datos no tiene consecuencias para la creación de informes de Journey Optimizer que dependen de y usan la integración de Customer Journey Analytics configurada automáticamente.


## Configurar manualmente una vista de datos para usarla con Journey Optimizer

En las secciones siguientes se describe cómo puede utilizar manualmente los datos generados por Journey Optimizer para realizar análisis avanzados en Customer Journey Analytics. Esta configuración manual solamente es necesaria si la [opción de configuración automática](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) no es suficiente para sus necesidades.

### Envío de datos de Journey Optimizer a Adobe Experience Platform

Adobe Experience Platform sirve como fuente de datos central y vínculo entre Journey Optimizer y Customer Journey Analytics. Consulte [Introducción a los conjuntos de datos](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) en la guía del usuario de Journey Optimizer para ver los pasos sobre cómo enviar datos de Journey Optimizer a Experience Platform como un conjunto de datos.

### Crear una conexión en Customer Journey Analytics

Una vez que los datos de Journey Optimizer están en Adobe Experience Platform, puede [Crear una conexión](/help/connections/create-connection.md) en función de su conjunto de datos de Journey Optimizer. O puede agregar conjuntos de datos de Journey Optimizer a una conexión existente.

Seleccione y configure los siguientes conjuntos de datos:

| Conjunto de datos | Tipo de conjunto de datos | Configuración de la conexión | Descripción |
| --- | --- | --- | --- |
| Conjunto de datos de evento de comentarios de mensajes AJO | Evento | ID de la persona: `IdentityMap` | Contiene eventos de envío de mensajes, como “[!UICONTROL Envíos]” y “[!UICONTROL Devoluciones]”. |
| Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | Evento | ID de persona: `IdentityMap` | Contiene eventos de seguimiento de correo electrónico como “[!UICONTROL Aperturas]”, “[!UICONTROL Clics]” y “[!UICONTROL Cancela la suscripción]”. |
| Conjunto de datos de evento de experiencia de seguimiento push AJO | Evento | ID de persona: `IdentityMap` | Contiene eventos de seguimiento push como “[!UICONTROL Lanzamientos de aplicaciones]”. |
| Eventos de paso de recorrido | Evento | ID de persona: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contiene eventos que muestran qué perfiles participaron en cada nodo del recorrido. |
| Conjunto de datos de entidad de AJO | Búsqueda | Clave: `_id`<br>Clave de coincidencia: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene clasificaciones que asocian metadatos de Recorridos y Campañas a todos los datos de eventos de Journey Optimizer. |

{style="table-layout:auto"}


### Configuración de la vista de datos

Después de crear una conexión, puede crear una o más [Vistas de datos](/help/data-views/create-dataview.md) para configurar las dimensiones y métricas deseadas disponibles en Customer Journey Analytics.

>[!NOTE]
>
>Las discrepancias de datos entre Journey Optimizer y Customer Journey Analytics suelen ser inferiores al 1-2 %. Es posible que las discrepancias sean mayores cuando los datos se hayan recopilado en las dos últimas horas. Utilice intervalos de fechas que excluyan hoy para mitigar las discrepancias que implican tiempo de procesamiento.


#### Configuración de dimensiones

Puede crear las dimensiones siguientes en una vista de datos para lograr una paridad aproximada con dimensiones similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de dimensiones.

| Dimensión | Descripción | Conjunto(s) de datos | Elemento de esquema | Configuración de componentes |
| --- | --- | --- | --- | --- |
| Error de ejecución de la acción (AJO) | Condición de error que impidió que Journey Runtime ejecutase la acción. | Eventos de paso de recorrido | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | Tipo de componente: Dimensión |
| Etiqueta de acción (AJO) | El nombre para mostrar generado por el cliente del elemento con el que interactuó el usuario final. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.`<br/>`propositionAction.label` | Tipo de componente: Dimensión |
| ID de lote (AJO) | GUID creado al invocar cada nueva instancia de lote para un Recorrido programado o una acción de campaña. Por ejemplo, si un Recorrido programado o una acción de campaña se ejecuta a las 8:00 y a las 10:00, hay dos batchInstanceID distintos. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | Tipo de componente: Dimensión |
| Marca de tiempo de instancia de lote (AJO) | Marca de tiempo de la instancia de lote. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| ID de campaña (AJO) | El ID de la campaña. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | Tipo de componente: Dimensión |
| Nombre de la campaña (AJO) | El nombre de la campaña. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | Tipo de componente: Dimensión |
| ID de versión de la campaña (AJO) | El ID de versión de la campaña. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | Tipo de componente: Dimensión |
| Canal (AJO) | El canal con el que deben correlacionarse estos datos. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | Tipo de componente: Dimensión |
| ID de correlación (AJO) | El ID de correlación | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | Tipo de componente: Dimensión |
| ID de directiva de decisión (AJO) | El ID de la política de decisión utilizada a la hora de decidir qué elementos incluir en esta proposición. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| Dominio del destinatario del correo electrónico (AJO) | Dominio de la dirección de correo electrónico | Conjunto de datos de evento de experiencia de seguimiento push de AJO, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | Tipo de componente: Dimensión |
| Asunto de correo electrónico (AJO) | Asunto de correo electrónico, no personalizado | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | Tipo de componente: Dimensión |
| ID de evento (AJO) | Un identificador único para el evento de la serie temporal. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_id` | Tipo de componente: Dimension (campo derivado) |
| ID de criterios de salida (AJO) | El ID de los criterios de salida utilizados para determinar si el recorrido debe salir. | Eventos de paso de recorrido | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | Tipo de componente: Dimensión |
| Nombre de los criterios de salida (AJO) | Nombre de los criterios de salida. | Eventos de paso de recorrido | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | Tipo de componente: Dimensión |
| ID de experimento (AJO) | El ID del experimento. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Tipo de componente: Dimensión |
| Nombre del experimento (AJO) | El nombre del experimento. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | Tipo de componente: Etiquetas de contexto de Dimension: Experimento de experimentación |
| Error de búsqueda (AJO) | Condición de error que impidió que Journey Runtime ejecutase la búsqueda. | Eventos de paso de recorrido | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | Tipo de componente: Dimensión |
| El tiempo de envío está optimizado (AJO) | Está la ejecución del mensaje SendTimeOptimized | Conjunto de datos de evento de experiencia de seguimiento push de AJO, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | Tipo de componente: Dimensión |
| Es un recorrido de prueba (AJO) | ¿El evento forma parte de la ejecución de un recorrido de prueba? | Eventos de paso de recorrido | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | Tipo de componente: Dimensión |
| Es un mensaje de prueba (AJO) | Es un mensaje enviado como ejecución de prueba | Conjunto de datos de evento de experiencia de seguimiento push de AJO, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | Tipo de componente: Dimensión |
| ID de elemento (AJO) | El ID del elemento. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.`<br/>`propositions.items.id` | Tipo de componente: Dimensión |
| Nombre del elemento (AJO) | El nombre del elemento | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.`<br/>`propositions.items.name` | Tipo de componente: Dimensión |
| ID de acción de recorrido | ID de acción de recorrido, para el que se activa MessageExecution. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | Tipo de componente: Dimensión |
| Nombre del nodo de acción del recorrido (AJO) | El nombre del nodo de acción del recorrido. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO, conjunto de datos de entidad de AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| Nombre del nodo del evento de recorrido (AJO) | Este valor se establece cada vez que se produce un segmento o un evento externo en un recorrido. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO, conjunto de datos de entidad de AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| ID de recorrido (AJO) | El ID del recorrido. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | Tipo de componente: Dimensión |
| Nombre del recorrido (AJO) | El nombre del recorrido. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | Tipo de componente: Dimensión |
| Nombre y versión del recorrido (AJO) | El nombre y la versión del recorrido. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | Tipo de componente: Dimensión |
| ID de versión de recorrido (AJO) | El ID de versión del recorrido. | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | Tipo de componente: Dimensión |
| ID de la página de aterrizaje (AJO) | Identificador único de la página de aterrizaje. | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | Tipo de componente: Dimensión |
| Fuente de las páginas de aterrizaje (AJO) | La fuente de la página de aterrizaje. | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| URL del vínculo (AJO) | La URL en la que el usuario hizo clic. | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | Tipo de componente: Dimensión |

{style="table-layout:auto"}

#### Configurar métricas en la vista de datos

Puede crear las métricas siguientes en una vista de datos para lograr una paridad aproximada con métricas similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de métricas.

| Métrica | Descripción | Conjunto(s) de datos | Elemento de esquema | Configuración de componentes |
| --- | --- | --- | --- | --- |
| Instalaciones de la aplicación (AJO) | Número de instalaciones de la aplicación | Conjunto de datos de evento de experiencia de seguimiento push AJO | `application.installs.value` | Tipo de componente: Métrica |
| Lanzamientos de la aplicación (AJO) | Número de veces que se lanza la aplicación móvil | Conjunto de datos de evento de experiencia de seguimiento push AJO | `application.launches.value` | Tipo de componente: Métrica |
| Rechazos para canales salientes (AJO) | Recuento total de mensajes rechazados en los canales salientes | Conjunto de datos de evento de comentarios de mensajes AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica |
| Clics (AJO) | Recuento total de clics en todos los canales | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO, conjunto de datos de evento de comentarios de mensajes de AJO | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Recuento de ofertas de reserva (AJO) | Recuento de ofertas de reserva. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | Tipo de componente: Métrica |
| Recuento de ofertas (AJO) | Recuento de ofertas. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | ` _experience.decisioning.`<br/>`propositions.items.id` | Tipo de componente: Métrica |
| Métrica Dedup (AJO) | Métrica Dedup | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_id` | Tipo de componente: Métrica |
| Entregado (AJO) | Recuento total de mensajes entregados. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Descartado (AJO) | Cuenta cada vez que el SDK de Adobe cierra el mensaje en la aplicación, independientemente de la acción que el usuario final elija para cerrarlo. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Tipo de componente: Métrica |
| Visualizaciones (AJO) | Este recuento muestra los mensajes AJO. Esto incluye aperturas de correo electrónico, visualizaciones web y visualizaciones en la aplicación. Las plataformas móviles no informan de las visualizaciones de mensajes SMS y push, por lo que no se contabilizan. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO, conjunto de datos de evento de comentarios de mensajes de AJO | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Aperturas de correos electrónicos (AJO) | Recuento total de correos abiertos | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: Métrica |
| Clics entrantes (AJO) | Recuento total de clics en los canales entrantes | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo de componente: Métrica |
| Descartes entrantes (AJO) | Recuento total de rechazos en los canales entrantes | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Tipo de componente: Métrica |
| Impresiones entrantes (AJO) | Recuento del total de impresiones en los canales entrantes | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: Métrica |
| Fin del recorrido (AJO) | True si el paso actual llevó a finalizar una instancia del recorrido. Que el último paso de un recorrido para un perfil determinado se ejecutó correctamente. | Eventos de paso de recorrido | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Tipo de componente: Métrica |
| Entradas del recorrido (AJO) | Verdadero si el evento de paso era un evento de entrada de un recorrido correspondiente a un perfil. | Eventos de paso de recorrido | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Salidas del recorrido (AJO) | True si el paso actual llevó a finalizar una instancia del recorrido. Este es el último paso de un recorrido en el que un perfil determinado se ejecutó correctamente. | Eventos de paso de recorrido | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Tipo de componente: Métrica |
| Errores del recorrido (AJO) | Proporciona el estado actual del paso que ha terminado de ejecutarse. Valores posibles: `Transitions` (el siguiente paso se producirá en una transición de eventos), `EndStep` (se ha ejecutado el último paso de esta instancia de recorrido), `Error` (este paso encontró una condición de error, finalizando la instancia de recorrido actual), `TimedOut` (el paso actual ha finalizado debido a un tiempo de espera agotado al recuperar o en una acción). | Eventos de paso de recorrido | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | Tipo de componente: Métrica |
| Clics en la página de aterrizaje (AJO) | Recuento total de clics en la página de aterrizaje. | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Conversiones de páginas de aterrizaje (AJO) | Recuento total de conversiones en la página de aterrizaje. | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: Métrica |
| Vistas de página de aterrizaje (AJO) | Recuento total de vistas en la página de aterrizaje. | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: Métrica |
| Entradas del nodo (AJO) | Verdadero si el evento de paso era un evento de entrada de un nodo correspondiente a un perfil. | Eventos de paso de recorrido | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Clics de salida (AJO) | Recuento total de clics en los canales salientes | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: Métrica |
| Errores salientes (AJO) | Recuento del total de mensajes con errores en los canales salientes | Conjunto de datos de evento de comentarios de mensajes AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica |
| Exclusiones salientes (AJO) | Recuento del total de eventos de exclusión en los canales salientes | Conjunto de datos de evento de comentarios de mensajes AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica |
| Envíos salientes (AJO) | Recuento total de mensajes enviados a través de los canales salientes | Conjunto de datos de evento de comentarios de mensajes AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica |
| Acciones personalizadas push (AJO) | Recuento del total de acciones personalizadas en la interacción push. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `eventType` | Tipo de componente: Métrica |
| Interacciones push (AJO) | Número de veces que se inicia la aplicación móvil debido a una interacción directa con un mensaje push | Conjunto de datos de evento de experiencia de seguimiento push AJO | `application.launches.value` | Tipo de componente: Métrica |
| Envíos (AJO) | Recuento del total de mensajes enviados a través de todos los canales | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Mensajes entrantes SMS (AJO) | Respuesta de entrada de SMS. Por ejemplo, detener, iniciar, suscribirse, etc. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | Tipo de componente: Métrica |
| Denuncia de spam (AJO) | Recuento total de reclamaciones por spam | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: Métrica |
| Adiciones a la lista de suscripción (AJO) | Recuento total de adiciones a la lista de suscripción. | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Eliminaciones de la lista de suscripción (AJO) | Recuento total de eliminaciones de la lista de suscripción. | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Segmentado (AJO) | Hace un recuento del número de veces que una propuesta se ha dirigido a una persona. Es el número de veces que se ha considerado una propuesta para mostrarla a una persona. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | Campos derivados | Tipo de componente: Métrica (campo derivado) |
| Activado (AJO) | El SDK de Adobe eligió mostrar la propuesta. Otros factores pueden impedir que se muestre realmente. | Conjunto de datos de evento de experiencia de seguimiento push de AJO, eventos de paso de Recorrido, conjunto de datos de evento de comentarios de mensajes de AJO, conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: Métrica |
| Visitantes únicos del experimento (AJO) | Los visitantes únicos del experimento | Conjunto de datos de entidad de AJO | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Tipo de componente: Métrica |
| Bajas (AJO) | Recuento del total de bajas | Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: Métrica |

{style="table-layout:auto"}
