---
title: Integración de Adobe Journey Optimizer (AJO) con Customer Journey Analytics (CJA)
description: Incorpore datos generados por AJO y analícelos usando Analysis Workspace dentro de CJA.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 9aed4e724c564272071b96c037f4eb0e82572e6f
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 53%

---

# Integración de Adobe Journey Optimizer con Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=es) le ayuda a ofrecer experiencias conectadas, contextualizadas y personalizadas. Esto ayuda a exponer a los clientes al siguiente paso de su recorrido del cliente.

Puede importar los datos generados por Journey Optimizer para realizar análisis avanzados en Customer Journey Analytics al realizar los siguientes pasos:

## Envío de datos de Journey Optimizer a Adobe Experience Platform

Adobe Experience Platform sirve como fuente de datos central y vínculo entre Journey Optimizer y Customer Journey Analytics. Consulte [Introducción a los conjuntos de datos](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=es) en la guía del usuario de Journey Optimizer para ver los pasos sobre cómo enviar datos de Journey Optimizer a Platform como un conjunto de datos.

## Crear una conexión en Customer Journey Analytics

Una vez que los datos de Journey Optimizer están en Adobe Experience Platform, puede [Crear una conexión](/help/connections/create-connection.md) en función de su conjunto de datos de Journey Optimizer. Seleccione el conjunto de datos que ha enviado a Platform.

## Configure la vista Datos para que se ajuste a las dimensiones y métricas de Journey Optimizer

Después de crear una conexión, puede crear una o más [Vistas de datos](/help/data-views/create-dataview.md) para configurar las dimensiones y métricas deseadas disponibles en Customer Journey Analytics.

>!![NOTE]
Las discrepancias de datos entre AJO y CJA suelen ser inferiores al 1-2 %. Las discrepancias más grandes son posibles para los datos recopilados en las últimas dos horas. Utilice intervalos de fechas que excluyan hoy para mitigar las discrepancias que implican tiempo de procesamiento.

### Configuración de dimensiones en la vista de datos

Puede crear las siguientes dimensiones en una vista de datos para lograr una paridad aproximada con dimensiones similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de dimensiones.

| Dimensión | Elemento Esquema | Configuración de componentes |
| --- | --- | --- |
| Nombre del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: Dimension |
| Nombre y versión del recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo de componente: Dimension |
| Nombre de nodo de recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: Dimension |
| Tipo de nodo de recorrido | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Tipo de componente: Dimension |
| Nombre de la campaña | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Tipo de componente: Dimension |
| Canal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Tipo de componente: Dimension |
| Título push | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Tipo de componente: Dimension |
| Asunto del mensaje de correo electrónico | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Tipo de componente: Dimension |
| Etiqueta de vínculo | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Tipo de componente: Dimension |
| Nombre del experimento | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Tipo de componente: Dimension<br>Etiquetas de contexto: Experimento de experimentación |
| Nombre del tratamiento | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Tipo de componente: Dimension<br>Etiquetas de contexto: Variante de experimentación |
| Motivo del error de entrega de correo electrónico | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Tipo de componente: Dimension |
| Motivo de exclusión de entrega de correo electrónico | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Tipo de componente: Dimension |

{style=&quot;table-layout:auto&quot;}

### Configurar métricas en la vista de datos

Puede crear las métricas siguientes en una vista de datos para lograr una paridad aproximada con métricas similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de métricas.

| Métrica | Descripción | Elemento Esquema | Configuración de componentes |
| --- | --- | --- | --- |
| Devoluciones | El número de mensajes que se rebotaron, incluidos los rechazos inmediatos y los rechazos después de la entrega. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Si se cumplen algunos criterios<br>Es igual a: `bounce`, Igual a: `denylist` |
| Devoluciones después de la entrega | Algunos servicios de correo electrónico informan de los correos electrónicos enviados y luego los devuelven más adelante. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `async` |
| Clics en correos electrónicos | El recuento de clics dentro de los mensajes. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `click` |
| Aperturas de correo electrónico | El número de mensajes abiertos. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `open` |
| Errores | El número de mensajes erróneos. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `error` |
| Excluye  | El número de mensajes excluidos. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `exclude` |
| Enviados | Número de mensajes que los proveedores de correo electrónico aceptaron. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `sent` |
| Reclamaciones por correo no deseado | Recuento de quejas por correo no deseado. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `spam_complaint` |
| Cancelación de suscripción | El número de bajas. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `unsubscribe` |

{style=&quot;table-layout:auto&quot;}

### Configurar métricas calculadas en Analysis Workspace

Una vez que haya configurado las dimensiones y métricas deseadas para el conjunto de datos de Journey Optimizer, también puede configurar [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obtener información adicional sobre esos datos. Estas métricas calculadas se basan en las métricas creadas anteriormente en el Administrador de vistas de datos.

| Métrica calculada | Descripción | Fórmula |
| --- | --- | --- |
| Mensajes enviados | El número total de mensajes enviados. Incluye mensajes correctos o fallidos. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Mensajes entregados | Número de correos electrónicos enviados a los clientes. | `[Sends] - [Bounces After Delivery]` |

{style=&quot;table-layout:auto&quot;}
