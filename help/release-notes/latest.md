---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2828a38161222a5433b15045a70cb25cfbc8bae7
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 100%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (octubre de 2023)

**Última actualización**: 4 de octubre de 2023

Estas notas de la versión abarcan el periodo de lanzamiento del 4 de octubre de 2023 al 24 de octubre de 2023. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Exportar tablas completas a la nube** | La exportación de tablas completas de Customer Journey Analytics le permite exportar millones de filas de Workspace a destinos de nube. <p>La exportación de tablas completas ofrece un envío único o programado de tablas de datos diseñadas en Workspace con soporte para hasta cinco desgloses, cinco métricas, filtros y métricas calculadas, todo en una tabla concatenada. Es la evolución de los informes de Data Warehouse en Adobe Analytics, con muchas funciones nuevas y a menudo solicitadas que no están disponibles en Data Warehouse en la actualidad.</p><p> Las opciones de exportación a la nube incluyen:</p><ul><li>Zona de aterrizaje de datos de Adobe Experience Platform</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>Para obtener más información, consulte [Exportar informes de Customer Journey Analytics a la nube](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=es). | 4 de octubre de 2023 | 19 de octubre de 2023 |
| **Nuevas columnas disponibles al administrar componentes** | Las siguientes columnas nuevas ya están disponibles en el [Administrador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html?lang=es) y el [Administrador de filtros](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html?lang=es) al administrar componentes:<ul><li>Utilizado en</li><li>Último uso</li></ul>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse. Puede utilizar el diccionario de datos junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización. | 23 de septiembre de 2023 | 4 de octubre de 2023 |
| **Migrar proyectos de Adobe Analytics y cualquier componente incluido a Customer Journey Analytics** | Ahora puede migrar sus proyectos de Adobe Analytics a Customer Journey Analytics. Este proceso simplifica la transición de Adobe Analytics a Customer Journey Analytics. <p>Al migrar proyectos a Customer Journey Analytics, los recursos se asignan de un grupo de informes de Adobe Analytics a una vista de datos de Customer Journey Analytics.</p> <p>Los proyectos se migran a Customer Journey Analytics desde la interfaz de Adobe Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=es)</p> | N/A | 9 de octubre de 2023 |
| **Adobe Product Analytics: Mostrar/ocultar serie** | Haga clic en la leyenda del gráfico o en las filas de la tabla para controlar la visibilidad de las series en las visualizaciones.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=es) | N/A | 4 de octubre de 2023 |
| **Anotaciones en Adobe Product Analytics** | El análisis guiado ahora admite la capacidad de ver anotaciones creadas en Customer Journey Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=es) | N/A | 4 de octubre de 2023 |
| **Administrador de actividades de creación de informes** | El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Proporciona a los administradores una visibilidad detallada del consumo de creación de informes para diagnosticar y corregir fácilmente los problemas de capacidad durante las horas de mayor actividad de creación de informes. Entre las características principales del Administrador de actividades de creación de informes se incluyen:<ul><li>Cancelar las solicitudes de creación de informes actuales (incluidas las solicitudes de análisis guiados y exportaciones de tabla completa)</li><li>Restringir solicitudes posteriores durante un período de tiempo definido</li></ul>Además de cancelar las solicitudes actuales, los administradores ahora pueden restringir las solicitudes durante un período de tiempo definido. Los administradores pueden restringir las solicitudes por solicitud, proyecto o usuario.  [Más información](/help/reporting-activity-manager/reporting-activity-overview.md) | 17 de octubre de 2023 | 23 de octubre de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-325940, AN-326468, AN-328301, AN-328640 y AN-329370

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | N/A | N/A |

{style="table-layout:auto"}

## Avisos de final de la vida útil

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics, la API de Customer Journey Analytics y Livestream que usan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
