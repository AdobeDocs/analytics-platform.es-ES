---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a5710e2d978661837016db5ed1bab5a53fb2d63e
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 76%

---

# Notas de la versión actuales de Adobe Customer Journey Analytics (octubre/noviembre de 2023)


**Última actualización**: 26 de octubre de 2023

Estas notas de la versión abarcan el periodo de lanzamiento del 16 de octubre de 2023 a finales de noviembre de 2023. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nuevas funciones de [!UICONTROL Uso] ver en Adobe Product Analytics** | Se han añadido las siguientes funciones a la [Vista de uso](/help/guided-analysis/types/usage.md):<ul><li>**Líneas de tendencia**: ahora se admiten las líneas de tendencia. Clic [!UICONTROL Superposiciones] encima del gráfico para activarlos.</li><li>**Desgloses de consultas**: Ahora puede aplicar desgloses a este tipo de vista. Están disponibles como opción en el carril de la consulta.</li></ul> | N/A | 25 de octubre de 2023 |
| **Documentación para la API de vistas de datos de CJA** | Consulte la [API de vistas de datos](https://developer.adobe.com/cja-apis/docs/endpoints/dataviews/) para obtener información sobre cómo crear, modificar o eliminar vistas de datos mediante programación. | N/A | 16 de octubre de 2023 |
| **Exportar tablas completas a la nube** | La exportación de tablas completas de Customer Journey Analytics le permite exportar millones de filas de Workspace a destinos de nube. <p>La exportación de tablas completas ofrece un envío único o programado de tablas de datos diseñadas en Workspace con soporte para hasta cinco desgloses, cinco métricas, filtros y métricas calculadas, todo en una tabla concatenada. Es la evolución de los informes de Data Warehouse en Adobe Analytics, con muchas funciones nuevas y a menudo solicitadas que no están disponibles en Data Warehouse en la actualidad.</p><p> Las opciones de exportación a la nube incluyen:</p><ul><li>Zona de aterrizaje de datos de Adobe Experience Platform</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>Para obtener más información, consulte [Exportar informes de Customer Journey Analytics a la nube](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=es). | 4 de octubre de 2023 | 19 de octubre de 2023 |
| **Administrador de actividades de creación de informes** | El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Proporciona a los administradores una visibilidad detallada del consumo de creación de informes para diagnosticar y corregir fácilmente los problemas de capacidad durante las horas de mayor actividad de creación de informes. Entre las características principales del Administrador de actividades de creación de informes se incluyen:<ul><li>Cancelar las solicitudes de creación de informes actuales (incluidas las solicitudes de análisis guiados y exportaciones de tabla completa)</li><li>Restringir solicitudes posteriores durante un período de tiempo definido</li></ul>Además de cancelar las solicitudes actuales, los administradores ahora pueden restringir las solicitudes durante un período de tiempo definido. Los administradores pueden restringir las solicitudes por solicitud, proyecto o usuario.  [Más información](/help/reporting-activity-manager/reporting-activity-overview.md) | 17 de octubre de 2023 | 24 de octubre de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-327661; AN-329282; AN-329383; AN-329808; AN-331030; AN-331087; AN-331105

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | N/A | N/A |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
