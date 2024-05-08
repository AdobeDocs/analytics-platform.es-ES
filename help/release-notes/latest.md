---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 284c73374ca3fdfc4afbc2824209bebdc764fb64
workflow-type: ht
source-wordcount: '946'
ht-degree: 100%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (abril de 2024)

**Última actualización**: 17 de abril de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 10 de abril de 2024 a mayo de 2024. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Streaming Media: envío de datos de Roku a Adobe Experience Platform Edge** | Ahora, al [instalar Media Analytics con Experience Platform Edge](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), puede utilizar el SDK de Roku de Adobe Experience Platform para enviar datos de medios de streaming a Adobe Experience Platform. |  | 12 de abril de 2024 |
| **Informes mensuales expuestos en el Administrador de actividades de creación de informes** | Cuando se visualiza la actividad de creación de informes de todas las conexiones en el Administrador de actividades de creación de informes, ahora hay disponible un gráfico que muestra los [informes/solicitudes mensuales](https://experienceleague.adobe.com/es/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) que se ejecutaron en el nivel de organización de IMS, tanto para el mes actual como para el anterior.<p>**Nota:** Los datos están disponibles a partir de marzo de 2024. | | 15 de abril de 2024 |
| **Subtítulos inteligentes en cuadros de resultados móviles** | Los [subtítulos inteligentes](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) pueden ayudar a los que no son analistas a dar un mayor sentido a sus datos sin la ayuda de analistas. Ahora están disponibles en los cuadros de resultados de Customer Journey Analytics. |  | 17 de abril de 2024 |
| **Mejora de permisos para componentes de [!UICONTROL Workspace] solo para proyectos** | Anteriormente, si un usuario (usuario A) compartía un proyecto con otro usuario (usuario B) y daba al usuario B acceso de edición al proyecto, el usuario B podía editar el proyecto. Sin embargo, el usuario B no podía editar [!UICONTROL filtros rápidos] incrustados en el proyecto. Esa limitación se ha quitado: el usuario B puede editar [filtros rápidos](/help/components/filters/quick-filters.md) y otros componentes exclusivos del proyecto que están incrustados en el proyecto compartido. |  | 17 de abril de 2024 |
| **Los administradores pueden administrar todas las ubicaciones de su organización** | Una nueva opción de la [página Ubicaciones](https://experienceleague.adobe.com/es/docs/analytics/components/locations/locations-manager) permite a los administradores ver y administrar todas las ubicaciones de la organización. Anteriormente, los administradores solo podían ver y administrar las ubicaciones que habían creado. |  | Abril de 2024 |
| **Adobe Product Analytics: matriz de características** | Impulse las decisiones de inversión al comprender cuáles son su núcleo, potencia, características únicas y cuestionables. [!UICONTROL Matriz de características] mide los eventos por frecuencia de uso frente al % de usuarios activos y lo compara con la mediana de uso. | 17 de abril de 2024 | 30 de abril de 2024 |
| **Adobe Product Analytics: perspectivas mejoradas en el canal** | En la vista [Fricción](https://experienceleague.adobe.com/es/docs/analytics-platform/using/guided-analysis/funnel/friction), las perspectivas escritas se han mejorado para incluir categorías, deltas y descripciones para una mayor comprensión del gráfico y la tabla. | 17 de abril de 2024 | 26 de abril de 2024 |
| **Adobe Product Analytics: vista de retención mejorada** | Se han añadido varias funciones a la vista de tarifas [Retención](https://experienceleague.adobe.com/es/docs/analytics-platform/using/guided-analysis/retention/retention-rates) para obtener perspectivas de retención más profundas y personalizables:<ul><li>Desvincular eventos de inicio y retorno</li><li>Comparar varios eventos de retorno en una sola vista</li><li>Personalice el modelo de retención aplicado con en o después (sin límite), en cada configuración (limitada) y entre corchetes</li><li>Mostrar y ocultar filas de cohorte individuales en el gráfico</li></ul> | 24 de abril de 2024 | 8 de mayo de 2024 |
| **Adobe Product Analytics: comparar eventos dentro de un solo paso de canal** | Ahora puede comparar eventos dentro de un solo paso de canal en la vista [Fricción](https://experienceleague.adobe.com/es/docs/analytics-platform/using/guided-analysis/funnel/friction). Esto resulta especialmente útil cuando el recorrido tiene opciones de paso o un paso en el que se está ejecutando un experimento A/B. | 23 de abril de 2024 | 3 de mayo de 2024 |
| **Transformación de esquemas B2B para persona a cuenta** | Permite transformar conjuntos de datos para que admitan mejor las búsquedas basadas en personas en escenarios de creación de informes B2B de Customer Journey Analytics. Esta capacidad está disponible para conjuntos de datos para esquemas B2B basados en las siguientes clases:<ul><li>Relación de persona de cuenta empresarial de XDM</li><li>Relación de persona de oportunidad empresarial de XDM</li><li>Miembros de lista de marketing empresarial de XDM</li><li>Miembros de campaña empresarial de XDM</li></ul> | | 1 de mayo de 2024 |
| **Detección de bots de Experience Edge** | [Detección de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=es) permite identificar eventos generados por SDK web, SDK móvil y API de servidor como si fueran generados por arañas de web y bots conocidos. | | 1 de mayo de 2024 |
| **Campos derivados: función Siguiente o Anterior** | Estas nuevas funciones le permiten tomar un campo como entrada e identificar el valor n-anterior o n-siguiente para obtener una mejor vista del recorrido del usuario. Esta funcionalidad también se puede combinar con otras funciones en [!UICONTROL Campos derivados], como [!UICONTROL Concatenar], para crear nuevas dimensiones. |  | 1 de mayo de 2024 |
| **Los púbicos se publican en una nueva sección “Públicos” en Experience Platform** | Los públicos publicados desde Customer Journey Analytics están ahora disponibles en la nueva sección “Públicos” de Experience Platform.<p>Anteriormente, los públicos publicados desde Customer Journey Analytics estaban disponibles en Experience Platform en la sección “Segmentos”.</p><p>Esta mejora ofrece las siguientes ventajas:</p><ul><li>Los públicos ya no tienen un retraso de 1 hora antes de aparecer en Experience Platform; están disponibles segundos tras su publicación.</li><li>Los públicos se pueden ordenar en Experience Platform mediante la columna “Origen”, que muestra la aplicación desde la que se publicó originalmente el público.</li><li>Las opciones de filtro y ordenación de Experience Platform le permiten encontrar más rápidamente los públicos relevantes.</li></ul> |  | Mayo de 2024 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-319662; AN-337894; AN-338469; AN-340147; AN-340200; AN-340443; AN-341594; AN-342442; AN-342976; AN-343020; AN-343469; AN-343703; AN-343938; AN-344614; AN-344677;

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Vínculos actualizados en vistas de datos e interfaces de usuario de conexiones** | 15 de febrero | A principios de marzo, Adobe tiene previsto actualizar los siguientes vínculos en la interfaz de usuario del producto de Customer Journey Analytics. Actualice sus marcadores según corresponda.<ul><li>**Página de vistas de datos, administrador de vistas de datos**: [vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Crear nueva vista de datos**: [vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Editar vista de datos**: [vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Nuevo vínculo](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Administrador de conexiones**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Información de conexiones**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Editar conexión**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Crear nueva conexión**: [Vínculo existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Nuevo vínculo](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
