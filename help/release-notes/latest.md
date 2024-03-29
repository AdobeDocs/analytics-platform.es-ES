---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 20e99275a42312ed974ac4c1af28ede73180e748
workflow-type: ht
source-wordcount: '957'
ht-degree: 100%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (marzo de 2024)

**Última actualización**: 20 de marzo de 2024

Estas notas de la versión abarcan el período de lanzamiento de finales del 13 de marzo de 2024 a abril de 2024. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nueva columna disponible en la página de aterrizaje Proyectos** | La columna **[!UICONTROL Último uso]** está disponible ahora al ver la pestaña Proyectos en la [página de aterrizaje del Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=es). <p>Esta información puede ayudarle a determinar si un proyecto es valioso para los usuarios de su organización, ya que muestra la fecha y la hora en que se abrió por última vez. Anteriormente, la columna **[!UICONTROL Último uso]** solo estaba disponible en el Administrador de métricas calculadas, el Administrador de segmentos y el Administrador de alertas.</p> |  | 13 de marzo de 2024 |
| **Métricas de uso** | La [interfaz de métricas de uso](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=es) muestra el uso de filas ingeridas y notificables en todas las conexiones. Esta interfaz permite determinar si el uso del Customer Journey Analytics cumple con lo acordado contractualmente. |  | 13 de marzo de 2024 |
| **Sistema de informes de Media Analytics: promedio de público por minuto (AMA)** | El panel Promedio de público por minuto ya está disponible en CJA. Los clientes de Media Analytics pueden utilizar el panel Público medio por minuto para comprender mejor el consumo medio de su contenido.  <p>La audiencia media por minuto permite comparar la programación de cualquier género o duración. Además, los clientes pueden comparar o anexar este público medio por minuto digital a métricas de minuto promedio de televisión lineales. </p><p> Este panel proporciona más flexibilidad para medir el promedio de público en periodos de tiempo personalizados, así como cuando la clasificación de duración se ha actualizado después del hecho.</p><p>Para obtener más información, consulte el [panel Público medio por minuto de medios](/help/analysis-workspace/c-panels/average-minute-audience-panel.md).</p> |  | 12 de marzo de 2024 |
| **Transformación de esquemas B2B para persona a cuenta** | Permite transformar conjuntos de datos para que admitan mejor las búsquedas basadas en personas en escenarios de creación de informes B2B de Customer Journey Analytics. Esta capacidad está disponible para conjuntos de datos para esquemas B2B basados en las siguientes clases:<ul><li>Relación de persona de cuenta empresarial de XDM</li><li>Relación de persona de oportunidad empresarial de XDM</li><li>Miembros de lista de marketing empresarial de XDM</li><li>Miembros de campaña empresarial de XDM</li></ul> | | 26 de marzo de 2024 |
| **Uso de Report Builder incluido en la columna &quot;Utilizado en&quot; del Administrador de métricas calculadas y del Administrador de filtros** | Al ver la columna **Utilizado en** en el Administrador de métricas calculadas o en el Administrador de filtros, los datos de uso ya están disponibles para Report Builder.<p>Anteriormente, los datos de uso del Administrador de filtros solo estaban disponibles para alertas, proyectos, proyectos programados y métricas calculadas; mientras que los datos de uso del Administrador de métricas calculadas solo estaban disponibles para alertas, proyectos y proyectos programados.</p> |  | Finales de marzo o principios de abril |
| **Adobe Product Analytics: comparar eventos dentro de un solo paso de canal** | En la vista Canal: fricción puede comparar eventos dentro de un solo paso de canal. Esto resulta especialmente útil cuando el recorrido tiene opciones de paso o un paso en el que se está ejecutando un experimento A/B. | 29 de marzo de 2024 | 12 de abril de 2024 |
| **Los administradores pueden administrar todas las ubicaciones de su organización** | Una nueva opción de la pestaña Ubicaciones (en la página Componentes > Exportaciones) permite a los administradores ver y administrar todas las ubicaciones de la organización.  <p>Una nueva opción de la pestaña Cuentas de ubicación (en la página Componentes > Exportaciones) permite a los administradores ver y administrar todas las cuentas de la organización.</p><p>Anteriormente, los administradores solo podían ver y administrar las ubicaciones y cuentas que habían creado.</p> | | Abril de 2024 |
| **Los púbicos se publican en una nueva sección &quot;Públicos&quot; en Experience Platform** | Los públicos publicados desde Customer Journey Analytics están ahora disponibles en la nueva sección “Públicos” de Experience Platform. Anteriormente, los públicos publicados desde Customer Journey Analytics estaban disponibles en Platform en la sección “Segmentos”. Esta mejora ofrece las siguientes ventajas:<ul><li>Los públicos ya no tienen un retraso de 1 hora antes de aparecer en Platform; están disponibles segundos tras su publicación.</li><li>Los públicos se pueden ordenar en Platform mediante la columna &quot;Origen&quot;, que muestra la aplicación desde la que se publicó originalmente el público.</li><li>Las opciones de filtro y ordenación de Platform le permiten encontrar más rápidamente los públicos relevantes.</li></ul>Para obtener más información, consulte la sección [Usar públicos de Customer Journey Analytics en Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=es#audiences-aep). |  | Abril de 2024 |
| **Detección de bots de Experience Edge** | [Detección de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=es) permite identificar eventos generados por SDK web, SDK móvil y API de servidor como si fueran generados por arañas de web y bots conocidos. | | 29 de abril de 2024 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-340429; AN-341544; AN-341974; AN-342176; AN-342391

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Vínculos actualizados en vistas de datos e interfaces de usuario de conexiones** | 15 de febrero | A principios de marzo, Adobe tiene previsto actualizar los siguientes vínculos en la interfaz de usuario del producto de Customer Journey Analytics. Actualice sus marcadores según corresponda.<ul><li>**Página de vistas de datos, administrador de vistas de datos**: [vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Crear nueva vista de datos**: [vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Editar vista de datos**: [vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Nuevo vínculo](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Administrador de conexiones**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Información de conexiones**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Editar conexión**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Crear nueva conexión**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Adiciones de miembros de objeto de API de Adobe | 17 de enero de 2024 | Adobe puede añadir miembros de solicitud y respuesta opcionales (pares de nombre/valor) a objetos de API existentes sin previo aviso ni cambios en las versiones. Estas adiciones deben ser cambios importantes para la implementación. Adobe recomienda que se consulte la documentación de la API de cualquier herramienta de terceros que se integre con nuestras API para que dichas adiciones se ignoren en el procesamiento si no se comprenden. Adobe no quitará los parámetros ni añadirá los parámetros necesarios sin antes proporcionar una notificación estándar mediante las notas de la versión. |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
