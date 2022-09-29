---
title: Integración de Adobe Journey Optimizer con el Customer Journey Analytics
description: Incorpore datos generados por AJO y analícelos usando Analysis Workspace dentro de CJA.
source-git-commit: 28bc99a7f5ec7b280fd26a7a45dc076e67f652dc
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 2%

---


# Integración de Adobe Journey Optimizer con el Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=es) ayuda a ofrecer experiencias conectadas, contextuales y personalizadas. Esto ayuda a exponer a los clientes al siguiente paso de su recorrido de clientes.

Puede importar los datos generados por Journey Optimizer para realizar análisis avanzados en Customer Journey Analytics siguiendo estos pasos:

## Envío de datos de Journey Optimizer a Adobe Experience Platform

Adobe Experience Platform sirve como fuente de datos central y vínculo entre Journey Optimizer y Customer Journey Analytics. Consulte [Introducción a los conjuntos de datos](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) en la guía del usuario de Journey Optimizer para ver los pasos sobre cómo enviar datos de Journey Optimizer a Platform as a Dataset.

## Crear una conexión en el Customer Journey Analytics

Una vez que los datos de Journey Optimizer están en Adobe Experience Platform, puede [Crear una conexión](/help/connections/create-connection.md) en función de su conjunto de datos de Journey Optimizer. Seleccione el conjunto de datos que ha enviado a Platform.

## Configure la vista Datos para que se ajuste a las dimensiones y métricas de Journey Optimizer

Después de crear una conexión, puede crear una o más [Vistas de datos](/help/data-views/create-dataview.md) para configurar las dimensiones y métricas disponibles en Customer Journey Analytics.

Puede crear las métricas siguientes en una vista de datos para lograr una paridad aproximada con métricas similares en Journey Optimizer. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md) en el Administrador de vista de datos para obtener detalles sobre cómo personalizar dimensiones y métricas.

| Métrica | Descripción | Configuración de la vista de datos |
| --- | --- | --- |
| Devoluciones | El número de mensajes que se rebotaron | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Si se cumplen algunos criterios<br>Es igual a: `bounce`<br>Es igual a: `denylist` |
| Errores | El número de mensajes erróneos | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `error` |
| Excluye | El número de mensajes excluidos | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `exclude` |
| Cancelación de suscripción | El número de bajas | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageInteraction.interactionType` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `unsubscribe` |
| Clics | El recuento de clics dentro de los mensajes | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageInteraction.interactionType` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `click` |
| Aperturas | El número de mensajes abiertos | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageInteraction.interactionType` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `open` |
| Reclamaciones por correo no deseado | Recuento de quejas por correo no deseado | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageInteraction.interactionType` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `spam_complaint` |
| Mensajes enviados correctamente | El número de mensajes enviados correctamente | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `sent` |
| Errores de sincronización | El número total de mensajes que no se sincronizaron | Usar el elemento de cadena de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` con la siguiente configuración:<br>Tipo de componente: Métrica<br>Incluir valores de exclusión: Es igual a `sync` |

## Configurar métricas calculadas con métricas de Journey Optimizer

Una vez que haya configurado las dimensiones y métricas deseadas para el conjunto de datos de Journey Optimizer, también puede configurar [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obtener información adicional sobre esos datos. Estas métricas calculadas se basan en las métricas creadas anteriormente en el Administrador de vistas de datos.

| Métrica calculada | Descripción | Fórmula |
| --- | --- | --- |
| Total de mensajes enviados | El número total de mensajes enviados, correctos o fallidos | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

## Diferencias en los informes entre Journey Optimizer y Customer Journey Analytics

Las discrepancias de datos entre productos suelen estar entre el 1 y el 2 %. Las discrepancias más grandes entre los productos pueden atribuirse potencialmente a lo siguiente:

* El tiempo de procesamiento de los datos entrantes puede ser ligeramente diferente entre los productos, especialmente para los datos recopilados en las últimas dos horas. Utilice intervalos de fechas que excluyan hoy para mitigar las discrepancias que implican tiempo de procesamiento.
* La métrica calculada &quot;Mensajes totales enviados&quot; no incluye la métrica &quot;Reintentos&quot;. Los datos de la métrica &quot;Reintentos&quot; no se incluyen en el conjunto de datos y muestran números potencialmente inferiores en los informes de CJA en comparación con los de AJO. Sin embargo, los datos de reintentos se convierten en las métricas &quot;Mensajes enviados correctamente&quot; o &quot;Devoluciones&quot;. Utilice intervalos de fechas de una semana o más para mitigar las discrepancias con la métrica &quot;Mensajes totales enviados&quot; entre productos.
