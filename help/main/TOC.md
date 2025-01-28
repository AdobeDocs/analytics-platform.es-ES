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
source-git-commit: 0e3f15abbc904786c359160749d62754a9ebbe50
workflow-type: tm+mt
source-wordcount: '1113'
ht-degree: 98%

---

# Guía de Adobe Customer Journey Analytics {#using}

+ [Guía de Adobe Customer Journey Analytics](../getting-started/cja-landing.md)
+ [Asistente de IA para Adobe Customer Journey Analytics](../ai-assistant.md)
+ [Asistente de IA de análisis de datos para Customer Journey Analytics](../data-analysis-ai.md)

+ Notas de la versión {#releases}
   + [Última versión](../release-notes/latest.md)
   + [Versiones de 2024](../release-notes/2024.md)
   + [Versiones de 2023](../release-notes/2023.md)
   + [Versiones de 2022](../release-notes/2022.md)
   + [Versiones de 2021](../release-notes/2021.md)
   + [Versiones de 2020](../release-notes/2020.md)
   + [Estrategia de lanzamiento de funciones](../release-notes/releases.md)
   + [Actualizaciones de documentación](../release-notes/doc-changes.md)

+ Introducción {#cja-overview}
   + [Información general sobre Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Guía de inicio rápido](../getting-started/cja-getting-started.md)
   + [Página de aterrizaje](../getting-started/landing.md)
   + [Página de aterrizaje (antigua)](../getting-started/cja-landing-old.md)
   + [Preguntas frecuentes](../getting-started/cja-faq.md)
   + [Comparar soluciones de Customer Journey Analytics con las soluciones de BI](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics y Adobe Analytics {#compare-aa-cja}
   + Actualizar a Customer Journey Analytics {#upgrade-to-cja}
      + [Introducción](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Elegir la ruta de actualización](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Enviar datos a Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Conservar datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [Proceso recomendado](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + [Comprender la implementación de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
      + [Creación de conjuntos de datos de búsqueda para clasificaciones](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
      + [Monitorización de la ingesta de datos](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + [Creación de un campo derivado de canal de marketing](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Implementación de la etiqueta de carga para la extensión del SDK web](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
      + [Creación de una etiqueta para su propiedad](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
      + [Adición de la extensión del SDK web a la etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
      + [Adición de la lógica de recopilación de datos XDM a la etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [Diseña tu esquema](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
      + [Crea tu etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
      + [Usa el esquema existente](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + [Crear un conjunto de datos](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
      + [Crear un flujo de datos](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
      + [Añade Platform como servicio](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + [Crea una conexión](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [Crea una vista de datos](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [Valida el flujo de datos](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [Método abreviado de actualización: migrar a SDK web](/help/getting-started/cja-upgrade/cja-upgrade-shortcut-websdk.md)
      + [Creación de un esquema XDM para el conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
      + [Creación del conector de origen de Analytics y asignación de campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
      + [Adición del conjunto de datos del conector de origen de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Uso del conector de origen de Analytics de manera exclusiva](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)
      + [Movimiento desde el conector de origen de Analytics al SDK web](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
      + [Deshabilitación de la recopilación de datos de AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + [Actualización desde una solución de análisis de terceros](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + [Compatibilidad con funciones de Adobe Analytics al actualizar](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
   + Comparación con Adobe Analytics {#cja-aa-comparison}
      + [Información general](../getting-started/aa-vs-cja/overview.md)
      + [Utilizar datos en Adobe Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Compatibilidad de funciones](../getting-started/aa-vs-cja/cja-aa.md)
      + [Comparar terminología](../getting-started/aa-vs-cja/terminology.md)
      + [Comparar procesamiento de datos](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Entornos](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Procesamiento de Analytics frente a preparación de datos](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [ID de Analytics:](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Evolución desde Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guía para usuarios de Adobe Analytics](../getting-started/aa-to-cja-user.md)

+ Ingesta de datos {#cja-data-ingestion}
   + [Información general sobre la ingesta de datos](../data-ingestion/data-ingestion.md)
   + Guías de inicio rápido de ingesta y uso{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
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
   + [Búsquedas B2B](../connections/transform-datasets-b2b-lookups.md)

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
      + [Grupo de datos de resumen](../data-views/component-settings/summary-data-group.md)
      + [Creación de depósitos](../data-views/component-settings/value-bucketing.md)
   + [Referencia de componente estándar](../data-views/component-reference.md)
   + [Extensión de BI](../data-views/bi-extension.md)
   + [Campos derivados](../data-views/derived-fields/derived-fields.md)
   + [Datos de resumen](../data-views/summary-data.md)
   + [Etiquetas y políticas](../data-views/data-governance.md)

+ Herramientas {#tools}
   + Transferencia de recurso {#asset-transfer}
      + [Transferir recursos](../tools/asset-transfer/transfer-assets.md)
   + Uso del producto {#product-usage}
      + [Información general](../tools/product-usage/usage-overview.md)
      + [Configuración de datos](../tools/product-usage/data-settings.md)
      + [Configuración de la exclusión](../tools/product-usage/opt-out-settings.md)

+ Proyectos de Workspace {#cja-workspace}
   + [Información general de Analysis Workspace](../analysis-workspace/home.md)
   + [Realizar análisis básico](../analysis-workspace/perform-basic-analysis.md)
   + [Realizar análisis avanzado](../analysis-workspace/perform-adv-analysis.md)
   + Proyectos {#build-workspace-project}
      + [Información general](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Crear proyectos](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Abrir proyectos](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Guardar proyectos](../analysis-workspace/build-workspace-project/save-projects.md)
      + Carpetas en Workspace {#workspace-folders}
         + [Acerca de las carpetas](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Creación de carpetas y subcarpetas](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Administración de carpetas](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Agregar o mover proyectos a carpetas](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Teclas de acceso directo (métodos abreviados)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Paletas de color](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Ver densidad](../analysis-workspace/build-workspace-project/view-density.md)
   + Plantillas {#templates}
      + [Uso de plantillas](../analysis-workspace/templates/use-templates.md)
      + [Creación y administración de plantillas](../analysis-workspace/templates/create-templates.md)
   + Visualizaciones {#visualizations}
      + [Información general](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Administración de fuentes de datos](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [Pies de ilustración inteligentes](../analysis-workspace/visualizations/intelligent-captions.md)
      + Tabla de forma libre {#freeform-table}
         + [Información general](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [Crear hipervínculo](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + Configuración de columna y fila {#column-row-settings}
            + [Configuración de columna](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Configuración de filas](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Elementos dinámicos y estáticos](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrado y ordenación de tablas](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totales de Workspace](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabla de cohorte {#cohort-table}
         + [Información general](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configuración](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casos prácticos](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Visita en orden previsto {#fallout}
         + [Información general](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configuración](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Visita en orden previsto entre dimensiones](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Aplicar filtros](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flujo {#flow}
         + [Información general](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configuración](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flujos interdimensionales](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + Lienzo de recorrido {#journey-canvas}
         + [Información general](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [Configuración](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [Solucionar problemas](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [Área (apilada)](../analysis-workspace/visualizations/area.md)
      + [Barra (apilada)](../analysis-workspace/visualizations/bar.md)
      + [Viñeta](../analysis-workspace/visualizations/bullet-graph.md)
      + [Combo](../analysis-workspace/visualizations/combo-charts.md)
      + [Anillo](../analysis-workspace/visualizations/donut.md)
      + [Histograma](../analysis-workspace/visualizations/histogram.md)
      + [Barra horizontal (apilada)](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Resumen de métricas clave](../analysis-workspace/visualizations/key-metric.md)
      + [Línea](../analysis-workspace/visualizations/line.md)
      + [Mapa](/help/analysis-workspace/visualizations/map.md)
      + [Dispersión](../analysis-workspace/visualizations/scatterplot.md)
      + [Encabezado de sección](/help/analysis-workspace/visualizations/section-header.md)
      + [Número de resumen y cambio](../analysis-workspace/visualizations/summary-number-change.md)
      + [Texto](../analysis-workspace/visualizations/text.md)
      + [Mapa de árbol](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Paneles {#panels}
      + [Información general](../analysis-workspace/c-panels/panels.md)
      + [Panel en blanco](../analysis-workspace/c-panels/blank-panel.md)
      + [Atribución](../analysis-workspace/c-panels/attribution.md)
      + [Experimentación](../analysis-workspace/c-panels/experimentation.md)
      + [De forma libre](../analysis-workspace/c-panels/freeform-panel.md)
      + [Audiencia media por minuto de medios](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Espectadores simultáneos de medios](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Tiempo invertido en la reproducción de medios](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Elemento siguiente o anterior](../analysis-workspace/c-panels/next-previous.md)
      + [Acceso rápido a información](../analysis-workspace/c-panels/quickinsight.md)
   + Depuración, uso compartido y programación de proyectos {#curate-share}
      + [Información general](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Depurar proyectos de](../analysis-workspace/curate-share/curate.md)
      + [Compartir proyectos](../analysis-workspace/curate-share/share-projects.md)
      + [Crear vínculos que se pueden compartir](../analysis-workspace/curate-share/shareable-links.md)
      + [Proyectos de solo de vista](../analysis-workspace/curate-share/view-only-projects.md)
   + Exportar {#export}
      + [Información general](../analysis-workspace/export/export-project-overview.md)
      + [Descargar](../analysis-workspace/export/download-send.md)
      + [Enviar a otros](../analysis-workspace/export/t-schedule-report.md)
      + [Exportar a la nube](../analysis-workspace/export/export-cloud.md)
   + Detección de anomalías {#anomaly-detection}
      + [Información general](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Ver anomalías](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Técnicas estadísticas](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Previsión {#forecasting}
      + [Información general](../analysis-workspace/c-forecast/forecasting.md)
      + [Ver previsiones](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Técnicas estadísticas](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Índice ](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
   + [Preferencias de usuario](../analysis-workspace/user-preferences.md)
   + Preguntas frecuentes sobre Workspace y más {#workspace-faq}
      + [Preguntas frecuentes](../analysis-workspace/workspace-faq/faq.md)
      + [Mensajes de error](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limitaciones](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisitos de administración](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accesibilidad](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Paneles de Analytics {#cja-dashboards}
   + [Información general](../mobile-app/home.md)
   + [Tareas del gestor de datos](../mobile-app/curator.md)
   + [Creación de cuadros de resultados móviles](../mobile-app/create-scorecard.md)
   + [Administración de cuadros de resultados móviles](../mobile-app/manage-scorecard.md)
   + [Configuración de ejecutivos para que utilicen tableros](../mobile-app/set-up-execs.md)
   + [Guía de inicio rápida para el usuario ejecutivo](../mobile-app/executive.md)

+ Análisis guiado {#guided-analysis}
   + [Información general](../guided-analysis/overview.md)
   + [Crecimiento activo](../guided-analysis/types/active-growth.md)
   + [Tendencias de conversión](../guided-analysis/types/conversion-trends.md)
   + [Participación](../guided-analysis/types/engagement.md)
   + [Impacto del primer uso](../guided-analysis/types/first-use-impact.md)
   + [Frecuencia](../guided-analysis/types/frequency.md)
   + [Canal](../guided-analysis/types/funnel.md)
   + [Crecimiento neto](../guided-analysis/types/net-growth.md)
   + [Impacto de versión](../guided-analysis/types/release-impact.md)
   + [Retención](../guided-analysis/types/retention.md)
   + [Cronología](../guided-analysis/types/timeline.md)
   + [Tendencias](../guided-analysis/types/trends.md)
   + [Casos de uso del sector](../guided-analysis/industry-use-cases.md)
   + [Preguntas más frecuentes](../guided-analysis/faq.md)

+ Componentes {#cja-components}
   + [Información general](../components/overview.md)
   + [Uso de componentes en Analysis Workspace](../components/use-components-in-workspace.md)
   + [Adición de descripciones de componentes](../components/add-component-descriptions.md)
   + Anotaciones {#annotations}
      + [Descripción general de anotaciones](../components/annotations/overview.md)
      + [Creación de anotaciones](../components/annotations/create-annotations.md)
      + [Administración de anotaciones](../components/annotations/manage-annotations.md)
      + [Visualización de anotaciones](../components/annotations/view-annotations.md)
      + [Anotaciones móviles](../components/annotations/mobile-annotations.md)
   + [Proyectos programados](../components/scheduled-projects-manager.md)
   + Audiencias {#audiences}
      + [Descripción general de las audiencias](../components/audiences/audiences-overview.md)
      + [Crear y publicar audiencias](../components/audiences/publish.md)
      + [Administrar audiencias](../components/audiences/manage.md)
   + Dimensiones {#dimensions}
      + [Información general de dimensiones](../components/dimensions/overview.md)
      + [Vista preliminar de dimensiones](../components/dimensions/view-dimensions.md)
      + [Desglose de dimensiones](../components/dimensions/t-breakdown-fa.md)
      + [Dimensiones de partición de tiempo](../components/dimensions/time-parting-dimensions.md)
      + [Dimensiones de alta cardinalidad](../components/dimensions/high-cardinality.md)
   + [Métricas](../components/apply-create-metrics.md)
   + Filtros {#cja-filters}
      + [Información general](../components/filters/filters-overview.md)
      + [Crear filtros](../components/filters/create-filters.md)
      + [Generar filtros](../components/filters/filter-builder.md)
      + [Filtros rápidos](../components/filters/quick-filters.md)
      + [Filtros secuenciales](../components/filters/seg-sequential-build.md)
      + [Compartir filtros](../components/filters/filters-share.md)
      + [Filtros de etiquetas](../components/filters/filters-tag.md)
      + [Filtrar la lista de filtros](../components/filters/filters-filter.md)
      + [Marcar filtros como favoritos](../components/filters/filters-favorite.md)
      + [Aprobar filtros](../components/filters/filters-approve.md)
      + [Copiar filtros](../components/filters/filters-copy.md)
      + [Administrar filtros](../components/filters/manage-filters.md)
      + [Operadores](../components/filters/operators.md)
   + Métricas calculadas {#cja-calcmetrics}
      + [Información general](../components/calc-metrics/calc-metr-overview.md)
      + Flujo de trabajo de las métricas calculadas {#cm-workflow}
         + [Crear métricas calculadas](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Crear métricas calculadas](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Buscar métricas](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Tipo de métrica y atribución](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Generar una métrica de participación](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Métricas filtradas](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Apilado y reemplazo de filtros](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrar métricas calculadas](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Marcar una métrica calculada como favorita](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Copiar métricas calculadas](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Uso de funciones](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Etiquetar métricas calculadas](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Aprobar métricas calculadas](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Compartir métricas calculadas](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Administrar métricas calculadas](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [Ejemplos](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [Plantillas de métricas calculadas](../components/calc-metrics/default-calcmetrics.md)
      + [Funciones básicas](../components/calc-metrics/cm-functions.md)
      + [Funciones avanzadas](../components/calc-metrics/cm-adv-functions.md)
   + Intervalos de fechas {#cja-date-ranges}
      + [Información general](../components/date-ranges/overview.md)
      + [Crear intervalos de fechas](../components/date-ranges/create.md)
      + [Administrar intervalos de fechas](../components/date-ranges/manage.md)
      + [Comparación de fechas](../components/date-ranges/time-comparison.md)
      + [Ejemplos](../components/date-ranges/custom-date-ranges.md)
   + Alertas {#alerts}
      + [Información general](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [Creación de alertas](/help/components/c-intelligent-alerts/alert-builder.md)
      + [Administración de alertas](/help/components/c-intelligent-alerts/alert-manager.md)
      + [Comparación de características](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [Casos prácticos](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + Exportaciones {#exports}
      + [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md)
      + [Configuración de ubicaciones de exportación en la nube](/help/components/exports/cloud-export-locations.md)
      + [Administración de ubicaciones de exportación en la nube](/help/components/exports/manage-export-locations.md)
      + [Administración de exportaciones](/help/components/exports/manage-exports.md)
      + [Administración de registros de exportación](/help/components/exports/manage-export-logs.md)
      + [Resolución de problemas de exportaciones](/help/components/exports/troubleshoot-exports.md)
   + Diccionario de datos {#data-dictionary}
      + [Información general](../components/data-dictionary/data-dictionary-overview.md)
      + [Visualización de información de componentes en el diccionario de datos](../components/data-dictionary/view-data-dictionary.md)
      + [Edición de entradas de componentes en el diccionario de datos](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Monitorización del estado del diccionario de datos](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Información general](../report-builder/report-buider-overview.md)
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

+ Identificación {#stitching}
   + [Información general](/help/stitching/overview.md)
   + [Vinculación basada en campos](/help/stitching/fbs.md)
   + [Vinculación basada en gráficos](/help/stitching/gbs.md)
   + [Usar vinculación](/help/stitching/use-stitching.md)
   + [Creación y administración de conjuntos de datos identificados](/help/stitching/stitching-ui.md)
   + [Preguntas frecuentes](/help/stitching/faq.md)

+ Integraciones de Adobe {#integrations}
   + [Información general](/help/integrations/overview.md)
   + [Integración de Adobe Analytics](/help/integrations/aa.md)
   + [Integración de Target](/help/integrations/at.md)
   + [Integración de datos de Journey Optimizer](/help/integrations/ajo.md)
   + [Integración de datos de gestión de decisiones](/help/integrations/ajo-od.md)
   + [Integración de la inteligencia artificial aplicada al cliente](/help/integrations/customer-ai.md)

+ Gobierno de datos {#cja-privacy}
   + [Gobernanza de datos](../privacy/privacy-overview.md)
   + [Registro de auditoría](../privacy/audit-log.md)
   + [Claves gestionadas por el cliente](../privacy/cmk.md)

+ Casos prácticos {#cja-usecases}
   + [Casos de uso de Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Datos de Google Analytics {#ga}
      + [Migración de datos de Google Analytics](../use-cases/ga/overview.md)
      + [Ingesta de datos históricos de Google Analytics](../use-cases/ga/backfill.md)
      + [Configuración del streaming de datos de Google Analytics](../use-cases/ga/streaming.md)
      + [Informe sobre datos de Google Analytics](../use-cases/ga/report.md)
   + Ingesta de datos {#data-ingestion}
      + [Ingesta y uso de datos de Marketo Engage](../use-cases/data-ingestion/marketo.md)
      + [Ingesta y uso de públicos de Experience Platform](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Vistas de datos {#data-views}
      + [Casos de uso de vistas de datos](/help/use-cases/data-views/data-views-usecases.md)
      + [Uso de dimensiones y métricas de enlace](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [Uso de datos de resumen](/help/use-cases/data-views/summary-data.md)
      + [Casos de uso de extensión de BI](/help/use-cases/data-views/bi-extension-usecases.md)
   + Exportación de datos {#data-export}
      + [Información general](../use-cases/data-export/overview.md)
      + [Extensión de BI](../use-cases/data-export/bi-extension.md)
      + [Exportar conjuntos de datos](../use-cases/data-export/export-datasets.md)
      + [Exportar tabla completa](../use-cases/data-export/export-full-table.md)
      + [Servicio de consultas y exportación de conjuntos de datos](../use-cases/data-export/queryservice-export-datasets.md)
   + B2B {#b2b}
      + [Ejemplo de proyecto B2B](../use-cases/b2b/example.md)
   + Datos multicanal {#cross-channel}
      + [Analizar datos en varios canales](../use-cases/cross-channel/cross-channel.md)
      + [Importación de datos web y de centros de llamadas](../use-cases/cross-channel/call-center.md)
   + Datos de Adobe Analytics {#aa-data}
      + [Uso de dimensiones del canal de marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinación de grupos de informes con diferentes esquemas](../use-cases/aa-data/combine-report-suites.md)
   + Datos complejos {#complex-data}
      + [Usar matrices de objetos](../use-cases/object-arrays.md)
   + Identificación {#stitching}
      + [Dispositivos compartidos](/help/use-cases/stitching/shared-devices.md)
   + Campos derivados {#derived-fields}
      + [Informe sobre metas](../use-cases/goals-using-derived-fields.md)

+ Labs {#labs}
   + [Guía del usuario de Labs](../labs/labs.md)

+ Resolución de problemas {#troubleshooting}
   + [Comparar datos](../troubleshooting/compare.md)
   + [Coherencia de métricas y audiencias](../troubleshooting/consistency-rcdp-cja.md)
   + [Falta de permisos](../troubleshooting/lack-of-permissions.md)

+ Notas técnicas {#technotes}
   + [Control de acceso](../technotes/access-control.md)
   + [Centros de datos](../technotes/data-centers.md)
   + [Implicaciones de la eliminación](../technotes/deletion.md)
   + [Dominios](../technotes/domains.md)
   + [Glosario](../technotes/glossary.md)
   + [Mecanismos de protección](../technotes/guardrails.md)
   + [Direcciones IP](../technotes/ip-addresses.md)
   + [Optimización del rendimiento](../technotes/optimizing-performance.md)
   + [Ver y administrar el uso](../technotes/estimate-usage.md)

+ [API de Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/)
+ [Análisis de contenido](/help/content-analytics.md)
