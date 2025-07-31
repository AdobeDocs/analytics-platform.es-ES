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
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1278'
ht-degree: 99%

---

# Guía de Adobe Customer Journey Analytics {#using}

+ [Guía de Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Notas de la versión  {#releases}
   + [Última versión de Customer Journey Analytics](../release-notes/latest.md)
   + [Notas de la versión preliminar de Customer Journey Analytics](../release-notes/pre-release-notes.md)
   + [Versiones de 2025](../release-notes/2025.md)
   + [Versiones de 2024](../release-notes/2024.md)
   + [Versiones de 2023](../release-notes/2023.md)
   + [Versiones de 2022](../release-notes/2022.md)
   + [Versiones de 2021](../release-notes/2021.md)
   + [Versiones de 2020](../release-notes/2020.md)
   + [Estrategia de lanzamiento de funciones](../release-notes/releases.md)
   + [Actualizaciones de documentación](../release-notes/doc-changes.md)

+ Introducción {#cja-overview}
   + Customer Journey Analytics {#cja-b2c-overview}
      + [Información general](../getting-started/cja-overview.md)
      + [Guía de inicio rápido](../getting-started/cja-getting-started.md)
      + [Página de destino](../getting-started/landing.md)
      + [Preguntas frecuentes](../getting-started/cja-faq.md)
      + [Comparar soluciones con las soluciones de BI](../getting-started/cja-vs-bi.md)
      + [Asistente de IA](../ai-assistant.md)
      + [Data Insights Agent](../data-analysis-ai.md)
   + Customer Journey Analytics B2B Edition {#cja-b2b}
      + [Información general](/help/getting-started/cja-b2b-edition.md)
      + [Conceptos y funciones de B2B](/help/getting-started/cja-b2b-concepts-features.md)
      + [Guía de inicio rápido](/help/getting-started/cja-b2b-quick-start-guide.md)
      + [Guía de transición](/help/getting-started/cja-b2b-transition.md)

+ Actualizar y comparar {#compare-aa-cja}
   + Actualizar a Customer Journey Analytics {#upgrade-to-cja}
      + [Introducción](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Elegir la ruta de actualización](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Enviar datos a Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Conservar datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [Proceso de actualización recomendado](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + Arquitecto y creación de un esquema {#schema}
         + [Diseña tu esquema](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
         + [Cree su esquema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
         + [Usa el esquema existente](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + Crear un flujo de datos {#create-datastream}
         + [Crear un flujo de datos](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
         + [Añade Platform como servicio](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + Creación de conjuntos de datos {#create-datasets}
         + [Creación de un conjunto de datos](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
         + [Creación de conjuntos de datos de búsqueda para clasificaciones](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
         + [Monitorización de la ingesta de datos](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + Implementación de Web SDK con etiquetas {#create-tags}
         + [Creación de una etiqueta para su propiedad](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
         + [Añada la extensión del SDK web a la etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
         + [Implementar la etiqueta de carga para la extensión del SDK web](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
         + [Añada la lógica de recopilación de datos XDM a la etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [Implementar el SDK Web manualmente](/help/getting-started/cja-upgrade/cja-upgrade-manual.md)
      + [Implementar el Web SDK con la API](/help/getting-started/cja-upgrade/cja-upgrade-api.md)
      + [Crea una conexión](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [Crea una vista de datos](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [Creación de un campo derivado del canal de marketing](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Validar el flujo de datos](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [Configurar la colección de medios de streaming](/help/getting-started/cja-upgrade/cja-upgrade-streaming-media.md)
      + Conservación de datos históricos con el conector de origen de Analytics {#historical-data-source-connector}
         + [Crear un esquema XDM para el conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
         + [Creación del conector de origen de Analytics y asignación de campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
         + [Adición del conjunto de datos del conector de origen de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Evaluar cuándo deshabilitar Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)
      + [Deshabilitación de Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + Métodos de actualización alternativos {#alternative-upgrade-methods}
         + [Uso de la recopilación de datos de AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)
         + [Enviar capa de datos](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)
         + [Conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)
      + Otros escenarios de actualización {#other-upgrade-scenarios}
         + [Movimiento desde el conector de origen de Analytics al SDK web](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
         + [Actualización desde una solución que no es de Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + Información adicional {#additional-information}
         + [Comprender la implementación de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
         + [Compatibilidad con funciones de Adobe Analytics al actualizar](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
         + [Funcionalidades de Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md)
         + [Opciones de implementación de Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md)
         + [Configuración de Adobe Analytics Web SDK para Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)
         + [Uso de la personalización con Adobe Journey Optimizer](/help/getting-started/cja-upgrade/cja-upgrade-personalization-journeyoptimizer.md)
   + Comparar con Adobe Analytics {#cja-aa-comparison}
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
      + [Incluir valores de exclusión](../data-views/component-settings/include-exclude-values.md)
      + [Anulación de duplicación métrica](../data-views/component-settings/metric-deduplication.md)
      + [Sin opciones de valor](../data-views/component-settings/no-value-options.md)
      + [Persistencia](../data-views/component-settings/persistence.md)
      + [Subcadena](../data-views/component-settings/substring.md)
      + [Grupo de datos de resumen](../data-views/component-settings/summary-data-group.md)
      + [Creación de depósitos](../data-views/component-settings/value-bucketing.md)
   + [Referencia de componente estándar](../data-views/component-reference.md)
   + [Extensión de BI](../data-views/bi-extension.md)
   + [Campos derivados](../data-views/derived-fields/derived-fields.md)
   + [Campos derivados (limitados)](../data-views/derived-fields/derived-fields-limited.md)
   + [Datos de resumen](../data-views/summary-data.md)
   + [Etiquetas y políticas](../data-views/data-governance.md)
   + Métricas y dimensiones compartidas{#shared-metrics-dimensions}
      + [Información general](/help/data-views/shared-metrics-dimensions/smd-overview.md)
      + [Editor](/help/data-views/shared-metrics-dimensions/shared-component-editor.md)

+ Herramientas {#tools}
   + Transferencia de recursos {#asset-transfer}
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
      + [Iniciar proyectos rápidamente](/help/analysis-workspace/build-workspace-project/starter-projects.md)
      + [Crear proyectos](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Abrir proyectos](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Comentario en proyectos](/help/analysis-workspace/build-workspace-project/comment-projects.md)
      + [Guardar proyectos](../analysis-workspace/build-workspace-project/save-projects.md)
      + [Tabla de contenido](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
      + Carpetas en Workspace {#workspace-folders}
         + [Información general](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Creación de carpetas](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Administración de carpetas](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Añadir o mover proyectos](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Teclas de acceso directo](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Paletas de color](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Ver densidad](../analysis-workspace/build-workspace-project/view-density.md)
      + [Depurador](../analysis-workspace/build-workspace-project/debugger.md)
   + Plantillas {#templates}
      + [Uso de plantillas](../analysis-workspace/templates/use-templates.md)
      + [Creación y administración de plantillas](../analysis-workspace/templates/create-templates.md)
   + Visualizaciones {#visualizations}
      + [Información general](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Administración de fuentes de datos](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [Subtítulos inteligentes](../analysis-workspace/visualizations/intelligent-captions.md)
      + Tabla de forma libre {#freeform-table}
         + [Información general](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [Crear hipervínculos](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + Configuración de columna y fila {#column-row-settings}
            + [Configuración de columna](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Configuración de filas](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Elementos dinámicos y estáticos](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrar y ordenar](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totales](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabla de cohortes {#cohort-table}
         + [Información general](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configuración](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casos de uso](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Visita en orden previsto {#fallout}
         + [Información general](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configuración](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Visita en orden previsto entre dimensiones](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Aplicar segmentos](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flujo {#flow}
         + [Información general](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configuración](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flujos interdimensionales](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + Lienzo de recorrido  {#journey-canvas}
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
      + [Disperso](../analysis-workspace/visualizations/scatterplot.md)
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
      + [Visualizadores simultáneos de medios](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Tiempo invertido en la reproducción de medios](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Elemento siguiente o anterior](../analysis-workspace/c-panels/next-previous.md)
      + [Acceso rápido a información](../analysis-workspace/c-panels/quickinsight.md)
   + Depurar y compartir {#curate-share}
      + [Información general](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Depurar proyectos de](../analysis-workspace/curate-share/curate.md)
      + [Compartir proyectos](../analysis-workspace/curate-share/share-projects.md)
      + [Crear vínculos que se pueden compartir](../analysis-workspace/curate-share/shareable-links.md)
      + [Proyectos de solo lectura](../analysis-workspace/curate-share/view-only-projects.md)
   + Exportar {#export}
      + [Información general](../analysis-workspace/export/export-project-overview.md)
      + [Descargar](../analysis-workspace/export/download-send.md)
      + [Enviar y programar](../analysis-workspace/export/t-schedule-report.md)
      + [Exportar a la nube](../analysis-workspace/export/export-cloud.md)
   + Atribución {#attribution}
      + [Información general de Attribution](../analysis-workspace/attribution/overview.md)
      + [Modelo, contenedor y ventana retrospectiva](../analysis-workspace/attribution/models.md)
      + [Atribución algorítmica](../analysis-workspace/attribution/algorithmic.md)
      + [Prácticas recomendadas](../analysis-workspace/attribution/best-practices.md)
      + [Preguntas frecuentes](../analysis-workspace/attribution/faq.md)
   + Detección de anomalías {#anomaly-detection}
      + [Información general](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Ver anomalías](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Técnicas estadísticas](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Previsión {#forecasting}
      + [Información general](../analysis-workspace/c-forecast/forecasting.md)
      + [Ver previsiones](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Técnicas estadísticas](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Preferencias de usuario](../analysis-workspace/user-preferences.md)
   + Preguntas frecuentes sobre Workspace y más {#workspace-faq}
      + [Preguntas frecuentes](../analysis-workspace/workspace-faq/faq.md)
      + [Optimización del rendimiento](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Errores y solución de problemas](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limitaciones](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisitos](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accesibilidad](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Análisis de contenido {#content-analytics}
   + [Información general](/help/content-analytics/content-analytics.md)
   + Informe {#report}
      + [Información general](/help/content-analytics/report/report.md)
      + [Componentes](/help/content-analytics/report/components.md)
   + Configuración {#configuration}
      + [Información general](/help/content-analytics/config/configuration.md)
      + [Configuración guiada](/help/content-analytics/config/guided.md)
      + [Configuración manual](/help/content-analytics/config/manual.md)
      + [Recopilación de datos](/help/content-analytics/config/datacollection.md)

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
   + [Impacto de la versión](../guided-analysis/types/release-impact.md)
   + [Retención](../guided-analysis/types/retention.md)
   + [Cronología](../guided-analysis/types/timeline.md)
   + [Tendencias](../guided-analysis/types/trends.md)
   + [Casos de uso del sector](../guided-analysis/industry-use-cases.md)
   + [Preguntas frecuentes](../guided-analysis/faq.md)

+ Componentes {#cja-components}
   + [Información general](../components/overview.md)
   + [Uso de componentes](../components/use-components-in-workspace.md)
   + [Adición de descripciones de componentes](../components/add-component-descriptions.md)
   + Anotaciones {#annotations}
      + [Información general](../components/annotations/overview.md)
      + [Creación de anotaciones](../components/annotations/create-annotations.md)
      + [Administración de anotaciones](../components/annotations/manage-annotations.md)
      + [Visualización de anotaciones](../components/annotations/view-annotations.md)
      + [Anotaciones de cuadros de resultados móviles](../components/annotations/mobile-annotations.md)
   + Audiencias {#audiences}
      + [Descripción general de las audiencias](../components/audiences/audiences-overview.md)
      + [Creación y publicación de públicos](../components/audiences/publish.md)
      + [Administrar públicos](../components/audiences/manage.md)
   + Dimensiones {#dimensions}
      + [Información general](../components/dimensions/overview.md)
      + [Vista preliminar de dimensiones](../components/dimensions/view-dimensions.md)
      + [Desglose de dimensiones](../components/dimensions/t-breakdown-fa.md)
      + [Dimensiones de partición de tiempo](../components/dimensions/time-parting-dimensions.md)
      + [Dimensiones de alta cardinalidad](../components/dimensions/high-cardinality.md)
   + [Métricas](../components/apply-create-metrics.md)
   + Segmentos {#segments}
      + [Información general](/help/components/segments/seg-overview.md)
      + [Crear segmentos](/help/components/segments/seg-create.md)
      + [Generación de segmentos](/help/components/segments/seg-builder.md)
      + [Segmentos rápidos](/help/components/segments/seg-quick.md)
      + [Segmentos secuenciales](/help/components/segments/seg-sequential-build.md)
      + [Compartir segmentos](/help/components/segments/seg-share.md)
      + [Etiquetar segmentos](/help/components/segments/seg-tag.md)
      + [Filtrar la lista de segmentos](/help/components/segments/seg-filter.md)
      + [Marcar segmentos como favoritos](/help/components/segments/seg-favorite.md)
      + [Aprobar segmentos](/help/components/segments/seg-approve.md)
      + [Copiar segmentos](/help/components/segments/seg-copy.md)
      + [Administración de segmentos](/help/components/segments/seg-manage.md)
      + [Operadores](/help/components/segments/seg-operators.md)
      + [Uso de segmentos](/help/components/segments/seg-use.md)
   + Métricas calculadas  {#cja-calcmetrics}
      + [Información general](../components/calc-metrics/calc-metr-overview.md)
      + Flujo de trabajo {#cm-workflow}
         + [Crear métricas calculadas](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Buscar métricas](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Crear métricas calculadas](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Un ejemplo sencillo](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Un ejemplo más complejo](../components/calc-metrics/cm-workflow/cm-orders-participation.md)
         + [Tipo de métrica y atribución](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Métricas de participación](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Métricas segmentadas](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Apilar y sustituir segmentos](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
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
   + Creación de informes en tiempo real {#real-time-reporting}
      + [Información general](/help/components/real-time/real-time.md)
      + [Uso de creación de informes en tiempo real](/help/components/real-time/use-real-time.md)
   + [Proyectos programados](../components/scheduled-projects-manager.md)
+ Report Builder {#cja-reportbuilder}
   + [Información general](../report-builder/rb-overview.md)
   + [Configuración de Report Builder](../report-builder/report-builder-setup.md)
   + [Creación de un bloque de datos](../report-builder/create-a-data-block.md)
   + [Hub de Report Builder](../report-builder/report-builder-hub.md)
   + [Seleccione una vista de datos](../report-builder/select-data-view.md)
   + [Selección de un intervalo de fechas](../report-builder/select-date-range.md)
   + [Trabajar con segmentos](../report-builder/work-with-filters.md)
   + [Filtrar dimensiones](../report-builder/filter-dimensions.md)
   + [Administrar bloques de datos](../report-builder/manage-reportbuilder.md)
   + [Programar libros para correo electrónico](../report-builder/schedule-reportbuilder.md)
   + [Programar libros para exportaciones en la nube](../report-builder/report-builder-export.md)
   + [Administrar programaciones de libros](/help/report-builder/manage-schedules-reportbuilder.md)
   + [Etiquetas restringidas](../report-builder/restricted-labels.md)
   + [Configuración de Report Builder](../report-builder/report-builder-settings.md)


+ Administrador de actividades de creación de informes {#reporting-activity-manager}
   + [Información general](../reporting-activity-manager/reporting-activity-overview.md)
   + [Visualización de la actividad de creación de informes](../reporting-activity-manager/reporting-activity.md)
   + [Cancelación de solicitudes de creación de informes](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Unión {#stitching}
   + [Información general](/help/stitching/overview.md)
   + [Vinculación basada en campos](/help/stitching/fbs.md)
   + [Vinculación basada en gráficos](/help/stitching/gbs.md)
   + [Usar vinculación](/help/stitching/use-stitching.md)
   + [Creación y administración de conjuntos de datos identificados](/help/stitching/stitching-ui.md)
   + [Validar vinculación](/help/stitching/validate.md)
   + [Preguntas frecuentes](/help/stitching/faq.md)

+ Integraciones de Adobe {#integrations}
   + [Información general](/help/integrations/overview.md)
   + [Integración de Adobe Analytics](/help/integrations/aa.md)
   + [Integración de Target](/help/integrations/at.md)
   + [Integración de datos de Journey Optimizer](/help/integrations/ajo.md)
   + [Integración de datos de gestión de decisiones](/help/integrations/ajo-od.md)
   + [Integración de la inteligencia artificial aplicada al cliente](/help/integrations/customer-ai.md)

+ Gobernanza de datos {#cja-privacy}
   + [Gobernanza de datos](../privacy/privacy-overview.md)
   + [Registro de auditoría](../privacy/audit-log.md)
   + [Claves gestionadas por el cliente](../privacy/cmk.md)

+ Casos prácticos {#cja-usecases}
   + [Casos de uso de Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Datos de Adobe Analytics {#aa-data}
      + [Uso de dimensiones del canal de marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinación de grupos de informes con diferentes esquemas](../use-cases/aa-data/combine-report-suites.md)
   + B2B {#b2b}
      + [Un ejemplo de proyecto B2B basado en personas](../use-cases/b2b/example.md)
      + B2B Edition {#b2b-edition}
         + [Información general de casos de uso](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)
         + [Configuración](/help/use-cases/b2b/b2b-edition/setup.md)
         + [Optimización del marketing de cuentas](/help/use-cases/b2b/b2b-edition/optimize-account-marketing.md)
         + [Ampliación de cuentas clave](/help/use-cases/b2b/b2b-edition/grow-key-accounts.md)
         + [Generar valor de producto](/help/use-cases/b2b/b2b-edition/build-product-value.md)
   + Datos complejos {#complex-data}
      + [Usar matrices de objetos](../use-cases/object-arrays.md)
   + Datos de canales múltiples {#cross-channel}
      + [Analizar datos en varios canales](../use-cases/cross-channel/cross-channel.md)
      + [Importación de datos web y de centros de llamadas](../use-cases/cross-channel/call-center.md)
   + Exportación de datos {#data-export}
      + [Información general](../use-cases/data-export/overview.md)
      + [Extensión de BI](../use-cases/data-export/bi-extension.md)
      + [Exportar conjuntos de datos](../use-cases/data-export/export-datasets.md)
      + [Exportar tabla completa](../use-cases/data-export/export-full-table.md)
      + [Servicio de consultas y exportación de conjuntos de datos](../use-cases/data-export/queryservice-export-datasets.md)
   + Ingesta de datos {#data-ingestion}
      + [Ingesta y uso de datos de Marketo Engage](../use-cases/data-ingestion/marketo.md)
      + [Ingesta y uso de públicos de Experience Platform](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Vistas de datos {#data-views}
      + [Casos de uso de vistas de datos](/help/use-cases/data-views/data-views-usecases.md)
      + [Uso de dimensiones y métricas de enlace](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [Uso de datos de resumen](/help/use-cases/data-views/summary-data.md)
      + [Casos de uso de extensión de BI](/help/use-cases/data-views/bi-extension-usecases.md)
   + Campos derivados {#derived-fields}
      + [Informe sobre metas](../use-cases/goals-using-derived-fields.md)
   + Análisis de productos {#product-analysis}
      + [Análisis de productos](/help/use-cases/product-analysis.md)
   + Unión {#stitching}
      + [Dispositivos compartidos](/help/use-cases/stitching/shared-devices.md)
   + Datos de terceros {#third-party}
      + [Información general](/help/use-cases/third-party/overview.md)
      + Google Analytics {#ga}
         + [Migración de datos de Google Analytics](/help/use-cases/third-party/ga/overview.md)
         + [Ingesta de datos históricos de Google Analytics](/help/use-cases/third-party/ga/backfill.md)
         + [Configuración del streaming de datos de Google Analytics](/help/use-cases/third-party/ga/streaming.md)
         + [Informe sobre datos de Google Analytics](/help/use-cases/third-party/ga/report.md)
      + Métrica cuántica {#qm}
         + [Información general](/help/use-cases/third-party/quantum-metric/qm-overview.md)
         + [Vincular reproducciones de sesión](/help/use-cases/third-party/quantum-metric/tie-session-replays.md)
         + [Usar mapas de calor](/help/use-cases/third-party/quantum-metric/heatmap.md)
         + [Añadir eventos de fricción](/help/use-cases/third-party/quantum-metric/friction-events.md)
         + [Conector de fuente](/help/use-cases/third-party/quantum-metric/source-connector.md)

+ Labs {#labs}
   + [Guía del usuario de Labs](../labs/labs.md)

+ Solución de problemas {#troubleshooting}
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
   + [Administrar uso](../technotes/estimate-usage.md)

+ [API de Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/)
