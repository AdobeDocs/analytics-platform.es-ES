---
title: Integración de Adobe Journey Optimizer con Customer Journey Analytics
description: Incorpore datos generados por Adobe Journey Optimizer y analícelos usando Analysis Workspace dentro de Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 13c3f99dba7725553c775df4492803f759ebead5
workflow-type: tm+mt
source-wordcount: '1541'
ht-degree: 100%

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
   - Algunas de las métricas o dimensiones, que se han agregado automáticamente, se basan en campos derivados. Estos campos derivados se crean específicamente para esta integración. Por ejemplo, la métrica [!UICONTROL Clics en páginas de aterrizaje (AJO)] se basa en el campo derivado [!UICONTROL Clics en páginas de aterrizaje].
   - Algunas de las métricas o dimensiones tienen una configuración adicional. Por ejemplo, [!UICONTROL Queja de spam (AJO)] tiene la configuración [!UICONTROL Formato] e [!UICONTROL Incluir valores de exclusión] aplicada.
   - Todas las métricas y dimensiones agregadas automáticamente tienen una etiqueta de contexto llamada `:`*`name_of_metric_or_dimension`*. Por ejemplo, la métrica [!UICONTROL Clics en página de aterrizaje (AJO)] tiene la etiqueta de contexto `:Landing page clicks (AJO)`.

- En la pestaña **[!UICONTROL Configuración]**, no no se aplican valores de configuración específicos

>[!IMPORTANT]
>
>Modificar cualquiera de los valores configurados automáticamente para la conexión y la vista de datos no tiene consecuencias para la creación de informes de Journey Optimizer que dependen de y usan la integración de Customer Journey Analytics configurada automáticamente.


## Configurar manualmente una vista de datos para usarla con Journey Optimizer

En las secciones siguientes se describe cómo puede utilizar manualmente los datos generados por Journey Optimizer para realizar análisis avanzados en Customer Journey Analytics. Esto solo es necesario si la [opción de configuración automática](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) no es suficiente para sus necesidades.

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


### Configure la vista Datos para que se ajuste a las dimensiones y métricas de Journey Optimizer

Después de crear una conexión, puede crear una o más [Vistas de datos](/help/data-views/create-dataview.md) para configurar las dimensiones y métricas deseadas disponibles en Customer Journey Analytics.

>[!NOTE]
>
>Las discrepancias de datos entre Journey Optimizer y Customer Journey Analytics suelen ser inferiores al 1-2 %. Es posible que las discrepancias sean mayores cuando los datos se hayan recopilado en las dos últimas horas. Utilice intervalos de fechas que excluyan hoy para mitigar las discrepancias que implican tiempo de procesamiento.


#### Configuración de dimensiones en la vista de datos

Puede crear las dimensiones siguientes en una vista de datos para lograr una paridad aproximada con dimensiones similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de dimensiones.

| Dimensión | Elemento de esquema | Configuración de componentes |
| --- | --- | --- |
| Nombre del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: Dimensión |
| Nombre y versión del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo de componente: Dimensión |
| Nombre de nodo del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | Tipo de componente: Dimensión |
| Tipo de nodo del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Tipo de componente: Dimensión |
| Nombre de la campaña | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Tipo de componente: Dimensión |
| Canal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Tipo de componente: Dimensión |
| Título push | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Tipo de componente: Dimensión |
| Asunto del mensaje de correo electrónico | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Tipo de componente: Dimensión |
| Etiqueta de vínculo | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Tipo de componente: Dimensión |
| Nombre del experimento | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Tipo de componente: Dimensión<br>Etiquetas de contexto: Experimento de experimentación |
| Nombre del tratamiento | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Tipo de componente: Dimensión<br>Etiquetas de contexto: Variante de experimentación |
| Motivo del error de entrega del correo electrónico | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Tipo de componente: Dimensión |
| Motivo de exclusión de entrega del correo electrónico | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Tipo de componente: Dimensión |
| Etiqueta de elemento | `_experience.decisioning.propositionAction.label` | Tipo de componente: Dimensión |

{style="table-layout:auto"}

#### Configurar métricas en la vista de datos

Puede crear las métricas siguientes en una vista de datos para lograr una paridad aproximada con métricas similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de métricas.

| Métrica | Descripción | Elemento de esquema | Configuración de componentes |
| --- | --- | --- | --- |
| Rechazos | El número de mensajes que se rebotaron, incluidos los rechazos inmediatos y los rechazos después de la entrega. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir excluir valores: Si se cumplen algunos criterios<br>Igual a: `bounce`, Igual a: `denylist` |
| Devoluciones después de la entrega | Algunos servicios de correo electrónico informan de correos electrónicos entregados y luego los devuelven. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `async` |
| Clics en correos electrónicos | El recuento de clics dentro de los mensajes. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `click` |
| Aperturas de correo electrónico | El número de mensajes abiertos. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `open` |
| Errores | El número de mensajes erróneos. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `error` |
| Excluye | El número de mensajes excluidos. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `exclude` |
| Enviados | Número de mensajes aceptados por los proveedores de correo electrónico. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `sent` |
| Reclamaciones por correo no deseado | Recuento de quejas por correo no deseado. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `spam_complaint` |
| Cancelaciones de suscripción | El número de cancelaciones de suscripción. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `unsubscribe` |
| Envíos de Edge | Número de veces que la red perimetral envía un mensaje al SDK web o móvil | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.send` | |
| Pantallas entrantes | El número de veces que se muestra un mensaje web o de aplicación al usuario | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.display` | |
| Clics entrantes | Recuento de clics en mensajes web o en la aplicación | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.interact` | |
| Activadores en la aplicación | El número de veces que el motor de decisión sugirió que se mostrara el mensaje. El SDK móvil podría anular la decisión, reduciendo el número de pantallas reales. | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.trigger` | |
| Revocaciones en la aplicación | El número de veces que el SDK elimina un mensaje de aplicación de la IU | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### Configurar las métricas calculadas en Analysis Workspace

Una vez que haya configurado las dimensiones y métricas deseadas para el conjunto de datos de Journey Optimizer, también puede configurar [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obtener información adicional sobre esos datos. Estas métricas calculadas se basan en las métricas creadas anteriormente en el Administrador de vistas de datos.

| Métrica calculada | Descripción | Fórmula |
| --- | --- | --- |
| Mensajes enviados | El número total de mensajes enviados. Incluye mensajes enviados con éxito o fallidos. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Mensajes entregados | Número de correos electrónicos enviados a los clientes. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
