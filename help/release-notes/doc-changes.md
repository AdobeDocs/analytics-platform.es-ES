---
title: Actualizaciones de la documentación de Customer Journey Analytics
description: Enumera las actualizaciones de contenido para la documentación de Customer Journey Analytics establecida desde diciembre de 2019.
exl-id: 1cfb9810-e083-4a68-9c58-295e674da8d7
solution: Customer Journey Analytics
feature: Release Notes
source-git-commit: a4b838f7813d78681eba072e4febd90ba0c7111d
workflow-type: tm+mt
source-wordcount: '4016'
ht-degree: 72%

---

# Actualizaciones de la documentación de Customer Journey Analytics

Se han realizado las siguientes actualizaciones en la documentación de Customer Journey Analytics desde su creación.

## 2024

| Función | Descripción |
| --- | --- |
| **Agosto de 2024** | |
| Ejemplo de proyecto B2B | Se ha agregado un [caso de uso](/help/use-cases/b2b/example.md) que documenta cómo configurar y generar informes sobre datos B2B basados en el nivel de perfil (persona) en Customer Journey Analytics, usando la nueva funcionalidad [transformar conjuntos de datos para búsquedas B2B](/help/connections/transform-datasets-b2b-lookups.md). |
| Casos de uso de exportación de datos actualizados | Se han agregado ejemplos de consultas más detallados a [Servicio de consultas (Data Distiller) y exportar conjuntos de datos](/help/use-cases/data-export/queryservice-export-datasets.md) para ilustrar cómo aplicar correctamente la atribución entre sesiones mediante una ventana retrospectiva. |
| Datos de resumen | Se agregó documentación sobre [datos de resumen](/help/data-views/summary-data.md), [configuración del componente de grupo de datos de resumen](/help/data-views/component-settings/summary-data-group.md) y un [caso de uso de datos de resumen](/help/use-cases/data-views/summary-data.md). |
| **Julio de 2024** | |
| Se ha añadido información sobre las métricas calculadas rápidas | Se ha actualizado la información de [Métricas](/help/components/apply-create-metrics.md) para aclarar la diferencia entre las [métricas calculadas que se crean en el creador de métricas calculadas](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) y las [que se crean como métricas calculadas rápidas dentro de un solo proyecto](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). También se han añadido más detalles acerca de cómo se crean las métricas calculadas rápidas.<p>Las métricas calculadas que se crean en el creador de métricas calculadas están disponibles en la lista de componentes y se pueden aplicar a proyectos de toda la organización, mientras que las métricas calculadas que se crean como métricas calculadas rápidas solo están disponibles dentro del proyecto en el que se crearon.</p><p>También se ha actualizado la información de [Generar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) para hacer aclaraciones similares.</p> |
| Función de deduplicación de campo derivada | Se ha agregado documentación sobre la función [deduplicar](/help/data-views/derived-fields/derived-fields.md#deduplicate) del campo derivado. |
| Mensajes de error comunes actualizados | Se han realizado actualizaciones menores de los [mensajes de error comunes](/help/analysis-workspace/workspace-faq/error-messages.md). |
| **Junio de 2024** | |
| Se ha actualizado el nombre del producto que hace referencia a las funciones de medios de streaming | Se han reemplazado las instancias de “Media Analytics” y “Streaming Media” por el nombre de “Complemento de colección Streaming Media” al hacer referencia al conjunto de funciones de medios de streaming que recopilan datos de medios de streaming y los muestran en Analysis Workspace. <p>Estas actualizaciones están disponibles en toda la documentación de Customer Journey Analytics, así como en [documentación de Streaming Media Collection](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-overview).</p> |
| Identificación basada en gráficos | Se ha actualizado y reestructurado la [documentación de vinculación](/help/stitching/overview.md) con la introducción de la vinculación basada en gráficos. |
| Asistente de IA | Se agregó [documentación](../ai-assistant.md) en el Asistente de IA para Customer Journey Analytics. |
| Transformar conjuntos de datos para búsquedas B2B | Se agregó documentación sobre cómo admitir [búsquedas basadas en personas en datos B2B](/help/connections//transform-datasets-b2b-lookups.md) (incluidas cuentas, oportunidades, listas de marketing y campañas) mediante la transformación de conjuntos de datos de búsqueda B2B. |
| Funciones de campo derivadas y plantillas de función | Se ha agregado documentación sobre las funciones de campo derivadas adicionales ([Math](/help/data-views/derived-fields/derived-fields.md#math), [Next o Previous](/help/data-views/derived-fields/derived-fields.md#next-or-previous), y [Summarize](/help/data-views/derived-fields/derived-fields.md#summarize)) y [plantillas de función](/help/data-views/derived-fields/derived-fields.md#function-templates). |
| **Mayo de 2024** | |
| Integración de Target | Se agregó [artículo a la sección de integración de Adobe](/help/integrations/at.md) sobre cómo integrar Target con el Customer Journey Analytics. |
| Información necesaria al exportar informes de Customer Journey Analytics a Google Cloud Platform mientras se utilizan restricciones de directivas de la organización | Se ha agregado el identificador de organización de Google Cloud Platform propiedad del Adobe a la documentación de [Configuración de ubicaciones de exportación en la nube](/help/components/exports/cloud-export-locations.md) para exportar informes de Customer Journey Analytics a Google Cloud Platform. <p>Esta información solo es necesaria para las organizaciones que utilizan [Restricciones de política de organización](https://cloud.google.com/storage/docs/org-policy-constraints) en Google Cloud Platform.</p> |
| Documentación sobre la adición de componentes a proyectos | Se ha añadido información general sobre cómo [añadir distintos tipos de componentes a los proyectos en Analysis Workspace](/help/components/use-components-in-workspace.md). |
| Casos de uso de exportación de datos | Conjunto de nuevos artículos que describen [casos de uso de exportación de datos](/help/use-cases/data-export/overview.md) y cómo usar las funcionalidades de Experience Platform y Customer Journey Analytics para implementar estos casos de uso |
| Nueva documentación para actualizar de Adobe Analytics a Customer Journey Analytics | Para las organizaciones que actualizan de Adobe Analytics a Customer Journey Analytics, existen varias opciones de actualización y muchas consideraciones que se deben tener en cuenta según la implementación de Adobe Analytics actual y los objetivos a largo plazo de una organización.<p>Ya hay disponibles nuevos recursos de documentación para ayudarle a comprender mejor:</p><ul><li>Las distintas rutas de actualización existentes</li><li>Qué rutas de actualización están disponibles según la implementación de Adobe Analytics actual de una organización</li><li>Las ventajas y desventajas de cada ruta de actualización</li><li>Guía paso a paso para cada ruta de actualización</li><li>Consideraciones para administrar datos históricos</li><li>¡Y mucho más!</li></ul><p>[Introducción a la actualización a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md).</p> |
| Se ha actualizado la documentación sobre intervalos de fechas personalizados | Capturas de pantalla y procedimientos actualizados relacionados con la [creación de intervalos de fechas personalizados](/help/components/date-ranges/custom-date-ranges.md) para que coincida con las características y el diseño actuales del producto. |
| Información general sobre los Dimension | Se ha agregado información sobre [dimensiones](/help/components/dimensions/overview.md). |
| Ejemplos de conectores de origen | Se agregaron ejemplos de conectores de origen que están disponibles al describir cómo [usar un conector de origen](/help/data-ingestion/sources.md#use-a-source-connector) para la ingesta de datos. |
| **Abril de 2024** | |
| Técnicas estadísticas de pronóstico | Se agregó un artículo que describe las [técnicas estadísticas utilizadas en el servicio de pronóstico](../analysis-workspace/c-forecast/statistics-forecasting.md). |
| Se ha añadido información que recomienda la exportación de tabla completa para dimensiones de alta cardinalidad | Se ha agregado una viñeta en [Prácticas recomendadas para dimensiones de alta cardinalidad](/help/components/dimensions/high-cardinality.md) para recomendar el uso de la exportación de tabla completa para dimensiones de alta cardinalidad. |
| Se ha añadido documentación sobre Subtítulos inteligentes en cuadros de resultados móviles | [Subtítulos inteligentes](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) pueden ayudar a los no analistas a entender mejor sus datos sin la ayuda de los analistas. |
| Nueva documentación para las funciones de Adobe Product Analytics | <ul><li>[Matriz de características](https://experienceleague.adobe.com/es/docs/analytics-platform/using/guided-analysis/funnel/friction)</li><li>[tasas de retención mejoradas](https://experienceleague.adobe.com/es/docs/analytics-platform/using/guided-analysis/retention/retention-rates)</li><li>[Perspectivas mejoradas en el canal](https://experienceleague.adobe.com/es/docs/analytics-platform/using/guided-analysis/funnel/friction)</li><li>Comparación de eventos dentro de un solo paso de canal</li></ul> |
| **Marzo de 2024** | |
| La información de uso relativa a la columna “Utilizado en” solo está disponible a partir de septiembre de 2023. | Se ha aclarado que la información de uso relativa a la columna **Utilizado en** en la [página de aterrizaje de proyectos](/help/getting-started/landing.md) solo se remonta hasta septiembre de 2023. |
| Se ha añadido documentación sobre la mejora de los permisos para componentes de Workspace solo de proyecto | Si comparte un proyecto con otros usuarios, esos usuarios pueden editar [filtros rápidos](/help/components/filters/quick-filters.md) y otros componentes solo de proyecto incrustados en el proyecto compartido. |
| **Febrero de 2024** | |
| Actualizaciones de la documentación sobre proyectos compartidos | Se agregó información sobre cómo [ver proyectos que se han compartido con usted](/help/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you).<p>También se ha simplificado la información sobre [uso compartido de proyectos individuales o múltiples](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).</p> |
| Requisitos de permiso añadidos para cargar archivos en Azure SAS y Azure RBAC al configurar ubicaciones de exportación en la nube | Se agregaron requisitos de permiso exactos para cargar archivos en Azure SAS y Azure RBAC al [configurar cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md) y [configurar ubicaciones de exportación en la nube](/help/components/exports/cloud-export-locations.md). |
| Se han añadido requisitos de permiso para cargar archivos en los bloques de ARN de la función Amazon S3 y GCP al configurar ubicaciones de exportación en la nube | Se agregaron requisitos de permiso exactos para cargar archivos en los bloques de ARN de la función Amazon S3 y Google Cloud Platform al [configurar ubicaciones de exportación en la nube](/help/components/exports/cloud-export-locations.md). |
| Se ha aclarado que los administradores de productos siempre tienen acceso para exportar tablas completas | Se han realizado los siguientes cambios para aclarar que los usuarios asignados a la función Administrador de productos tienen acceso para exportar tablas completas desde Analysis Workspace de forma predeterminada: <ul><li>Se ha agregado una nueva viñeta a [Permisos predeterminados del administrador de productos](/help/technotes/access-control.md#product-admin-default-permissions).</li><li>Se agregó una nota bajo los [requisitos mínimos para exportar tablas completas a la nube](/help/analysis-workspace/export/export-cloud.md#minimum-requirements).</li></ul> |
| Se ha aclarado que los segmentos se vuelven a crear durante la migración de componentes desde Adobe Analytics | En la [Guía del usuario para usuarios de Adobe Analytics](/help/getting-started/aa-to-cja-user.md), se aclaró que los segmentos se vuelven a crear automáticamente en Adobe Analytics como parte del proceso de migración de componentes y no es necesario volver a crearlos manualmente. |
| Detalles de registro omitidos | Se ha añadido documentación sobre la funcionalidad de detalles de registros omitidos en Conexiones. Consulte [Detalles de conexión](../connections/manage-connections.md#connection-details) para obtener más información. |
| **Enero de 2024** | |
| Previsión | Se agregó documentación sobre [forecasting](../analysis-workspace/c-forecast/forecasting.md), la nueva función de Analysis Workspace para pronosticar una métrica estándar o calculada con cualquier granularidad de tiempo admitida (por hora, diario, semanal, mensual y anual) para tablas de forma libre y gráficos de líneas. |
| Se ha actualizado la documentación para agregar cuentas y ubicaciones al exportar tablas completas | Se ha actualizado la documentación para reflejar actualizaciones menores de la interfaz al configurar una nueva cuenta o ubicación al [exportar tablas completas desde Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace).<p>Ahora hay disponible una nueva opción [!UICONTROL **Agregar cuenta**] en el menú desplegable [!UICONTROL **Cuenta**]. La opción [!UICONTROL **Agregar ubicación**] que antes estaba disponible como botón junto al menú desplegable [!UICONTROL **Nombre de ubicación**] ya está disponible en el propio menú. |
| Nueva información de migración de componentes al migrar desde Adobe Analytics | Se ha agregado información a [Evolución desde Adobe Analytics](/help/getting-started/aa-to-cja.md) que hace referencia a las nuevas capacidades de [migración de componentes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=es) que se documentan en la Guía de administración de Adobe Analytics. |
| Se ha aclarado que cierta información solo está disponible para administradores | Se ha agregado información para indicar que las columnas &quot;Último uso&quot; y &quot;Utilizado en&quot; que se describen en [Administrador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md) y [Administrador de filtros](/help/components/filters/manage-filters.md) solo están disponibles para los administradores del sistema. |
| Permisos necesarios para exportar conjuntos de datos | Se agregó información que explica los [permisos necesarios](/help/technotes/access-control.md) para exportar conjuntos de datos a destinos de nube. |
| Administrar conexiones | Se ha actualizado el artículo [Administrar conexiones](../connections/manage-connections.md), basado en los comentarios de los clientes. |
| Campos derivados | Se ha agregado un resumen de la función [limitaciones](/help/data-views/derived-fields/derived-fields.md#limitations) y una explicación sobre cómo determinar el número de [operadores](/help/data-views/derived-fields/derived-fields.md#operators) utilizados en una función. |

{style="table-layout:auto"}


## 2023

| Función | Descripción |
| --- | --- |
| **Diciembre de 2023** | |
| Centros de datos | Se agregó un artículo sobre el Customer Journey Analytics [ubicaciones de alojamiento](../technotes/data-centers.md). |
| Mecanismos de protección | Se ha agregado un artículo que enumera el Customer Journey Analytics [protecciones](../technotes/guardrails.md). |
| Actualizaciones de conversión de moneda | Se ha aclarado la documentación sobre cómo [configurar la conversión de moneda](/help/data-views/component-settings/format.md). |
| Actualizaciones en la documentación de Detección de anomalías | Anteriormente, la documentación de Detección de anomalías se encontraba en una sección sobre Analista virtual. Se han realizado los siguientes cambios: <ul><li>El término Analista virtual se ha eliminado de la documentación.</li><li>La sección sobre [Detección de anomalías](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) se ha movido directamente debajo de la sección Analysis Workspace.</li></ul> |
| **Octubre de 2023** | |
| Usar un campo derivado para establecer metas/objetivos | Se ha agregado [caso de uso](../use-cases/goals-using-derived-fields.md) artículo que ilustra cómo usar campos derivados para establecer metas/objetivos e informar sobre estos. |
| Exportar tablas completas a la nube | Se ha añadido documentación sobre la exportación de tablas completas con millones de filas de Workspace a destinos de nube. <p>La exportación de tablas completas ofrece un envío único o programado de tablas de datos diseñadas en Workspace con soporte para hasta cinco desgloses, cinco métricas, filtros y métricas calculadas, todo en una tabla concatenada. Es la evolución de los informes de Data Warehouse en Adobe Analytics, con muchas funciones nuevas y a menudo solicitadas que no están disponibles en Data Warehouse en la actualidad.</p><p>Para obtener más información, consulte [Exportar informes de Customer Journey Analytics a la nube](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=es). |
| Administrador de actividades de creación de informes | Se ha agregado documentación para el Administrador de actividades de creación de informes. <p>El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Proporciona a los administradores una visibilidad detallada del consumo de creación de informes para diagnosticar y corregir fácilmente los problemas de capacidad durante las horas de mayor actividad de la creación de informes.</p> <p>Se agregaron los siguientes artículos nuevos:<ul><li>[Información general del Administrador de actividades de creación de informes](/help/reporting-activity-manager/reporting-activity-overview.md)</li><li>[Ver actividad de creación de informes en el Administrador de actividades de creación de informes](/help/reporting-activity-manager/reporting-activity.md)</li><li>[Cancelar solicitudes en el Administrador de actividades de creación de informes](/help/reporting-activity-manager/reporting-activity-cancel-requests.md)</ul> |
| Nuevas columnas en páginas de administración | Se han documentado nuevas columnas que ahora están disponibles en [Administrador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html?lang=es) y en [Administrador de filtros](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html?lang=es). |
| Comparación con Adobe Analytics | Se ha agregado una [página de información general](../getting-started/aa-vs-cja/overview.md) como introducción para comparar y comprender las diferencias entre Customer Journey Analytics y Adobe Analytics. |
| Funcionalidad adicional de campos derivados | Documentación actualizada para la nueva función [`Lookup`](/help/data-views/derived-fields/derived-fields.md#lookup). |
| **Septiembre de 2023** | |
| Estructura actualizada de los artículos del panel Tiempo empleado en la reproducción de medios | Se ha eliminado la carpeta denominada Tiempo empleado en la reproducción de medios y se ha combinado el contenido de la carpeta en un solo artículo: [Panel Tiempo empleado en la reproducción de medios](/help/analysis-workspace/c-panels/media-playback-time-spent.md). <p>Este cambio está más en línea con la documentación de otros paneles.</p> |
| Funcionalidad adicional de campos derivados | Documentación actualizada para las nuevas funciones [`Lowercase`](/help/data-views/derived-fields/derived-fields.md#lowercase) y [`Trim`](/help/data-views/derived-fields/derived-fields.md#trim) y para las funcionalidades CSV adicionales agregadas a la función [`Classify`](/help/data-views/derived-fields/derived-fields.md#classify). |
| Recopilación de datos regionales | Actualizado [FAQ](../getting-started/cja-faq.md#12-regional-data-collection) con información sobre la recopilación de datos regionales al utilizar Customer Journey Analytics. |
| **Agosto de 2023** | |
| Panel Tiempo invertido en la reproducción de medios | Contenido actualizado del [Panel Tiempo invertido en la reproducción de medios](/help/analysis-workspace/c-panels/media-playback-time-spent.md) para mejorar la legibilidad. |
| Mejoras de Report Builder | Contenido actualizado de [Programación de libros](/help/report-builder/schedule-reportbuilder.md) para proporcionar información para descargar tareas programadas. Contenido actualizado de [Creación de un bloque de datos](/help/report-builder/create-a-data-block.md) para proporcionar información sobre el uso de Fecha de inicio como dimensión. |
| Se ha movido contenido sobre la gestión de proyectos programados | Se ha creado un nuevo artículo en la Guía de componentes de Analytics llamado [Proyectos programados](/help/components/scheduled-projects-manager.md). Este contenido se encontraba anteriormente en [Programar proyectos](/help/analysis-workspace/export/t-schedule-report.md) en la Guía de herramientas de Analytics. |
| Compatibilidad con las funciones de Adobe Customer Journey Analytics | Se ha añadido más información en la tabla *Compatible de una nueva forma* sobre las funcionalidades de la definición de sesiones en Customer Journey Analytics en comparación con Adobe Analytics. [Más información](../getting-started/aa-vs-cja/cja-aa.md#supported-in-a-new-way) |
| Evolución desde Adobe Analytics | Se ha actualizado la sección *reconfiguración de canales de marketing* con una referencia a la plantilla de función de canales de marketing de Campos derivados. [Más información](../getting-started/aa-to-cja.md#3-reconfigure-your-marketing-channels) |
| Guías de inicio rápido de ingesta de datos para aplicaciones móviles y otras plataformas | Se han añadido guías de inicio rápido de ingesta de datos adicionales que describen cómo ingerir y utilizar datos de aplicaciones móviles u otras plataformas (como aplicaciones de escritorio, juegos en consolas, aplicaciones en decodificadores y dispositivos de IoT) en Customer Journey Analytics. [Más información](../data-ingestion/data-ingestion.md) |
| **Julio de 2023** | |
| Configuración de sesión | Se ha añadido un tema a esta configuración de vista de datos. [Más información](/help/data-views/session-settings.md) |
| Adobe Product Analytics | Adobe Product Analytics es una nueva forma de interactuar con los datos y las perspectivas en canales múltiples en Customer Journey Analytics. Estas nuevas funcionalidades permiten a los equipos de productos autogestionar datos y perspectivas sobre su experiencia con el producto mediante flujos de trabajo de [análisis guiados.](/help/guided-analysis/overview.md) |
| Campos derivados | Un [campo derivado](/help/data-views/derived-fields/derived-fields.md) permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. |
| Compatibilidad de búsqueda ampliada para datos de perfil y búsqueda | Proporciona la posibilidad de añadir conjuntos de datos como búsquedas de campos dentro de conjuntos de datos de perfil o de búsqueda. Anteriormente, solo se admitían conjuntos de datos de eventos. [Más información](/help/connections/create-connection.md) |
| Mejoras de Report Builder | <ul><li>[Filtre desde la celda para varios bloques de datos](/help/report-builder/select-data-view.md)</li><li>[Muestre y oculte encabezados de fila y columna](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=es#build-the-data-block)</li></ul> |
| búsquedas geográficas de Edge Network | [Configuración de secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=es) muestra un servicio de búsqueda geográfica que proporciona datos geográficos unificados. |
| **Junio de 2023** | |
| Vinculación y análisis en canales múltiples | En previsión de los próximos cambios para habilitar la vinculación y aclarar mejor cómo se puede elevar el análisis entre canales mediante la vinculación, la documentación relacionada con la funcionalidad de Análisis entre canales se edita para hacer referencia a [análisis en canales múltiples](../use-cases/cross-channel/cross-channel.md) como la capacidad de Customer Journey Analytics y el caso de uso, y [Vinculación](../stitching/overview.md) como una funcionalidad importante para lograrlo. |
| Acceso de Power BI y Tableau a vistas de datos de Customer Journey Analytics | La extensión de Customer Journey Analytics BI permite el acceso SQL a las vistas de datos definidas en Customer Journey Analytics. [Más información](/help/data-views/bi-extension.md) |
| Vistas de datos de Adobe Journey Optimizer | Las personas administradoras de Customer Journey Analytics tienen acceso a algunas vistas de datos adicionales en Customer Journey Analytics, tituladas &quot;Vista de datos de AJO (nombre de zona protegida)&quot;. [Más información](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/content-management/content-experiment/reporting-configuration). |
| Conversión de moneda | Documentación actualizada para compatibilidad de [conversión de moneda](../data-views/component-settings/format.md#currency). |
| Actualizaciones de métricas calculadas | Se han introducido las siguientes actualizaciones en la documentación de las métricas calculadas para alinearla con la funcionalidad actual de Customer Journey Analytics: <ul><li>Se ha actualizado la lista de [métricas calculadas predeterminadas](/help/components/calc-metrics/default-calcmetrics.md) disponible en Customer Journey Analytics</li><li>Capturas de pantalla y procedimientos actualizados en varios artículos de métricas calculadas </li></ul> |
| **Mayo de 2023** | |
| Documentación sobre vinculación profunda (aplicación móvil) | Permite a los usuarios enviar vínculos a cuadros de resultados que los llevarán directamente al cuadro de resultados de la aplicación. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=es#share-scorecards-using-a-shareable-link) |
| Documento sobre “Selección de vista de datos de la celda” en Report Builder | Esta función permite a los usuarios seleccionar la vista de datos para un bloque de datos de una celda. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=es) |
| Documentación sobre la actualización de la pantalla de inicio de la aplicación de paneles de Analytics (aplicación móvil) | La nueva pantalla de inicio actualizada le permite ver todos los cuadros de resultados en una lista consolidada de cuadros de resultados. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html?lang=es#use-dashboards) |
| Actualización de optimización | Artículo actualizado sobre [Optimización del rendimiento de Customer Journey Analytics](/help/technotes/optimizing-performance.md) |
| Información general de Analysis Workspace | Se ha actualizado la [información general de Analysis Workspace](/help/analysis-workspace/home.md) para incluir información más general y vínculos a contenido relevante. |
| Crear proyectos | Se ha creado un nuevo artículo que explica en detalle cómo [Crear proyectos](/help/analysis-workspace/build-workspace-project/create-projects.md) en Analysis Workspace. |
| Ordenar componentes en el carril izquierdo | Se ha añadido información sobre la ordenación de la lista de componentes en el carril izquierdo. Consulte la sección &quot;Buscar, filtrar y ordenar la lista de componentes&quot; en [Información general de componentes](/help/components/overview.md). |
| Eliminación de filas que contienen dimensiones dinámicas de una tabla de forma libre | Se ha añadido información acerca de cómo eliminar rápidamente filas específicas que contienen dimensiones dinámicas mediante el icono x. Consulte la sección &quot;Excluir rápidamente filas específicas de una tabla&quot; en [Filtrado y ordenación de tablas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| Botón para añadir una visualización dentro de un panel | Se ha agregado información sobre un nuevo botón en la parte inferior de cada panel en Analysis Workspace que le permite agregar rápidamente una visualización. Consulte la sección “Adición de visualizaciones a un panel” en [Información general sobre visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md). |
| Documentación sobre pies de ilustración inteligentes | Enriquezca las historias para los usuarios con resúmenes en lenguaje natural de una visualización de [Línea](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| Campos derivados | Documentación añadida para la funcionalidad de [campos derivados](../data-views/derived-fields/derived-fields.md). |
| **Abril de 2023** |  |
| Vídeo sobre el uso de filtros como dimensiones | Se ha actualizado el vídeo sobre el uso de filtros como dimensión. <p>Este vídeo está vinculado desde la página [Crear filtros](/help/components/filters/create-filters.md).</p> <p>A continuación se muestra un vínculo directo al vídeo: [Usar filtros como dimensiones en Analysis Workspace](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/use-filters-as-dimensions.html?lang=es).</p> |
| Documentación del filtro | Se ha añadido un artículo sobre el uso del [Generador de filtros](/help/components/filters/filter-builder.md). <p>Documentación optimizada en [Crear filtros](/help/components/filters/create-filters.md) e [Información general de Filtros](/help/components/filters/filters-overview.md).</p> |
| Actualización de la documentación del panel Experimentación | Se ha añadido una sección en [interpretación de dimensiones no aleatorias](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html#non-randomized). |
| Filtros de proyecto (filtros específicos y rápidos) | Se ha simplificado la documentación acerca de los filtros del proyecto y se ha eliminado la información duplicada. Los pasos para crear filtros ad hoc se combinan ahora con los pasos para [crear filtros rápidos](/help/components/filters/quick-filters.md). |
| **Marzo de 2023** | |
| Integración de datos de gestión de decisiones | Se ha añadido contenido que explica cómo [integrar datos de administración de decisiones de Adobe Journey Optimizer en Customer Journey Analytics](/help/integrations/ajo-od.md). |
| Creación de historias de datos en cuadros de resultados móviles | Una [historia de datos](/help/mobile-app/create-scorecard.md#create-data-stories) es una colección de puntos de datos de apoyo, contexto empresarial y métricas relacionadas creada en torno a un tema o métrica central. |
| Compatibilidad de funciones actualizadas | [Compatibilidad con funciones de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md) actualizada con una tabla de funciones disponibles en Customer Journey Analytics, pero no disponibles ni admitidas en AA. |
| Métricas calculadas predeterminadas | Se ha añadido contenido que explica las [métricas calculadas predeterminadas que proporciona Adobe](/help/components/calc-metrics/default-calcmetrics.md). |
| Diccionario de datos | <p>Se agregó nueva documentación para el diccionario de datos, incluida [Información general](/help/components/data-dictionary/data-dictionary-overview.md), [Visualización](/help/components/data-dictionary/view-data-dictionary.md), [Edición](/help/components/data-dictionary/edit-entries-data-dictionary.md) y [Monitorización](/help/components/data-dictionary/monitor-data-dictionary-health.md) del diccionario de datos.</p><p>La información de [Adición de descripciones de componentes](/help/components/add-component-descriptions.md) se ha actualizado para tener en cuenta la funcionalidad del diccionario de datos.</p> |
| Uso compartido de vínculos para proyectos (no se requiere inicio de sesión) | <p>Se ha actualizado la documentación existente para explicar cómo compartir un vínculo de solo lectura de un proyecto con personas que no tienen acceso a Analysis Workspace.</p> <p>La documentación de usuario actualizada incluye el [Uso compartido de proyectos](/help/analysis-workspace/curate-share/share-projects.md) y la [Creación de vínculos que se pueden compartir](/help/analysis-workspace/curate-share/shareable-links.md).</p> <p>Se han añadido opciones para administradores a [Preferencias](/help/analysis-workspace/user-preferences.md).</p> |
| **Febrero de 2023** | |
| Comparar soluciones de Customer Journey Analytics con las soluciones de BI | Nuevo documento sobre una [comparación](../getting-started/cja-vs-bi.md) de Customer Journey Analytics con las soluciones típicas de BI. |
| Actualización de la documentación de Audiences | Nueva sección sobre [consideraciones de latencia](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency). |
| Actualización de la documentación de Audiences | Después de crear un público, Adobe crea un segmento de streaming de Experience Platform [ para cada nuevo público de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=es#after-audience-created). |
| Calendarios e intervalos de fechas del Espacio de trabajo | Se ha actualizado el contenido para describir intervalos de fechas relativos, actualizaciones de cálculo de fórmula y cambios en la IU del calendario. Consulte [Acerca de los intervalos de fechas relativos del panel](/help/components/date-ranges/calendar.md#relative-panel-dates). |
| Cuadros de resultados móviles | Nueva sección de documentación para describir cómo mostrar y ocultar intervalos de fechas de comparación. Consulte [Mostrar intervalos de fechas de comparación](/help/mobile-app/create-scorecard.md#show-comparison-dates) en Customer Journey Analytics. |
| **Enero de 2023** | |
| Filtrado y ordenación de tablas | Se ha actualizado el contenido (incluyendo procedimientos y explicaciones de las opciones disponibles) en el artículo [Filtrado y ordenación de tablas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). Se ha cambiado el nombre de este artículo de “Paginación, filtrado y ordenación de tablas”. |
| Guías de inicio rápido sobre la ingesta de datos | Nueva sección de documentación sobre la [ingesta y uso de datos](/help/data-ingestion/data-ingestion.md) en Customer Journey Analytics. |
| Carpetas de Workspace | Páginas específicas para la [administración de carpetas](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Preferencias de usuario de Workspace | Muchas preferencias de usuario adicionales están ahora disponibles en [Preferencias](/help/analysis-workspace/user-preferences.md). |
| Guardado automático para proyectos de Workspace | Contenido actualizado para incluir la funcionalidad de guardado automático en [Guardar proyectos](/help/analysis-workspace/build-workspace-project/save-projects.md). |
| Página de aterrizaje | Nuevas actualizaciones de la página de aterrizaje [página de aterrizaje](/help/getting-started/landing.md). |
| Programar libros de trabajo | Página dedicada para describir cómo [Programar Workbooks](/help/report-builder/schedule-reportbuilder.md) en Report Builder. |
| Soporte para matrices de objetos de conjuntos de datos de perfil y búsqueda | [Usar matrices de objetos](/help/use-cases/object-arrays.md) e [Ingesta de públicos de Adobe Experience Platform](/help/use-cases/data-ingestion/ingest-aep-segments.md) actualizados para reflejar la compatibilidad de matrices de objetos para conjuntos de datos de perfil y búsqueda. |

{style="table-layout:auto"}

## 2022

| Fecha | Actualizar descripción |
| --- | --- |
| **Diciembre de 2022** |  |
| 16 de diciembre de 2022 | Tema nuevo acerca de la [medición y administración del uso de los datos de Customer Journey Analytics](/help/technotes/estimate-usage.md). |
| **Octubre de 2022** | |
| Octubre de 2022 | Tema nuevo en [protección de contraseña de proyectos programados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=es#password). Esta función es compatible con [Preparación para HIPAA](https://www.adobe.com/trust/compliance/hipaa-ready.html). |
| Octubre de 2022 | Tema nuevo en [Claves administradas por el cliente](/help/privacy/cmk.md). Esta función es compatible con [Preparación para HIPAA](https://www.adobe.com/trust/compliance/hipaa-ready.html). |
| Octubre de 2022 | Tema nuevo sobre [Registro de auditoría de Customer Journey Analytics](/help/privacy/audit-log.md). |
| Octubre de 2022 | Tema nuevo sobre la visualización [Resumen de métricas clave](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=es). |
| Octubre de 2022 | Nueva sección sobre [funcionalidad de fecha y hora en las vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#date) |
| Octubre de 2022 | Aplicación móvil: Tema nuevo sobre [vistas de detalles personalizadas](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#view-detail-slides). |
| Octubre de 2022 | Actualizaciones del tema [Soporte de funciones de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). |
| **Septiembre de 2022** | |
| Septiembre de 2022 | Nuevo caso de uso en [Migración de datos de Google Analytics a Customer Journey Analytics](/help/use-cases/ga/overview.md). |
| Septiembre de 2022 | Tema nuevo acerca de los [Gráficos combinados](/help/analysis-workspace/visualizations/combo-charts.md) en Workspace. |
| Septiembre de 2022 | Tema nuevo acerca del [Panel de experimentación](/help/analysis-workspace/c-panels/experimentation.md) en Workspace. |
| **Agosto de 2022** | |
| Agosto de 2022 | Artículo de Adobe Experience Platform sobre [compatibilidad entre regiones para el conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es). |
| Agosto de 2022 | Artículo actualizado de forma significativa sobre [control de acceso de Customer Journey Analytics](/help/technotes/access-control.md). |
| Agosto de 2022 | Nuevo artículo sobre [Compatibilidad con Customer Journey Analytics para etiquetas y políticas de gobernanza de datos](/help/data-views/data-governance.md). |
| Agosto de 2022 | Nuevo artículo sobre [comparación de la terminología de los datos de Analytics obtenidos a través del conector de origen de Analytics](/help/getting-started/aa-vs-cja/terminology.md). |
| Agosto de 2022 | Nueva documentación sobre [publicación de audiencias en el Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=es). |
| **Julio de 2022** | |
| Julio de 2022 | Documentación del [Panel Tiempo invertido en la reproducción de medios](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=es). |
| Julio de 2022 | Documentación del [Panel de visualizadores simultáneos de medios.](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=es) |
| Julio de 2022 | Documentación de creación de informes de [Primera sesión](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=es#new-repeat). |
| **Junio de 2022** | |
| Junio de 2022 | Nuevo artículo sobre [AAID, ECID, AACUSTOMID y el conector de origen de Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=es) |
| Junio de 2022 | Nuevo artículo sobre las [reglas de procesamiento de Adobe Analytics, VISTA y clasificaciones frente a la preparación de datos para el conector de origen de Analytics](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md). |
| Junio de 2022 | Nuevo artículo sobre [entornos de creación de informes virtuales y entornos de zona protegida](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md). |
| Junio de 2022 | Nuevo artículo sobre [comparación del procesamiento de datos entre las funciones de creación de informes de Adobe Analytics y Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md). |
| Junio de 2022 | Nuevo artículo sobre [combinación de grupos de informes con distintos esquemas](/help/use-cases/aa-data/combine-report-suites.md). |
| Junio de 2022 | Nuevo artículo sobre [compartir anotaciones en cuadros de resultados móviles](/help/components/annotations/mobile-annotations.md). |
| Junio de 2022 | Nuevo artículo sobre [Analytics Labs en Customer Journey Analytics](/help/labs/labs.md). |
| Junio de 2022 | Nueva sección sobre [compatibilidad con campos numéricos como claves de búsqueda y valores de búsqueda](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#numeric). |
| Junio de 2022 | Actualizaciones de [Flujo de trabajo de visualización de flujo](/help/analysis-workspace/visualizations/c-flow/create-flow.md). |
| **Mayo de 2022** | |
| Mayo de 2022 | Artículo actualizado de forma significativa sobre [creación de conexiones](/help/connections/create-connection.md) en Customer Journey Analytics. |
| Mayo de 2022 | Nuevo artículo sobre cómo [administrar bloques de datos en Report Builder de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=es). |
| Mayo de 2022 | Nuevo artículo sobre la [ingesta de públicos de Adobe Experience Platform en Customer Journey Analytics](/help/use-cases/data-ingestion/ingest-aep-segments.md). |
| **Abril de 2022** | |
| Abril de 2022 | Documentación sobre [subcadenas de dimensión](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=es). |
| Abril de 2022 | Nueva [Guía del usuario de Customer Journey Analytics para usuarios de Adobe Analytics](/help/getting-started/aa-to-cja-user.md). |
| **Marzo de 2022** | |
| Marzo de 2022 | Nueva [Documentación de API de anotaciones de Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/). |
| Marzo de 2022 | Nueva documentación sobre [anotaciones en Workspace](/help/components/annotations/overview.md). |
| Marzo de 2022 | Contenido actualizado de forma significativa en el [cálculo del tamaño de la conexión](/help/getting-started/cja-faq.md). |
| **Febrero de 2022** | |
| Febrero de 2022 | Una nueva guía para administradores que se trasladan de Adobe Analytics a Customer Journey Analytics: [Evolución de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=es) |
| **Enero de 2022** | |
| Enero de 2022 | Nuevo caso de uso para [Uso de dimensiones y métricas de enlace en Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md) |
| Enero de 2022 | Se ha añadido nueva documentación de funciones en [enlace de dimensiones y métricas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#binding-dimension) y en configuración de asignación [[!UICONTROL Conocido por primera vez] y [!UICONTROL Último conocido]](/help/data-views/component-settings/persistence.md#allocation-settings) |
| Enero de 2022 | Nuevo artículo sobre la [comparación de los datos de Adobe Analytics con los datos de Analytics en Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=es) |

{style="table-layout:auto"}

## 2021

| Fecha | Actualizar descripción |
| --- | --- |
| **Noviembre de 2021** | |
| Noviembre de 2021 | Documentación actualizada para [[!UICONTROL Registros omitidos]](/help/connections/manage-connections.md) en la página Detalles de conexiones. |
| **Octubre de 2021** | |
| Octubre de 2021 | Documentación para [Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/report-buider-overview.html?lang=es#) en Customer Journey Analytics. |
| Octubre de 2021 | Documentación de API de [Registro de auditoría](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) de Customer Journey Analytics |
| Octubre de 2021 | [Visualizaciones para paneles de Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=es#apply-visualizations) documentadas |
| Octubre de 2021 | Doc para la ventana móvil para la [retención de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=es#set-rolling-window-for-connection-data-retention) [!UICONTROL de Conexión]. |
| **Septiembre de 2021** | |
| Septiembre de 2021 | Doc de [Anulación de duplicación de métricas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=es) |
| Septiembre de 2021 | [Compatibilidad con el horario de verano para la creación de informes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=es#calendar) |
| Septiembre de 2021 | Documentación de [Calendarios de clientes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=es#calendar) |
| Septiembre de 2021 | Documentación de [Campos booleanos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/behavior.html?lang=es) |
| Septiembre de 2021 | Se ha desglosado la configuración de componentes en vistas de datos en archivos individuales:<ul><li>Información general sobre la configuración de [[!UICONTROL componentes]](/help/data-views/component-settings/overview.md)</li><li>Configuración de componentes de [[!UICONTROL atribución]](/help/data-views/component-settings/attribution.md)</li><li>Configuración de los componentes de [[!UICONTROL comportamiento]](/help/data-views/component-settings/behavior.md)</li><li>Configuración de componentes de [[!UICONTROL formato]](/help/data-views/component-settings/format.md)</li><li>Configuración de componentes de [[!UICONTROL Incluir/excluir]](/help/data-views/component-settings/include-exclude-values.md)</li><li>Configuración de componentes de [[!UICONTROL anulación de deduplicación de métricas]](/help/data-views/component-settings/metric-deduplication.md)</li><li>Sin configuración de componentes de [[!UICONTROL valor]](/help/data-views/component-settings/no-value-options.md)</li><li>Configuración de componentes de [[!UICONTROL persistencia]](/help/data-views/component-settings/persistence.md)</li><li>Configuración de componentes de [[!UICONTROL bloque de valores]](/help/data-views/component-settings/value-bucketing.md)</li></ul> |
| Septiembre de 2021 | Nueva sección sobre las [implicaciones de la combinación de grupos de informes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#6-considerations-when-merging-report-suites-in-cja) en Customer Journey Analytics. |
| **Agosto de 2021** | |
| Agosto de 2021 | Nueva sección sobre la experiencia de [Conexiones](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=es) mejorada en Customer Journey Analytics. |
| Agosto de 2021 | Nueva sección sobre la [distinción entre mayúsculas y minúsculas en las dimensiones de vista de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=es#configure-behavior-settings). |
| **Junio de 2021** | |
| Junio de 2021 | Nueva documentación sobre [versiones anteriores del proyecto](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/build-workspace-project/save-projects.html?lang=es#previous-version) en Workspace. |
| **Abril de 2021** | |
| Abril de 2021 | Nuevo tema sobre [persistencia](/help/data-views/component-settings/persistence.md). |
| Abril de 2021 | Nueva documentación sobre la compatibilidad con proyectos programados en Workspace. |
| Abril de 2021 | Temas nuevos sobre la experiencia [Vistas de datos mejorada](/help/data-views/data-views.md). |
| Abril de 2021 | Temas nuevos sobre [ingesta de datos de Google Analytics](/help/use-cases/ga/overview.md) y [análisis de esos datos](/help/use-cases/ga/report.md). |
| Abril de 2021 | Se ha añadido un tema sobre [informes programados](/help/analysis-workspace/export/t-schedule-report.md) en Workspace. |
| Abril de 2021 | Tema nuevo sobre [dimensiones de alta cardinalidad en Customer Journey Analytics](/help/components/dimensions/high-cardinality.md). |
| **Marzo de 2021** | |
| Marzo de 2021 | Se ha añadido un tema sobre la compatibilidad con [Paneles de Analytics](/help/mobile-app/home.md) (aplicación móvil). |
| Marzo de 2021 | Nuevo tema sobre [preferencias de usuario](/help/analysis-workspace/user-preferences.md) en Workspace. |
| **Febrero de 2021** | |
| Febrero de 2021 | Nuevo tema sobre el uso de [dimensiones del canal de marketing en Adobe Experience Platform](/help/use-cases/aa-data/marketing-channels.md). |
| Febrero de 2021 | Publicada la nueva documentación de la [API de Customer Journey Analytics](https://www.adobe.io/cja-apis/docs/). |
| **Enero de 2021** | |
| Enero de 2021 | Nuevo tema sobre [agregar búsquedas estándar al conjunto de datos](/help/connections/standard-lookups.md). |

{style="table-layout:auto"}

## 2020

| Fecha | Actualizar descripción |
| --- | --- |
| 13 de noviembre de 2020 | Nuevos temas sobre [Análisis en canales múltiples](/help/stitching/overview.md), que le permite volver a escribir la ID personal de un conjunto de datos y permite una combinación perfecta de múltiples conjuntos de datos. |
| 13 de noviembre de 2020 | Se ha añadido un nuevo caso de uso en [importación de centro de llamadas y datos web](/help/use-cases/cross-channel/call-center.md). |
| 10 de noviembre de 2020 | Se ha añadido una sección sobre las implicaciones de eliminar componentes de datos en las [preguntas frecuentes](/help/getting-started/cja-faq.md). |
| 2 de noviembre de 2020 | Actualizaciones a la página [compatibilidad con funciones de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). |
| Noviembre de 2020 | Se ha agregado contenido en [eliminando las limitaciones de relleno](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#backfill-historical-data) para las conexiones. |
| 7 de octubre de 2020 | Se ha añadido un tema sobre [conjuntos de datos de evento combinados](/help/connections/combined-dataset.md). |
| 15 de septiembre de 2020 | Se ha añadido un tema sobre [ingesta de datos](/help/data-ingestion/data-ingestion.md). |
| 2 de septiembre de 2020 | Se ha actualizado la sección sobre [permisos de usuario](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es). |
| Julio de 2020 | Se ha añadido información sobre la [opción de mapa de identidad para ID de persona](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es). |
| Julio de 2020 | Se ha añadido un nuevo tema sobre [matrices de objetos](/help/use-cases/object-arrays.md) o jerarquías de datos. |
| 14 de abril de 2020 | Actualizaciones de la IU más reciente en el tema [Crear conexiones](/help/connections/create-connection.md). |
| 27 de febrero de 2020 | Actualizaciones a la [compatibilidad con funciones de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md) |
| Diciembre de 2019 | Primer borrador de la documentación de Customer Journey Analytics |

{style="table-layout:auto"}
