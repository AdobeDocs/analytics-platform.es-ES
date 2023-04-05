---
title: Integración de la administración de decisiones de Adobe Journey Optimizer con Customer Journey Analytics (CJA)
description: Incorpore los datos generados por la Administración de decisiones de Adobe Journey Optimizer y analícelos con Analysis Workspace dentro de Customer Journey Analytics.
source-git-commit: f9ee0db464c49339bc36b144e18ef4aea4f4f033
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 18%

---

# Integración de la gestión de decisiones con el Customer Journey Analytics


Adobe Journey Optimizer [Administración de decisiones](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) facilita la personalización con una biblioteca central de ofertas de marketing y un motor de decisión que aplica reglas y restricciones a perfiles enriquecidos y en tiempo real creados por Adobe Experience Platform para ayudarle a enviar a sus clientes la oferta correcta en el momento adecuado.

La gestión de decisiones forma parte de Adobe Journey Optimizer (AJO) y se integra con él. También se puede utilizar independientemente de los recorridos y campañas definidos en AJO, utilizando su riqueza [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) asistencia técnica.

Puede importar los datos generados por la Administración de decisiones para realizar análisis avanzados en Customer Journey Analytics (CJA) siguiendo estos pasos:

## Envío de datos desde Administración de decisiones a Adobe Experience Platform

Adobe Experience Platform sirve como fuente de datos central y vínculo entre Administración de decisiones y Customer Journey Analytics. Los datos de Administración de decisiones se recopilan en el Experience Platform **automatically** o como parte de **eventos de experiencia enviados explícitamente** (por ejemplo, impresiones o clics). Consulte [Introducción a la recopilación de datos](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) para obtener más información.

## Crear una conexión

Una vez que los datos de Administración de decisiones se encuentran en Adobe Experience Platform, puede crear una [Conexión](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es) en función de sus conjuntos de datos de Administración de decisiones . O puede agregar conjuntos de datos de Administración de decisiones a una conexión existente.

Seleccione y configure los siguientes conjuntos de datos:

| Conjunto de datos | Tipo de conjunto de datos | Configuración de la conexión | Descripción |
| --- | --- | --- | --- |
| ODE DecisonEvents - _entorno limitado_ decisioning | Evento | ID de la persona: `IdentityMap` | Contiene datos generados automáticamente para los eventos de decisión de Administración de decisiones. _Sandbox_ hace referencia al nombre específico del simulador de pruebas. |
| Conjunto de datos del evento de comentarios de mensajes AJO | Evento | ID de la persona: `IdentityMap` | Contiene eventos de envío de mensajes. |
| Conjunto de datos del evento de experiencia de seguimiento de correo electrónico AJO | Evento | ID de la persona: `IdentityMap` | Contiene eventos de seguimiento de correo electrónico. |
| Conjunto de datos del evento de experiencia de seguimiento push de AJO | Evento | ID de la persona: `IdentityMap` | Contiene eventos de seguimiento push. |
| Conjunto de datos de entidad AJO | Búsqueda | Clave: `_id`<br>Clave de coincidencia: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene clasificaciones que asocian metadatos de Recorrido y campaña a todos los datos de evento de AJO. |

{style="table-layout:auto"}

## Creación de una vista de datos

Después de crear una conexión, puede crear una o más [Vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=es) para configurar las dimensiones y métricas deseadas disponibles en CJA.

>[!NOTE]
>
>Las discrepancias de datos entre AJO y CJA suelen ser inferiores al 1-2 %. Es posible que las discrepancias sean mayores cuando los datos se hayan recopilado en las dos últimas horas. Utilice intervalos de fechas que excluyan hoy para mitigar las discrepancias que implican tiempo de procesamiento.

### Configurar dimensiones

Puede crear las siguientes dimensiones en una vista de datos para lograr una paridad aproximada con dimensiones similares en Administración de decisiones. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de dimensiones.

| Dimensión | Elemento de esquema | Configuración de componentes |
| --- | --- | --- |
| Nombre de la actividad | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Tipo de componente: Dimensión |
| Identificador de contenedor | `_experience.decisioning.containerID` | Tipo de componente: Dimensión |
| Identificador de correlación | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Tipo de componente: Dimensión |
| Nombre de opción de decisión | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Tipo de componente: Dimensión |
| Nombre de opción de decisión de reserva | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Tipo de componente: Dimensión |
| Nombre de colocación | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Tipo de componente: Dimensión |

{style="table-layout:auto"}


### Configurar métricas

Puede crear las siguientes métricas en una vista de datos para lograr una paridad aproximada con métricas similares en Administración de decisiones. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener más información sobre las opciones de personalización de métricas.

| Métrica | Descripción | Elemento de esquema | Configuración de componentes |
| --- | --- | --- | --- |
| Tipo de evento (cambie el nombre para hacer referencia a un evento específico, por ejemplo `Feedback` para `message.feedback`) [1] | Cantidad de un tipo específico de evento | `eventType` | Tipo de componente: Métrica<br/>**[!UICONTROL Definir valores de exclusión de inclusión ]**: Activado<br/>**[!UICONTROL Coincidencia]**: [!UICONTROL Si se cumplen todos los criterios]<br/>**[!UICONTROL Criterios ]**:**[!UICONTROL  Es igual a ]**`message.feedback` |
| Puntuación de opción de decisión | Valor calculado para una opción de decisión en el contexto de un solo ámbito. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo de componente: Métrica |
| Puntuación de opción de decisión de reserva | Valor calculado para una opción de decisión de reserva en el contexto de un solo ámbito. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo de componente: Métrica |
| Desestimación de ofertas | Número de ofertas rechazadas o rechazadas sin ninguna otra interacción directa. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: Métrica |
| Visualización de ofertas | Número de ofertas mostradas en el perfil. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: Métrica |
| Interacción de ofertas | Número de ofertas mostradas en el perfil. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo de componente: Métrica |
| Envío de ofertas | Número de ofertas enviadas al perfil. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo de componente: Métrica |
| Déclencheur de ofertas | Número de ofertas que el SDK de cliente ha elegido mostrar. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: Métrica |
| Cancelación de suscripción de ofertas | Número de ofertas solicitadas por perfil que no se mostrarán en el futuro. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: Métrica |

{style="table-layout:auto"}
[1] Puede definir varias métricas para los distintos tipos de evento disponibles. Consulte [Incluir valores de exclusión configuración de componentes](/help/data-views/component-settings/include-exclude-values.md) para obtener más información.
