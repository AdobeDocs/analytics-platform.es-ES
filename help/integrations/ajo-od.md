---
title: Integración de Administración de decisiones de Adobe Journey Optimizer con Adobe Customer Journey Analytics
description: Incorpore datos generados por la gestión de decisiones de Adobe Journey Optimizer y analícelos con Analysis Workspace en Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 20%

---

# Integración de Administración de decisiones con Adobe Customer Journey Analytics


Adobe Journey Optimizer [Gestión de decisiones](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) facilita la personalización con una biblioteca central de ofertas de marketing y un motor de decisión que aplica reglas y restricciones a perfiles enriquecidos en tiempo real creados por Adobe Experience Platform para ayudarle a enviarles a sus clientes la oferta correcta en el momento adecuado.

Gestión de decisiones forma parte de Adobe Journey Optimizer y está integrada con él. También se puede utilizar de forma independiente de los recorridos y campañas definidos en Adobe Journey Optimizer, utilizando su [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) soporte.

Puede importar los datos generados por Gestión de decisiones para realizar análisis avanzados en Customer Journey Analytics realizando los siguientes pasos:

## Envío de datos de Gestión de decisiones a Adobe Experience Platform

Adobe Experience Platform sirve como fuente de datos central y vínculo entre Administración de decisiones y Customer Journey Analytics. Los datos de Administración de decisiones se recopilan en Experience Platform **automáticamente** o como parte de **eventos de experiencia enviados explícitamente** (por ejemplo, impresiones o clics). Consulte [Introducción a la recopilación de datos](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) para obtener más información.

## Crear una conexión

Una vez que los datos de Administración de decisiones estén en Adobe Experience Platform, puede crear un [Conexión](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es) en función de sus conjuntos de datos de Administración de decisiones. O puede agregar conjuntos de datos de Administración de decisiones a una conexión existente.

Seleccione y configure los siguientes conjuntos de datos:

| Conjunto de datos | Tipo de conjunto de datos | Configuración de la conexión | Descripción |
| --- | --- | --- | --- |
| ODE DecisionEvents - _espacio aislado_ toma de decisiones | Evento | ID de la persona: `IdentityMap` | Contiene datos generados automáticamente para eventos de decisión de Administración de decisiones. _Sandbox_ hace referencia al nombre de zona protegida específico. |
| Conjunto de datos de evento de comentarios de mensajes Adobe Journey Optimizer | Evento | ID de la persona: `IdentityMap` | Contiene eventos de envío de mensajes. |
| Conjunto de datos de evento de experiencia de seguimiento de correo electrónico Adobe Journey Optimizer | Evento | ID de la persona: `IdentityMap` | Contiene eventos de seguimiento de correo electrónico. |
| Conjunto de datos de evento de experiencia de seguimiento push de Adobe Journey Optimizer | Evento | ID de la persona: `IdentityMap` | Contiene eventos de seguimiento push. |
| Conjunto de datos de entidad Adobe Journey Optimizer | Búsqueda | Clave: `_id`<br>Clave de coincidencia: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene clasificaciones que asocian metadatos de Recorridos y campañas a todos los datos de eventos de Adobe Journey Optimizer. |

{style="table-layout:auto"}

## Creación de una vista de datos

Después de crear una conexión, puede crear una o más [Vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=es) para configurar las dimensiones y métricas deseadas disponibles en Customer Journey Analytics.

>[!NOTE]
>
>Las discrepancias de datos entre Adobe Journey Optimizer y Customer Journey Analytics suelen ser inferiores al 1-2 %. Es posible que las discrepancias sean mayores cuando los datos se hayan recopilado en las dos últimas horas. Utilice intervalos de fechas que excluyan hoy para mitigar las discrepancias que implican tiempo de procesamiento.

### Configuración de dimensiones

Puede crear las siguientes dimensiones en una vista de datos para lograr una paridad aproximada con dimensiones similares en Administración de decisiones. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de dimensiones.

| Dimensión | Elemento de esquema | Configuración de componentes |
| --- | --- | --- |
| Nombre de la actividad | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Tipo de componente: Dimensión |
| Identificador de contenedor | `_experience.decisioning.containerID` | Tipo de componente: Dimensión |
| Identificador de correlación | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Tipo de componente: Dimensión |
| Nombre de opción de decisión | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Tipo de componente: Dimensión |
| Nombre de opción de decisión de reserva | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Tipo de componente: Dimensión |
| Nombre de ubicación | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Tipo de componente: Dimensión |

{style="table-layout:auto"}


### Configurar métricas

Puede crear las siguientes métricas en una vista de datos para lograr una paridad aproximada con métricas similares en Administración de decisiones. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de métricas.

| Métrica | Descripción | Elemento de esquema | Configuración de componentes |
| --- | --- | --- | --- |
| Tipo de evento (cambie el nombre para hacer referencia a un evento específico, por ejemplo, `Feedback` para `message.feedback`) [1] | Importe de un tipo específico de evento | `eventType` | Tipo de componente: Métrica<br/>**[!UICONTROL Establecer valores de exclusión de inclusión ]**: Activado<br/>**[!UICONTROL Coincidencia]**: [!UICONTROL Si se cumplen todos los criterios]<br/>**[!UICONTROL Criterios ]**:**[!UICONTROL  Igual a ]**`message.feedback` |
| Puntuación de opción de decisión | Valor calculado para una opción de decisión en el contexto de un solo ámbito. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo de componente: Métrica |
| Opción de decisión de reserva | Valor calculado para una opción de decisión de reserva en el contexto de un solo ámbito. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo de componente: Métrica |
| Ofertas descartadas | El número de ofertas rechazadas o rechazadas sin ninguna otra interacción directa. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: Métrica |
| Visualización de ofertas | El número de ofertas mostradas en el perfil. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: Métrica |
| Interacción de ofertas | El número de ofertas mostradas en el perfil. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo de componente: Métrica |
| Envíos de ofertas | El número de ofertas enviadas al perfil. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo de componente: Métrica |
| Déclencheur de ofertas | El número de ofertas seleccionadas para que las muestre el SDK de cliente. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: Métrica |
| Cancelación de suscripción a ofertas | El número de ofertas solicitadas por perfil que no se mostrarán en el futuro. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: Métrica |

{style="table-layout:auto"}

[1] Puede definir varias métricas para los distintos tipos de eventos disponibles. Consulte [Incluir valores de exclusión configuración de componentes](/help/data-views/component-settings/include-exclude-values.md) para obtener más información.
