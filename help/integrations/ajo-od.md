---
title: Integración de Adobe Journey Optimizer Decision Management
description: Incorpore datos generados por Gestión de decisiones de Adobe Journey Optimizer y analícelos con Analysis Workspace en Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
autotag-review: '2026-05-19T07:19:20.352Z'
TQID: 'https://experienceleague.adobe.com/n3xsScsv43IG-tOQhgNjeqB2UmWzbIVw7sv5CcpZPd0'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: df066828-d385-4da6-af58-80137fb27d7b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 753
ht-degree: 100%

---

# Integración de gestión de decisiones


La [gestión de decisiones](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=es) de Adobe Journey Optimizer facilita la personalización con una biblioteca central de ofertas de marketing y un motor de decisión que aplica reglas y restricciones a perfiles enriquecidos en tiempo real creados por Adobe Experience Platform para ayudarle a enviar a sus clientes la oferta correcta en el momento adecuado.

La gestión de decisiones forma parte de Adobe Journey Optimizer y está integrada en él. También se puede utilizar de forma independiente de los recorridos y campañas definidos en Adobe Journey Optimizer, utilizando su amplio soporte de [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=es).

Puede importar los datos generados por la gestión de decisiones para realizar análisis avanzados en Customer Journey Analytics al realizar los siguientes pasos:

## Envío de datos de la gestión de decisiones a Adobe Experience Platform

Adobe Experience Platform sirve como fuente de datos central y vínculo entre Gestión de decisiones y Customer Journey Analytics. Los datos de la gestión de decisiones se recopilan en Experience Platform **automáticamente** o como parte de los **eventos de experiencia enviados explícitamente** (por ejemplo, impresiones o clics). Para obtener más información, consulte la [Introducción a la recopilación de datos](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=es).

## Crea una conexión

Una vez que los datos de la gestión de decisiones están en Adobe Experience Platform, puede crear una [conexión](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es) en función de su conjunto de datos de la gestión de decisiones. O puede añadir conjuntos de datos de gestión de decisiones a una conexión existente.

Seleccione y configure los siguientes conjuntos de datos:

| Conjunto de datos | Tipo de conjunto de datos | Configuración de la conexión | Descripción |
| --- | --- | --- | --- |
| ODE DecisionEvents: toma de decisiones de la _zona protegida_ | Evento | ID de persona: `IdentityMap` | Contiene datos generados automáticamente para eventos de decisión de Gestión de decisiones. _Zona protegida_ hace referencia al nombre de zona protegida específico. |
| Conjunto de datos de evento de comentarios de mensajes de Adobe Journey Optimizer | Evento | ID de persona: `IdentityMap` | Contiene eventos de envío de mensajes. |
| Conjunto de datos de evento de experiencia de seguimiento del correo electrónico de Adobe Journey Optimizer | Evento | ID de persona: `IdentityMap` | Contiene eventos de seguimiento del correo electrónico. |
| Conjunto de datos de evento de experiencia de seguimiento push de Adobe Journey Optimizer | Evento | ID de persona: `IdentityMap` | Contiene eventos de seguimiento push. |
| Conjunto de datos de entidad de Adobe Journey Optimizer | Búsqueda | Clave: `_id`<br>Clave de coincidencia: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene clasificaciones que asocian metadatos de Recorridos y campañas a todos los datos de eventos de Adobe Journey Optimizer. |

{style="table-layout:auto"}

## Crea una vista de datos

Después de crear una conexión, puede crear una o más [Vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=es) para configurar las dimensiones y métricas deseadas disponibles en Customer Journey Analytics.

>[!NOTE]
>
>Las discrepancias de datos entre Adobe Journey Optimizer y Customer Journey Analytics suelen ser inferiores al 1-2 %. Es posible que las discrepancias sean mayores cuando los datos se hayan recopilado en las dos últimas horas. Utilice intervalos de fechas que excluyan hoy para mitigar las discrepancias que implican tiempo de procesamiento.

### Configuración de dimensiones

Puede crear las dimensiones siguientes en una vista de datos para lograr una paridad aproximada con dimensiones similares en Gestión de decisiones. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de dimensiones.

| Dimensión | Elemento de esquema | Configuración de componentes |
| --- | --- | --- |
| Nombre de la actividad | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Tipo de componente: dimensión |
| Identificador de contenedor | `_experience.decisioning.containerID` | Tipo de componente: dimensión |
| Identificador de correlación | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Tipo de componente: dimensión |
| Nombre de opción de decisión | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Tipo de componente: dimensión |
| Nombre de opción de decisión de reserva | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Tipo de componente: dimensión |
| Nombre de ubicación | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Tipo de componente: dimensión |

{style="table-layout:auto"}


### Configuración de métricas

Puede crear las siguientes métricas en una vista de datos para lograr una paridad aproximada con métricas similares en Gestión de decisiones. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de métricas.

| Métrica | Descripción | Elemento de esquema | Configuración de componentes |
| --- | --- | --- | --- |
| Tipo de evento (cambie el nombre para hacer referencia a un evento específico, por ejemplo, `Feedback` para `message.feedback`) [1] | Cantidad de un tipo específico de evento | `eventType` | Tipo de componente: Métrica<br/>**[!UICONTROL Establecer valores de exclusión de inclusión ]**: Activado<br/>**[!UICONTROL Coincidencia]**: [!UICONTROL Si se cumplen todos los criterios]<br/>**[!UICONTROL Criterios ]**:**[!UICONTROL  Igual a ]**`message.feedback` |
| Puntuación de opción de decisión | Valor calculado para una opción de decisión en el contexto de un solo ámbito. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo de componente: métrica |
| Puntuación de opción de decisión de reserva | Valor calculado para una opción de decisión de reserva en el contexto de un solo ámbito. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo de componente: métrica |
| Ofertas descartadas | El número de ofertas descartadas o rechazadas sin ninguna otra interacción directa. | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Tipo de componente: métrica |
| Visualización de ofertas | Número de ofertas visualizadas en el perfil. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: métrica |
| Interacción de ofertas | El número de ofertas con las que interactuó el perfil. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo de componente: métrica |
| Ofertas enviadas | Número de ofertas enviadas al perfil. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo de componente: métrica |
| Activador de ofertas | El número de ofertas elegidas para ser mostradas por el SDK del cliente. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: métrica |
| Cancelación la suscripción de ofertas | El número de ofertas solicitadas por perfil que no se mostrarán en el futuro. | `_experience.decisioning.`<br/>`propositionEventType.unsubscribe` | Tipo de componente: métrica |

{style="table-layout:auto"}

[1]Puede definir múltiples métricas para los distintos tipos de eventos disponibles. Consulte [Configuración del componente Incluir/excluir valores](/help/data-views/component-settings/include-exclude-values.md) para obtener más información.
