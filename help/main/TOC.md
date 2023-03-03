---
git-repo: https://github.com/AdobeDocs/analytics-platform.es-ES
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guía de Customer Journey Analytics
user-guide-description: Obtenga información acerca Customer Journey Analytics (CJA) y cómo utilizar Analysis Workspace con datos de Experience Platform.
breadcrumb-title: Guía de Customer Journey Analytics
source-git-commit: 9ea7184ecc13b310072e6f2f6d0ed5bf29abaa81
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 100%

---


# Guía de Customer Journey Analytics {#using}

+ [Guía de Customer Journey Analytics](../getting-started/cja-landing.md)

+ Notas de la versión {#releases}
   + [Última versión](../release-notes/latest.md)
   + [Versiones de 2023](../release-notes/2023.md)
   + [Versiones de 2022](../release-notes/2022.md)
   + [Versiones de 2021](../release-notes/2021.md)
   + [Versiones de 2020](../release-notes/2020.md)
   + [Versiones de CJA](../release-notes/releases.md)
   + [Actualizaciones de documentación de CJA](../release-notes/doc-changes.md)

+ Introducción {#cja-overview}
   + [Información general sobre Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Guía de inicio rápido](../getting-started/cja-getting-started.md)
   + [Página de aterrizaje](../getting-started/landing.md)
   + [Preguntas frecuentes](../getting-started/cja-faq.md)
   + [Comparar soluciones de CJA con las soluciones de BI](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics y Adobe Analytics {#compare-aa-cja}
   + [Evolución desde Adobe Analytics ](../getting-started/aa-to-cja.md)
   + [Guía para usuarios de Adobe Analytics](../getting-started/aa-to-cja-user.md)
   + Comparación con Adobe Analytics {#cja-aa-comparison}
      + [Utilizar los datos de Adobe Analytics en Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Compatibilidad con funciones de Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Comparación de terminología para datos de Analytics pasados a través del conector de origen de Analytics](../getting-started/aa-vs-cja/terminology.md)
      + [Comparar el procesamiento de datos entre Adobe Analytics y CJA](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Entornos de informes virtuales y entornos de zonas protegidas](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Reglas de procesamiento, VISTA y clasificaciones en comparación con la preparación de datos](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID y el conector de origen de Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ Ingesta de datos {#cja-data-ingestion}
   + [Información general sobre la ingesta de datos](../data-ingestion/data-ingestion.md)
   + Guías de inicio rápido de ingesta y uso {#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + [SDK web de Adobe Experience Platform y Edge Network](../data-ingestion/aepwebsdk.md)
      + [Datos por lotes](../data-ingestion/batch.md)
      + [Datos de streaming](../data-ingestion/streaming.md)
      + [Conectores de origen](../data-ingestion/sources.md)

+ Conexiones {#cja-connections}
   + [Información general sobre conexiones](../connections/overview.md)
   + [Crear una conexión](../connections/create-connection.md)
   + [Administrar conexiones](../connections/manage-connections.md)
   + [Conjuntos de datos de evento combinados](../connections/combined-dataset.md)
   + [Búsquedas estándar](../connections/standard-lookups.md)
   + [Análisis en canales múltiples](../connections/cca.md)

+ Vistas de datos {#cja-dataviews}
   + [Información general de las vistas de datos](../data-views/data-views.md)
   + [Creación o edición de una vista de datos](../data-views/create-dataview.md)
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
   + [Etiquetas y políticas](../data-views/data-governance.md)


+ Proyectos de Workspace {#cja-workspace}
   + [Información general de Analysis Workspace](../analysis-workspace/home.md)
   + [Realizar análisis básico](../analysis-workspace/perform-basic-analysis.md)
   + [Realizar análisis avanzado](../analysis-workspace/perform-adv-analysis.md)

   + Proyectos {#build-workspace-project}
      + [Información general sobre Proyectos](../analysis-workspace/build-workspace-project/freeform-overview.md)
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
         + [Paginación, filtrado y ordenación de tablas](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)

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
      + [Panel de información rápida](../analysis-workspace/c-panels/quickinsight.md)
      + [Panel de visualizadores simultáneos de medios](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + Tiempo invertido en la reproducción de medios {#media-playback-timespent}
         + [Información general](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [Configuración de entrada y salida](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [Preguntas frecuentes](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + Depuración, uso compartido y programación de proyectos {#curate-share}
      + [Menú Compartir](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Depurar proyectos de](../analysis-workspace/curate-share/curate.md)
      + [Compartir proyectos](../analysis-workspace/curate-share/share-projects.md)
      + [Crear vínculos que se pueden compartir](../analysis-workspace/curate-share/shareable-links.md)
      + [Proyectos de solo de vista](../analysis-workspace/curate-share/view-only-projects.md)
      + [Descarga de archivos PDF o CSV](../analysis-workspace/curate-share/download-send.md)
      + [Programar proyectos](../analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [Información general de Attribution](../analysis-workspace/attribution/overview.md)
      + [Modelos de atribución y ventanas retroactivas](../analysis-workspace/attribution/models.md)
      + [Atribución algorítmica](../analysis-workspace/attribution/algorithmic.md)
      + [Prácticas recomendadas de atribución](../analysis-workspace/attribution/best-practices.md)
      + [Preguntas más frecuentes](../analysis-workspace/attribution/faq.md)
   + Analista virtual {#virtual-analyst}
      + [Descripción general del analista virtual](../analysis-workspace/virtual-analyst/overview.md)
      + Detección de anomalías {#anomaly-detection}
         + [Resumen de la Detección de anomalías](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Visualización de anomalías en Analysis Workspace](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Técnicas estadísticas utilizadas en la detección de anomalías](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Preferencias de usuario](../analysis-workspace/user-preferences.md)

   + Preguntas frecuentes sobre de Workspace {#workspace-faq}
      + [Preguntas frecuentes](../analysis-workspace/workspace-faq/faq.md)
      + [Optimizar rendimiento de Analysis Workspace](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Mensajes de error](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limitaciones de Analysis Workspace](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisitos de administración](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accesibilidad en Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Long-tail en Analysis Workspace](../analysis-workspace/workspace-faq/long-tail.md)












+ Componentes {#cja-components}
   + [Resumen de componentes](../components/overview.md)
   + Anotaciones {#annotations}
      + [Descripción general de anotaciones](../components/annotations/overview.md)
      + [Creación de anotaciones](../components/annotations/create-annotations.md)
      + [Administración de anotaciones](../components/annotations/manage-annotations.md)
      + [Visualización de anotaciones](../components/annotations/view-annotations.md)
      + [Anotaciones móviles](../components/annotations/mobile-annotations.md)
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
      + [Crear un filtro](../components/filters/create-filters.md)
      + [Administrar filtros](../components/filters/manage-filters.md)
      + [Filtros rápidos](../components/filters/quick-filters.md)
      + [Filtros ad hoc](../components/filters/ad-hoc-filters.md)
      + [Operadores](../components/filters/operators.md)
   + Métricas calculadas {#cja-calcmetrics}
      + [Información general sobre las métricas calculadas](../components/calc-metrics/calc-metr-overview.md)
      + Flujo de trabajo de las métricas calculadas {#cm-workflow}
         + [Flujo de trabajo de las métricas calculadas](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Buscar métricas](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Generar métricas](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Tipo de métrica y atribución](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Generar una métrica “Vistas de página por visitas” simple](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Métricas filtradas](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Apilar y sustituir segmentos](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Métricas filtradas y ponderadas](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Uso de funciones](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Métrica de participación](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Etiquetar métricas calculadas](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Aprobar métricas calculadas](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Compartir métricas calculadas](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Administrador de métricas calculadas](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Funciones básicas](../components/calc-metrics/cm-functions.md)
      + [Funciones avanzadas](../components/calc-metrics/cm-adv-functions.md)
   + Intervalos de fechas {#cja-date-ranges}
      + [Información general sobre los intervalos de fechas](../components/date-ranges/overview.md)
      + [Crear un intervalo de fecha](../components/date-ranges/create.md)
      + [Administrar intervalos de fechas](../components/date-ranges/manage.md)
      + [Información general del calendario](../components/date-ranges/calendar.md)
      + [Crear intervalos de fechas](../components/date-ranges/custom-date-ranges.md)
      + [Comparación de fechas](../components/date-ranges/time-comparison.md)

+ Paneles de Analytics {#cja-dashboards}
   + [Paneles de Analytics: Información general](../mobile-app/home.md)
   + [Tareas del gestor de datos](../mobile-app/curator.md)
   + [Creación de un cuadro de resultados móvil](../mobile-app/create-scorecard.md)
   + [Configuración de ejecutivos para que utilicen paneles](../mobile-app/set-up-execs.md)
   + [Guía de inicio rápida para el usuario ejecutivo](../mobile-app/executive.md)

+ Report Builder {#cja-reportbuilder}
   + [Información general de Report Builder](../report-builder/report-buider-overview.md)
   + [Configuración de Report Builder](../report-builder/report-builder-setup.md)
   + [Creación de un bloque de datos](../report-builder/create-a-data-block.md)
   + [Report Builder Hub](../report-builder/report-builder-hub.md)
   + [Selección de un intervalo de fechas](../report-builder/select-date-range.md)
   + [Trabajo con filtros](../report-builder/work-with-filters.md)
   + [Filtrar dimensiones](../report-builder/filter-dimensions.md)
   + [Administrar bloques de datos](../report-builder/manage-reportbuilder.md)
   + [Programar libros de trabajo](../report-builder/schedule-reportbuilder.md)
   + [Etiquetas restringidas](../report-builder/restricted-labels.md)
   + [Configuración de Report Builder](../report-builder/report-builder-settings.md)

+ Análisis en canales múltiples {#cca}
   + [Información general sobre Análisis en canales múltiples](../cca/overview.md)
   + [Cómo funcionan las reproducciones](../cca/replay.md)
   + [Preguntas frecuentes sobre Análisis en canales múltiples](../cca/faq.md)

+ Integraciones de Adobe {#integrations}
   + [Información general sobre la integración de soluciones de Adobe con CJA](/help/integrations/overview.md)
   + [Integración de soluciones de Adobe Analytics con Customer Journey Analytics](/help/integrations/aa.md)
   + [Integración de datos de Journey Optimizer con CJA](/help/integrations/ajo.md)
   + [Integración de datos de inteligencia artificial aplicada al cliente con CJA](/help/integrations/customer-ai.md)

+ Gobierno de datos {#cja-privacy}
   + [Gobernanza de datos](../privacy/privacy-overview.md)
   + [Registro de auditoría](../privacy/audit-log.md)
   + [Claves gestionadas por el cliente](../privacy/cmk.md)

+ Casos prácticos {#cja-usecases}
   + [Casos de uso de Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Datos de Google Analytics {#ga}
      + [Información general sobre la migración de datos de Google Analytics a CJA](../use-cases/ga/overview.md)
      + [Ingesta de datos históricos de Google Analytics en Platform](../use-cases/ga/backfill.md)
      + [Configuración del streaming de los datos de Google Analytics a Platform](../use-cases/ga/streaming.md)
      + [Informe sobre datos de Google Analytics en CJA](../use-cases/ga/report.md)
   + Ingesta de datos {#data-ingestion}
      + [Ingesta de datos de Marketo Engage en AEP e informes en CJA](../use-cases/data-ingestion/marketo.md)
      + [Ingesta de audiencias de AEP en CJA](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Vistas de datos {#data-views}
      + [Casos de uso de vistas de datos](../use-cases/data-views/data-views-usecases.md)
      + [Uso de dimensiones y métricas de enlace](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [Añadir datos de nivel de cuenta como un conjunto de datos de consulta](../use-cases/b2b/b2b.md)
   + Datos multicanal {#cross-channel}
      + [Analizar datos en varios canales](../use-cases/cross-channel/cross-channel.md)
      + [Importación de datos web y de centros de llamadas](../use-cases/cross-channel/call-center.md)
   + Datos de Adobe Analytics {#aa-data}
      + [Uso de dimensiones del canal de marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinación de grupos de informes con diferentes esquemas](../use-cases/aa-data/combine-report-suites.md)
   + Datos complejos {#complex-data}
      + [Usar matrices de objetos](../use-cases/object-arrays.md)

+ Administración {#cja-admin}
   + [Control de acceso](../admin/cja-access-control.md)
   + [Ver y administrar el uso](../admin/estimate-usage.md)
   + [Implicaciones de eliminación](../admin/cja-deletion.md)

+ Labs {#labs}
   + [Guía del usuario de Labs](../labs/labs.md)

+ Resolución de problemas {#troubleshooting}
   + [Comparación de los datos de Adobe Analytics con los de CJA](../troubleshooting/compare.md)
   + [Coherencia de métricas y recuentos de miembros de audiencia entre Real-time CDP y CJA](../troubleshooting/consistency-rcdp-cja.md)

+ [Glosario de CJA](../getting-started/cja-glossary.md)

+ [API de CJA](https://developer.adobe.com/cja-apis/docs/)
