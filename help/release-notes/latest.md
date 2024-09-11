---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d0315fe645e62a2c67148cb0fc3fbd4c1b780187
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 43%

---

# Notas actuales de la versión de Customer Journey Analytics (septiembre de 2024)

**Última actualización**: jueves, 11 de septiembre de 2024

Estas notas de la versión abarcan el período de lanzamiento del 11 de septiembre de 2024 a principios de octubre. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Análisis de uso** | Consulte cómo utiliza su organización Customer Journey Analytics. Al habilitar esta función, se crea un conjunto de datos en Adobe Experience Platform que recopila datos cuando cualquier persona de su organización utiliza Analysis Workspace. También se crean automáticamente una conexión y una vista de datos, lo que le permite acceder a dimensiones como los tipos de proyecto principales, los usuarios más activos y los componentes más populares utilizados en los proyectos. (Vínculo a la documentación a continuación) |  | 18 de septiembre de 2024 |
| **Información adicional en la columna &quot;Utilizado en&quot; del administrador de métricas calculadas y del administrador de filtros** | La columna &quot;Utilizado en&quot; del administrador de métricas calculadas y del administrador de filtros contiene las siguientes áreas nuevas de creación de informes:<ul><li>**Report Builder**: muestra el número de métricas calculadas o filtros que se están usando en el Report Builder.</li><li>**Componentes ad hoc**: Muestra el número de métricas calculadas ad hoc o filtros ad hoc que se están usando en los proyectos. Estas métricas y filtros calculados específicos (conocidos como &quot;métricas calculadas rápidas&quot; y &quot;filtros rápidos&quot;) solo se pueden usar en el proyecto en el que se crearon, por lo que se crean por separado del área de informes &quot;Proyecto&quot; en la columna &quot;Utilizado en&quot;.</li></ul>(Vínculo a la documentación a continuación) |  | 11 de septiembre de 2024 |
| **Análisis guiado: incrustar en Workspace** | Combine varios análisis guiados en una sola vista en Analysis Workspace. (Vínculo a la documentación a continuación) | lunes, 22 de septiembre de 2024 | jueves, 02 de octubre de 2024 |
| **Alertas inteligentes** | Las alertas inteligentes de Customer Journey Analytics le permiten recibir notificaciones de forma inmediata cuando se producen eventos anormales en sus datos.<p>Puede definir alertas para que se activen en función de umbrales de anomalías, porcentajes modificados o puntos de datos específicos. Las alertas proporcionan controles granulares que se integran con la Detección de anomalías y se activan cuando más los necesita.</p><p>El proceso de utilización de las Alertas inteligentes en Customer Journey Analytics es casi idéntico al de las Alertas inteligentes en Adobe Analytics. Una diferencia clave es que las alertas horarias no están disponibles en Customer Journey Analytics. Esta diferencia se debe a que la ingesta de datos para los distintos tipos de datos de evento que se pueden introducir se completa solo después de un retraso, que generalmente oscila entre 3 y 9 horas después del tiempo de evento de datos. (Vínculo a la documentación a continuación)</p><p><!--[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)--></p> |  | jueves, 11 de septiembre de 2024 |
| **Actualizaciones en el conector de origen de Adobe Analytics** | La página de actividad del conjunto de datos no muestra información sobre los lotes, ya que el conector de Source de Analytics se administra completamente mediante el Adobe. Puede monitorizar que los datos fluyen mirando las métricas alrededor de los registros ingeridos. Lea la guía sobre [creación de una conexión de origen para datos de Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) para obtener más información. |  | Ya disponible |


## Correcciones en Customer Journey Analytics

AN-352461; AN-355446: AN-355665

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | | |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión del complemento de recopilación de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
