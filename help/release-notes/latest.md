---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7d915fc9b50163b7ec9c48232b99a85a3b063a77
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 42%

---

# Notas actuales de la versión de Customer Journey Analytics (julio de 2024)

**Última actualización**: jueves, 17 de julio de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 17 de julio de 2024 a agosto de 2024. Las versiones de Adobe Customer Journey Analytics funcionan con un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Alertas inteligentes** | Las alertas inteligentes ya están disponibles en Customer Journey Analytics, lo que le permite recibir notificaciones inmediatas cuando se producen eventos anormales en los datos.<p>Puede definir alertas para que se activen en función de umbrales de anomalías, porcentajes modificados o puntos de datos específicos. Las alertas proporcionan controles granulares que se integran con la Detección de anomalías y se activan cuando más los necesita.</p><p>El proceso de usar Alertas inteligentes en Customer Journey Analytics es casi idéntico al de usar Alertas inteligentes en Adobe Analytics. Una diferencia clave es que las alertas horarias no están disponibles en Customer Journey Analytics. Esta diferencia se debe a que la ingesta de datos para los distintos tipos de datos de evento que se pueden introducir se completa solo después de un retraso, que generalmente oscila entre 3 y 9 horas después del tiempo de evento de datos.</p><p>(Se han actualizado los siguientes enlaces de documentación)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | sábado, 26 de julio de 2024 |
| **Configuración del administrador para controlar las cuentas y ubicaciones que se usan al exportar informes a la nube** | Una nueva ficha &quot;Configuración de administración&quot; de [ en el Administrador de ubicaciones](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) proporciona a los administradores control sobre si los usuarios pueden crear y editar cuentas y ubicaciones.<p>Esta configuración se aplica cuando los usuarios [configuran cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md) y [configuran ubicaciones de exportación en la nube](/help/components/exports/cloud-export-locations.md).</p><p>Los administradores también pueden limitar los tipos de cuentas que los usuarios pueden crear y utilizar. Los tipos de cuenta incluyen Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake, etc.</p><p>Anteriormente, cualquier usuario podía crear, editar y utilizar cuentas y ubicaciones para cualquier tipo de cuenta.</p> | viernes, 11 de julio de 2024 | sábado, 19 de julio de 2024 |
| **Fuentes de datos de nivel de resumen** | Permite introducir datos de series temporales que no tienen un ID de persona. Estos datos de series temporales se pueden utilizar para varios casos de uso, como:<ul><li>Presentación de indicadores de rendimiento de alto nivel como parte de los datos de nivel de evento o junto a ellos. Esto puede incluir algo tan simple como una fecha y un solo valor de métrica o incluir varias dimensiones y métricas, como impresiones de publicidad, aperturas de correo electrónico, gasto en publicidad, coste del bien vendido, etc.</li><li>Cargar objetivos o metas de forma diaria, semanal, mensual o trimestral, y colocarlos con métricas de nivel de evento para ayudar a visualizar las tendencias de las métricas en comparación con los objetivos o metas de la organización.</li></ul><p>(Se han actualizado los siguientes enlaces de documentación)</p> |  | jueves, 31 de julio de 2024 |
| **Campos derivados - Función de deduplicación** | La [función de deduplicación](/help/data-views/derived-fields/derived-fields.md#deduplicate) de los campos derivados le ayuda a evitar que cuente un valor varias veces. |  | jueves, 17 de julio de 2024 |
| **Aprovisionamiento guiado de análisis para clientes de CJA** | El análisis guiado permite a los usuarios ofrecer datos de alta calidad y perspectivas sobre el recorrido del cliente a través de flujos de trabajo guiados, basados en los datos de canales cruzados de Customer Journey Analytics. <p>Los equipos interfuncionales, desde el marketing hasta el producto, pueden conectarse en tiempo real para utilizar y comprender estos informes.</p><p>Ahora hay disponibles hasta 11 vistas de análisis guiado dentro de los paquetes de CJA. [Más información](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | jueves, 17 de julio de 2024 |
| **Compartir cuentas y ubicaciones que se utilizan para exportar e importar** | Ahora, los usuarios pueden poner las cuentas y ubicaciones que creen a disposición de todos los usuarios de su organización. Solo los propietarios de cuentas y ubicaciones, y los administradores del sistema pueden editar y eliminar cuentas y ubicaciones. Antes, las cuentas y ubicaciones solo las podía utilizar el usuario que las había creado. Esta configuración está disponible cuando los usuarios [configuran cuentas de exportación en la nube](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) y [configuran ubicaciones de exportación en la nube](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 de junio de 2024 | Mediados de julio de 2024 |
| **Los púbicos se publican en una nueva sección “Públicos” en Experience Platform** | Los públicos publicados desde Customer Journey Analytics están ahora disponibles en la nueva sección “Públicos” de Experience Platform.<p>Anteriormente, los públicos publicados desde Customer Journey Analytics estaban disponibles en Experience Platform en la sección “Segmentos”.</p><p>Esta mejora ofrece las siguientes ventajas:</p><ul><li>Los públicos ya no tienen un retraso de 1 hora antes de aparecer en Experience Platform; están disponibles segundos tras su publicación.</li><li>Los públicos se pueden ordenar en Experience Platform mediante la columna “Origen”, que muestra la aplicación desde la que se publicó originalmente el público.</li><li>Las opciones de filtro y ordenación de Experience Platform permiten encontrar las audiencias relevantes más rápidamente.</li></ul> <p>(Vínculo a la documentación a continuación)</p> |  | Por determinar |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-306000; AN-288748; AN-351547; AN-351110

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
