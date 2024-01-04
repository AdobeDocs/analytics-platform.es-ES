---
title: Integración de Adobe Journey Optimizer con Customer Journey Analytics
description: Incorpore datos generados por Adobe Journey Optimizer y analícelos con Analysis Workspace en Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 64%

---

# Integración de Adobe Journey Optimizer con Adobe Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=es) le ayuda a ofrecer experiencias conectadas, contextualizadas y personalizadas. Esto ayuda a exponer a los clientes al siguiente paso de su recorrido del cliente.

Puede importar los datos generados por Journey Optimizer para realizar análisis avanzados en Customer Journey Analytics al realizar los siguientes pasos:

## Envío de datos de Journey Optimizer a Adobe Experience Platform

Adobe Experience Platform sirve como fuente de datos central y vínculo entre Journey Optimizer y Customer Journey Analytics. Consulte [Introducción a los conjuntos de datos](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=es) en la guía del usuario de Journey Optimizer para ver los pasos sobre cómo enviar datos de Journey Optimizer a Platform como un conjunto de datos.

## Crear una conexión en Customer Journey Analytics

Una vez que los datos de Journey Optimizer estén en Adobe Experience Platform, puede [Crear una conexión](/help/connections/create-connection.md) en función de sus conjuntos de datos de Journey Optimizer. O puede agregar conjuntos de datos de Journey Optimizer a una conexión existente.

Seleccione y configure los siguientes conjuntos de datos:

| Conjunto de datos | Tipo de conjunto de datos | Configuración de la conexión | Descripción |
| --- | --- | --- | --- |
| Conjunto de datos de evento de comentarios de mensajes AJO | Evento | ID de persona: `IdentityMap` | Contiene eventos de envío de mensajes, como &#39;[!UICONTROL Envíos]&#39; y &#39;[!UICONTROL Devoluciones]&#39;. |
| Conjunto de datos de evento de experiencia de seguimiento de correo electrónico AJO | Evento | ID de persona: `IdentityMap` | Contiene eventos de seguimiento de correo electrónico como &#39;[!UICONTROL Aperturas]&#39;, &#39;[!UICONTROL Clics]&#39;, y &#39;[!UICONTROL Cancela la suscripción]&#39;. |
| Conjunto de datos de evento de experiencia de seguimiento push AJO | Evento | ID de persona: `IdentityMap` | Contiene eventos de seguimiento push como &#39;[!UICONTROL Lanzamientos de aplicaciones]&#39;. |
| Eventos de paso de recorrido | Evento | ID de persona: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contiene eventos que muestran qué perfiles participaron en cada nodo del recorrido. |
| Conjunto de datos de entidad AJO | Búsqueda | Clave: `_id`<br>Clave de coincidencia: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene clasificaciones que asocian metadatos de Recorridos y campañas a todos los datos de eventos de Adobe Journey Optimizer. |

{style="table-layout:auto"}


## Configure la vista Datos para que se ajuste a las dimensiones y métricas de Journey Optimizer

Después de crear una conexión, puede crear una o más [Vistas de datos](/help/data-views/create-dataview.md) para configurar las dimensiones y métricas deseadas disponibles en Customer Journey Analytics.

>[!NOTE]
>
>Las discrepancias de datos entre Adobe Journey Optimizer y Customer Journey Analytics suelen ser inferiores al 1-2 %. Es posible que las discrepancias sean mayores cuando los datos se hayan recopilado en las dos últimas horas. Utilice intervalos de fechas que excluyan hoy para mitigar las discrepancias que implican tiempo de procesamiento.


### Configuración de dimensiones en la vista de datos

Puede crear las dimensiones siguientes en una vista de datos para lograr una paridad aproximada con dimensiones similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de dimensiones.

| Dimensión | Elemento de esquema | Configuración de componentes |
| --- | --- | --- |
| Nombre del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: Dimensión |
| Nombre y versión del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo de componente: Dimensión |
| Nombre de nodo del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: Dimensión |
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

### Configurar métricas en la vista de datos

Puede crear las métricas siguientes en una vista de datos para lograr una paridad aproximada con métricas similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de métricas.

| Métrica | Descripción | Elemento de esquema | Configuración de componentes |
| --- | --- | --- | --- |
| Devoluciones | El número de mensajes que se rebotaron, incluidos los rechazos inmediatos y los rechazos después de la entrega. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir excluir valores: Si se cumplen algunos criterios<br>Igual a: `bounce`, Igual a: `denylist` |
| Devoluciones después de la entrega | Algunos servicios de correo electrónico informan de correos electrónicos entregados y luego los devuelven. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `async` |
| Clics en correos electrónicos | El recuento de clics dentro de los mensajes. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `click` |
| Aperturas de correo electrónico | El número de mensajes abiertos. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `open` |
| Errores | El número de mensajes erróneos. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `error` |
| Excluye | El número de mensajes excluidos. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `exclude` |
| Enviados | Número de mensajes aceptados por los proveedores de correo electrónico. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `sent` |
| Reclamaciones por correo no deseado | Recuento de quejas por correo no deseado. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `spam_complaint` |
| Cancelación de suscripción | El número de bajas. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir excluir valores: Igual a `unsubscribe` |
| Edge Sends | Número de veces que la red perimetral envía un mensaje al SDK web o móvil | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.send` |
| Pantallas entrantes | El número de veces que se muestra un mensaje web o de aplicación al usuario | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.display` |
| Clics entrantes | Recuento de clics en mensajes web o en la aplicación | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.interact` |
| Déclencheur en la aplicación | El número de veces que el motor de decisión sugirió que se mostrara el mensaje. El SDK móvil podría anular la decisión de reducir el número de pantallas reales. | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.trigger` |
| Revocaciones en la aplicación | El número de veces que el SDK elimina un mensaje de aplicación de la interfaz de usuario | Usar el elemento de cadena de esquema `_experience.decisioning.propositionEventType.dismiss` |

{style="table-layout:auto"}

### Configurar las métricas calculadas en Analysis Workspace

Una vez que haya configurado las dimensiones y métricas deseadas para el conjunto de datos de Journey Optimizer, también puede configurar [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obtener información adicional sobre esos datos. Estas métricas calculadas se basan en las métricas creadas anteriormente en el Administrador de vistas de datos.

| Métrica calculada | Descripción | Fórmula |
| --- | --- | --- |
| Mensajes enviados | El número total de mensajes enviados. Incluye mensajes enviados con éxito o fallidos. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Mensajes entregados | Número de correos electrónicos enviados a los clientes. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
