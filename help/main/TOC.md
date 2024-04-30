---
git-repo: https://github.com/AdobeDocs/analytics-platform.es-ES
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guía de Customer Journey Analytics
user-guide-description: Obtenga información acerca de Customer Journey Analytics y sobre cómo utilizar Analysis Workspace con datos de Experience Platform.
breadcrumb-title: Guía de Customer Journey Analytics
source-git-commit: 4ab43b345adabb1add21294f5bf1f7858d08a11a
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 77%

---


# Guía de Adobe Customer Journey Analytics {#using}

+ [Guía de Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Notas de la versión {#releases}
   + [Última versión](../release-notes/latest.md)
   + [Versiones de 2024](../release-notes/2024.md)
   + [Versiones de 2023](../release-notes/2023.md)
   + [Versiones de 2022](../release-notes/2022.md)
   + [Versiones de 2021](../release-notes/2021.md)
   + [Versiones de 2020](../release-notes/2020.md)
   + [Versiones del Customer Journey Analytics](../release-notes/releases.md)
   + [Actualizaciones de la documentación de Customer Journey Analytics](../release-notes/doc-changes.md)

+ Introducción {#cja-overview}
   + [Información general sobre Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Guía de inicio rápido](../getting-started/cja-getting-started.md)
   + [Página de aterrizaje](../getting-started/landing.md)
   + [Página de aterrizaje (antigua)](../getting-started/cja-landing-old.md)
   + [Preguntas frecuentes](../getting-started/cja-faq.md)
   + [Comparar soluciones de Customer Journey Analytics con las soluciones de BI](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics y Adobe Analytics {#compare-aa-cja}
   + Migrar a Customer Journey Analytics {#migrate-to-cja}
      + [Introducción](/help/getting-started/cja-migration/cja-migration-getstarted.md)
      + [Elija una ruta de migración](/help/getting-started/cja-migration/cja-migration-path.md)
      + [Envío de datos a Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)
      + [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)
   + Comparación con Adobe Analytics {#cja-aa-comparison}
      + [Información general](../getting-started/aa-vs-cja/overview.md)
      + [Utilizar los datos de Adobe Analytics en Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Compatibilidad con las funciones de Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Comparación de la terminología de datos de Analytics transferidos a través del conector de origen de Analytics](../getting-started/aa-vs-cja/terminology.md)
      + [Compare el procesamiento de datos entre Adobe Analytics y Customer Journey Analytics](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Entornos de informes virtuales y entornos de zonas protegidas](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Reglas de procesamiento, VISTA y clasificaciones en comparación con la preparación de datos](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID y el conector de origen de Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Evolución desde Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guía para usuarios de Adobe Analytics](../getting-started/aa-to-cja-user.md)

+ Ingesta de datos {#cja-data-ingestion}
   + [Información general sobre la ingesta de datos](../data-ingestion/data-ingestion.md)
   + Guías de inicio rápido de ingesta y uso{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Adobe Experience Platform Edge Network {#edge-network}
         + [SDK web](../data-ingestion/aepwebsdk.md)
         + [SDK móvil](../data-ingestion/aepmobilesdk.md)
         + [API de servidor](../data-ingestion/serverapi.md)
      + [Datos por lotes](../data-ingestion/batch.md)
      + [Datos de streaming](../data-ingestion/streaming.md)
      + [Conectores de origen](../data-ingestion/sources.md)

+ Conexiones {#cja-connections}
   + [Información general sobre conexiones](../connections/overview.md)
   + [Crear o editar una conexión](../connections/create-connection.md)
   + [Administrar conexiones](../connections/manage-connections.md)
   + [Conjuntos de datos de evento combinados](../connections/combined-dataset.md)
   + [Búsquedas estándar](../connections/standard-lookups.md)

+ Vistas de datos {#cja-dataviews}
   + [Información general de las vistas de datos](../data-views/data-views.md)
   + [Creación o edición de una vista de datos](../data-views/create-dataview.md)
   + [Configuración de sesión](../data-views/session-settings.md)
   + Configuración de componentes {#component-settings}
      + [Información general sobre la configuración de componentes](../data-views/component-settings/overview.md)
      + [Atribución](../data-views/component-settings/attribution.md)
      + [Comportamiento](../data-views/component-settings/behavior.md)
      + [Formato](../data-views/component-settings/format.md)
      + [Incluir/excluir valores](../data-views/component-settings/include-exclude-values.md)
      + [Anulación de duplicación métrica](../data-views/component-settings/metric-deduplication.md)
      + [Sin opciones de valor](../data-views/component-settings/no-value-options.md)
      + [Persistencia](../data-views/component-settings/persistence.md)
      + [Subcadena](../data-views/component-settings/substring.md)
      + [Clasificación de valor](../data-views/component-settings/value-bucketing.md)
   + [Referencia de componente estándar](../data-views/component-reference.md)
   + [Extensión de CJA BI](../data-views/bi-extension.md)
   + [Campos derivados](../data-views/derived-fields/derived-fields.md)
   + [Etiquetas y políticas](../data-views/data-governance.md)

+ Proyectos de Workspace {#cja-workspace}
   + [Información general de Analysis Workspace](../analysis-workspace/home.md)
   + [Realizar análisis básico](../analysis-workspace/perform-basic-analysis.md)
   + [Realizar análisis avanzado](../analysis-workspace/perform-adv-analysis.md)
   + Proyectos {#build-workspace-project}
      + [Información general sobre Proyectos](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Crear proyectos](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Guardar proyectos](../analysis-workspace/build-workspace-project/save-projects.md)
      + Carpetas en Workspace {#workspace-folders}
         + [Acerca de las carpetas en Workspace](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Creación de carpetas y subcarpetas](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Eliminar carpetas](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [Agregar proyectos](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [Quitar un proyecto](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [Guardar un nuevo proyecto](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [Teclas de acceso directo (métodos abreviados)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Paletas de color](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Ver densidad](../analysis-workspace/build-workspace-project/view-density.md)
   + Visualizaciones {#visualizations}
      + [Resumen de las visualizaciones](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Administración de fuentes de datos](../analysis-workspace/visualizations/t-sync-visualization.md)
      + Tabla de forma libre {#freeform-table}
         + [Tabla de forma libre](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Configuración de columna y fila {#column-row-settings}
            + [Configuración de columna](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Configuración de filas](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Elementos dinámicos vs. estáticos](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrado y ordenación de tablas](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totales de Workspace](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabla de cohorte {#cohort-table}
         + [¿Qué es el análisis de cohorte?](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurar un informe de análisis de cohorte](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casos de uso de análisis de cohorte](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Visita en orden previsto {#fallout}
         + [Resumen de visita en orden previsto](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurar una visualización de visita en orden previsto](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Visita en orden previsto entre dimensiones](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Aplicar filtros en un análisis de visitas en orden previsto](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flujo {#flow}
         + [Resumen de flujos](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configuración de una visualización de flujo](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flujos interdimensionales](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Área y área apilada](../analysis-workspace/visualizations/area.md)
      + [Barra y barra apilada](../analysis-workspace/visualizations/bar.md)
      + [Gráfico de viñetas](../analysis-workspace/visualizations/bullet-graph.md)
      + [Gráfico combinado](../analysis-workspace/visualizations/combo-charts.md)
      + [Anillo](../analysis-workspace/visualizations/donut.md)
      + [Histograma](../analysis-workspace/visualizations/histogram.md)
      + [Barras horizontales y barras horizontales apiladas](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Pies de ilustración inteligentes](../analysis-workspace/visualizations/intelligent-captions.md)
      + [Resumen de métricas clave](../analysis-workspace/visualizations/key-metric.md)
      + [Línea](../analysis-workspace/visualizations/line.md)
      + [Diagrama de dispersión](../analysis-workspace/visualizations/scatterplot.md)
      + [Número de resumen y cambio de resumen](../analysis-workspace/visualizations/summary-number-change.md)
      + [Texto](../analysis-workspace/visualizations/text.md)
      + [Mapa de árbol](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Paneles {#panels}
      + [Resumen de paneles](../analysis-workspace/c-panels/panels.md)
      + [Panel de Attribution](../analysis-workspace/c-panels/attribution.md)
      + [Panel en blanco](../analysis-workspace/c-panels/blank-panel.md)
      + [Panel Experimentación](../analysis-workspace/c-panels/experimentation.md)
      + [Panel de forma libre](../analysis-workspace/c-panels/freeform-panel.md)
      + [Panel de audiencia media por minuto de medios](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Panel de información rápida](../analysis-workspace/c-panels/quickinsight.md)
      + [Panel Visualizadores simultáneos de medios](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Panel Tiempo invertido en la reproducción de contenido](../analysis-workspace/c-panels/media-playback-time-spent.md)
   + Depuración, uso compartido y programación de proyectos {#curate-share}
      + [Menú Compartir](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Depurar proyectos de](../analysis-workspace/curate-share/curate.md)
      + [Compartir proyectos](../analysis-workspace/curate-share/share-projects.md)
      + [Crear vínculos que se pueden compartir](../analysis-workspace/curate-share/shareable-links.md)
      + [Proyectos de solo de vista](../analysis-workspace/curate-share/view-only-projects.md)
   + Exportar {#export}
      + [Información general de exportación](../analysis-workspace/export/export-project-overview.md)
      + [Descargar](../analysis-workspace/export/download-send.md)
      + [Enviar a otras personas](../analysis-workspace/export/t-schedule-report.md)
      + [Exportación a la nube](../analysis-workspace/export/export-cloud.md)
   + Detección de anomalías {#anomaly-detection}
      + [Resumen de la Detección de anomalías](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Visualización de anomalías en Analysis Workspace](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Técnicas estadísticas utilizadas en la detección de anomalías](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Previsión {#forecasting}
      + [Resumen de previsión](../analysis-workspace/c-forecast/forecasting.md)
      + [Ver previsiones en Analysis Workspace](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Técnicas estadísticas utilizadas en el servicio de pronóstico](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Preferencias de usuario](../analysis-workspace/user-preferences.md)
   + Preguntas frecuentes sobre de Workspace {#workspace-faq}
      + [Preguntas frecuentes](../analysis-workspace/workspace-faq/faq.md)
      + [Mensajes de error](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limitaciones de Analysis Workspace](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisitos de administración](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accesibilidad en Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Paneles de Analytics {#cja-dashboards}
   + [Paneles de Analytics: Información general](../mobile-app/home.md)
   + [Tareas del gestor de datos](../mobile-app/curator.md)
   + [Creación de un cuadro de resultados móvil](../mobile-app/create-scorecard.md)
   + [Administrar cuadros de resultados móviles](../mobile-app/manage-scorecard.md)
   + [Configuración de ejecutivos para que utilicen tableros](../mobile-app/set-up-execs.md)
   + [Guía de inicio rápida para el usuario ejecutivo](../mobile-app/executive.md)

+ Análisis guiado {#guided-analysis}
   + [Información general](../guided-analysis/overview.md)
   + Canal {#funnel}
      + [Vista de fricción](../guided-analysis/types/friction.md)
      + [Vista de tendencias de conversión](../guided-analysis/types/conversion-trends.md)
   + Impacto {#impact}
      + [Vista de versión](../guided-analysis/types/release.md)
      + [Vista de primer uso](../guided-analysis/types/first-use.md)
   + Retención {#retention}
      + [Tasas de retención](../guided-analysis/types/retention-rates.md)
   + Tendencias {#trends}
      + [Vista de uso](../guided-analysis/types/usage.md)
      + [Vista de frecuencia](../guided-analysis/types/frequency.md)
   + Crecimiento de usuarios {#user-growth}
      + [Vista activa](../guided-analysis/types/active.md)
      + [Vista de crecimiento neto](../guided-analysis/types/net-growth.md)
   + Flujo de usuarios {#streams}
      + [Cronología](../guided-analysis/types/timeline.md)
   + [Casos de uso del sector](../guided-analysis/industry-use-cases.md)
   + [Preguntas más frecuentes](../guided-analysis/faq.md)

+ Componentes {#cja-components}
   + [Resumen de componentes](../components/overview.md)
   + [Adición de descripciones de componentes](../components/add-component-descriptions.md)
   + Anotaciones {#annotations}
      + [Descripción general de anotaciones](../components/annotations/overview.md)
      + [Creación de anotaciones](../components/annotations/create-annotations.md)
      + [Administración de anotaciones](../components/annotations/manage-annotations.md)
      + [Visualización de anotaciones](../components/annotations/view-annotations.md)
      + [Anotaciones móviles](../components/annotations/mobile-annotations.md)
   + [Proyecto programado](../components/scheduled-projects-manager.md)
   + Audiencias {#audiences}
      + [Descripción general de las audiencias](../components/audiences/audiences-overview.md)
      + [Crear y publicar audiencias](../components/audiences/publish.md)
      + [Administrar audiencias](../components/audiences/manage.md)
   + Dimensiones {#dimensions}
      + [Vista preliminar de dimensiones](../components/dimensions/view-dimensions.md)
      + [Desglose de dimensiones](../components/dimensions/t-breakdown-fa.md)
      + [Dimensiones de partición de tiempo](../components/dimensions/time-parting-dimensions.md)
      + [Dimensión con muy alta cardinalidad](../components/dimensions/high-cardinality.md)
   + [Métricas](../components/apply-create-metrics.md)
   + Filtros {#cja-filters}
      + [Información general de Filtros](../components/filters/filters-overview.md)
      + [Crear filtros](../components/filters/create-filters.md)
      + [Compartir filtros](../components/filters/filters-share.md)
      + [Filtros de etiquetas](../components/filters/filters-tag.md)
      + [Filtrado de la lista de filtros](../components/filters/filters-filter.md)
      + [Marcar filtros como favoritos](../components/filters/filters-favorite.md)
      + [Aprobar filtros](../components/filters/filters-approve.md)
      + [Copiar filtros](../components/filters/filters-copy.md)
      + [Filtros rápidos](../components/filters/quick-filters.md)
      + [Generador de filtros](../components/filters/filter-builder.md)
      + [Administrar filtros](../components/filters/manage-filters.md)
      + [Operadores](../components/filters/operators.md)
   + Métricas calculadas {#cja-calcmetrics}
      + [Información general sobre las métricas calculadas](../components/calc-metrics/calc-metr-overview.md)
      + Flujo de trabajo de las métricas calculadas {#cm-workflow}
         + [Flujo de trabajo de las métricas calculadas](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Buscar métricas](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Generar métricas](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Tipo de métrica y atribución](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Crear una métrica de participación](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Métricas filtradas](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Apilado y reemplazo de filtros](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Métricas filtradas y ponderadas](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Filtrar métricas calculadas](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Marcar una métrica calculada como favorita](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Copiar métricas calculadas](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Uso de funciones](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Etiquetar métricas calculadas](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Aprobar métricas calculadas](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Compartir métricas calculadas](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Administrador de métricas calculadas](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Métricas calculadas predeterminadas](../components/calc-metrics/default-calcmetrics.md)
      + [Funciones básicas](../components/calc-metrics/cm-functions.md)
      + [Funciones avanzadas](../components/calc-metrics/cm-adv-functions.md)
   + Calendario e intervalos de fechas {#cja-date-ranges}
      + [Resumen de calendario e intervalos de fechas](../components/date-ranges/calendar.md)
      + [Crear un intervalo de fecha](../components/date-ranges/create.md)
      + [Administrar intervalos de fechas](../components/date-ranges/manage.md)
      + [Crear intervalos de fechas](../components/date-ranges/custom-date-ranges.md)
      + [Comparación de fechas](../components/date-ranges/time-comparison.md)
   + Exportaciones {#exports}
      + [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md)
      + [Configuración de ubicaciones de exportación de nube](/help/components/exports/cloud-export-locations.md)
      + [Administrar ubicaciones de exportación en la nube](/help/components/exports/manage-export-locations.md)
      + [Administración de exportaciones](/help/components/exports/manage-exports.md)
      + [Administración de registros de exportación](/help/components/exports/manage-export-logs.md)
      + [Resolución de problemas de exportaciones](/help/components/exports/troubleshoot-exports.md)
   + Diccionario de datos {#data-dictionary}
      + [Información general del diccionario de datos](../components/data-dictionary/data-dictionary-overview.md)
      + [Visualización de información de componentes en el diccionario de datos](../components/data-dictionary/view-data-dictionary.md)
      + [Edición de entradas de componentes en el diccionario de datos](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Monitorización del estado del diccionario de datos](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Información general de Report Builder](../report-builder/report-buider-overview.md)
   + [Configuración de Report Builder](../report-builder/report-builder-setup.md)
   + [Creación de un bloque de datos](../report-builder/create-a-data-block.md)
   + [Report Builder Hub](../report-builder/report-builder-hub.md)
   + [Seleccionar una vista de datos](../report-builder/select-data-view.md)
   + [Selección de un intervalo de fechas](../report-builder/select-date-range.md)
   + [Trabajo con filtros](../report-builder/work-with-filters.md)
   + [Filtrar dimensiones](../report-builder/filter-dimensions.md)
   + [Administrar bloques de datos](../report-builder/manage-reportbuilder.md)
   + [Programar libros de trabajo](../report-builder/schedule-reportbuilder.md)
   + [Etiquetas restringidas](../report-builder/restricted-labels.md)
   + [Configuración de Report Builder](../report-builder/report-builder-settings.md)

+ Administrador de actividades de creación de informes {#reporting-activity-manager}
   + [Información general](../reporting-activity-manager/reporting-activity-overview.md)
   + [Ver actividad de creación de informes](../reporting-activity-manager/reporting-activity.md)
   + [Cancelar solicitudes de creación de informes](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Vinculación {#stitching}
   + [Información general](../stitching/overview.md)
   + [Cómo funciona la vinculación](../stitching/explained.md)
   + [Crear y administrar conjuntos de datos enlazados](../stitching/stitching-ui.md)
   + [Preguntas frecuentes](../stitching/faq.md)

+ Integraciones de Adobe {#integrations}
   + [Integración de soluciones de Adobe con información general sobre Customer Journey Analytics](/help/integrations/overview.md)
   + [Integración de Adobe Analytics con Customer Journey Analytics](/help/integrations/aa.md)
   + [Integración de datos de Journey Optimizer con Customer Journey Analytics](/help/integrations/ajo.md)
   + [Integración de datos de Administración de decisiones con Customer Journey Analytics](/help/integrations/ajo-od.md)
   + [Integración de Customer AI con Customer Journey Analytics](/help/integrations/customer-ai.md)

+ Gobierno de datos {#cja-privacy}
   + [Gobernanza de datos](../privacy/privacy-overview.md)
   + [Registro de auditoría](../privacy/audit-log.md)
   + [Claves gestionadas por el cliente](../privacy/cmk.md)

+ Casos prácticos {#cja-usecases}
   + [Casos de uso de Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Datos de Google Analytics {#ga}
      + [Información general sobre la migración de datos de Google Analytics a Customer Journey Analytics](../use-cases/ga/overview.md)
      + [Ingesta de datos históricos de Google Analytics en Platform](../use-cases/ga/backfill.md)
      + [Configuración del streaming de los datos de Google Analytics a Platform](../use-cases/ga/streaming.md)
      + [Informar sobre los datos de Google Analytics en Customer Journey Analytics](../use-cases/ga/report.md)
   + Ingesta de datos {#data-ingestion}
      + [Ingesta de datos de Marketo Engage en Adobe Experience Platform e informes en Customer Journey Analytics](../use-cases/data-ingestion/marketo.md)
      + [Ingesta de audiencias de Adobe Experience Platform en Customer Journey Analytics](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Vistas de datos {#data-views}
      + [Casos de uso de vistas de datos](../use-cases/data-views/data-views-usecases.md)
      + [Uso de dimensiones y métricas de enlace](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [Ejemplo de proyecto B2B](../use-cases/b2b/example.md)
      + [Añadir datos de nivel de cuenta como un conjunto de datos de consulta](../use-cases/b2b/b2b.md)
   + Datos multicanal {#cross-channel}
      + [Analizar datos en varios canales](../use-cases/cross-channel/cross-channel.md)
      + [Importación de datos web y de centros de llamadas](../use-cases/cross-channel/call-center.md)
   + Datos de Adobe Analytics {#aa-data}
      + [Uso de dimensiones del canal de marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinación de grupos de informes con diferentes esquemas](../use-cases/aa-data/combine-report-suites.md)
      + [Emulación de fuentes de datos](../use-cases/emulating-data-feeds.md)
   + Datos complejos {#complex-data}
      + [Usar matrices de objetos](../use-cases/object-arrays.md)
   + Campos derivados {#derived-fields}
      + [Usar campos derivados para informar sobre objetivos](../use-cases/goals-using-derived-fields.md)


+ Administración {#cja-admin}
   + [Mecanismos de protección](../admin/guardrails.md)
   + [Control de acceso](../admin/cja-access-control.md)
   + [Ver y administrar el uso](../admin/estimate-usage.md)
   + [Implicaciones de eliminación](../admin/cja-deletion.md)
   + [Optimización del rendimiento del Customer Journey Analytics](../admin/optimizing-performance.md)
   + [Direcciones IP](../admin/ip-addresses.md)

+ Labs {#labs}
   + [Guía del usuario de Labs](../labs/labs.md)

+ Resolución de problemas {#troubleshooting}
   + [Comparación de los datos de Adobe Analytics con los de Customer Journey Analytics](../troubleshooting/compare.md)
   + [Coherencia de métricas y recuentos de miembros de audiencia entre Real-time CDP y Customer Journey Analytics](../troubleshooting/consistency-rcdp-cja.md)
   + [Falta de permisos](../troubleshooting/lack-of-permissions.md)

+ Notas técnicas {#technotes}
   + [centros de datos de Customer Journey Analytics](../technotes/cja-datacenters.md)

+ [Glosario de Customer Journey Analytics](../getting-started/cja-glossary.md)

+ [API de Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/)
