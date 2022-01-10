---
git-repo: https://git.corp.adobe.com/AdobeDocs/analytics-platform.es-ES
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guía de Customer Journey Analytics
user-guide-description: Esta guía proporciona ayuda para Customer Journey Analytics, la solución de nueva generación de Adobe para Análisis entre canales, basada en Adobe Experience Platform.
breadcrumb-title: Guía de Customer Journey Analytics
source-git-commit: 6c5fb7b3964cbf2bb5158733a2ede9b54f9415a5
workflow-type: ht
source-wordcount: '556'
ht-degree: 100%

---


# Guía de Customer Journey Analytics {#using}

+ [Guía de Customer Journey Analytics](getting-started/cja-landing.md)
+ Información general sobre Customer Journey Analytics {#cja-overview}
   + [Información general sobre Customer Journey Analytics](getting-started/cja-overview.md)
   + [Introducción](getting-started/cja-getting-started.md)
   + [Preguntas frecuentes](getting-started/cja-faq.md)
   + [Compatibilidad con funciones de Customer Journey Analytics](getting-started/cja-aa.md)
   + [Implicaciones de eliminación](getting-started/cja-deletion.md)
   + [Glosario de CJA](getting-started/cja-glossary.md)
+ Conexiones {#cja-connections}
   + [Crear una conexión](connections/create-connection.md)
   + [Administrar conexiones](connections/manage-connections.md)
   + [Cálculo del tamaño de la conexión](connections/estimate-connection-size.md)
   + [Conjuntos de datos de evento combinados](connections/combined-dataset.md)
   + [Búsquedas estándar](connections/standard-lookups.md)
   + Análisis entre canales {#cca}
      + [Información general sobre Análisis entre canales](connections/cca/overview.md)
      + [Cómo funcionan las reproducciones](connections/cca/replay.md)
      + [Preguntas frecuentes sobre Análisis entre canales](connections/cca/faq.md)
+ Vistas de datos {#cja-dataviews}
   + [Información general de las vistas de datos](data-views/data-views.md)
   + [Creación o edición de una fuente de datos](data-views/create-dataview.md)
   + Configuración de componentes {#component-settings}
      + [Información general sobre la configuración de componentes](data-views/component-settings/overview.md)
      + [Atribución](data-views/component-settings/attribution.md)
      + [Comportamiento](data-views/component-settings/behavior.md)
      + [Formato](data-views/component-settings/format.md)
      + [Incluir/excluir valores](data-views/component-settings/include-exclude-values.md)
      + [Anulación de duplicación métrica](data-views/component-settings/metric-deduplication.md)
      + [Sin opciones de valor](data-views/component-settings/no-value-options.md)
      + [Persistencia](data-views/component-settings/persistence.md)
      + [Clasificación de valor](data-views/component-settings/value-bucketing.md)
   + [Referencia de componente estándar](data-views/component-reference.md)
   + [Casos de uso de vistas de datos](data-views/data-views-usecases.md)
+ Proyectos del Espacio de trabajo {#cja-workspace}
   + [Información general de Analysis Workspace](analysis-workspace/home.md)
   + [Realizar análisis básico](analysis-workspace/perform-basic-analysis.md)
   + [Realizar análisis avanzado](analysis-workspace/perform-adv-analysis.md)
   + Proyectos {#build-workspace-project}
      + [Información general sobre Proyectos](analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Guardar proyectos](analysis-workspace/build-workspace-project/save-projects.md)
      + [Teclas de acceso directo (métodos abreviados)](analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Paletas de color](analysis-workspace/build-workspace-project/color-palettes.md)
      + [Ver densidad](analysis-workspace/build-workspace-project/view-density.md)
   + Visualizaciones {#visualizations}
      + [Resumen de las visualizaciones](analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Administración de fuentes de datos](analysis-workspace/visualizations/t-sync-visualization.md)
      + Tabla de forma libre {#freeform-table}
         + [Tabla improvisada](analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Configuración de columna y fila {#column-row-settings}
            + [Configuración de columna](analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Configuración de filas](analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Elementos dinámicos vs. estáticos](analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Paginación, filtrado y ordenación de tablas](analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md)
         + [Totales del Espacio de trabajo](analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabla de cohorte {#cohort-table}
         + [¿Qué es el análisis de cohorte?](analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurar un informe de análisis de cohorte](analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casos de uso de análisis de cohorte](analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Abandono {#fallout}
         + [Resumen de abandonos](analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurar una visualización de abandonos](analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Abandonos entre dimensiones](analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Aplicar filtros en un análisis de visitas en orden previsto](analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flujo {#flow}
         + [Resumen de flujos](analysis-workspace/visualizations/c-flow/flow.md)
         + [Configuración de una visualización de flujo](analysis-workspace/visualizations/c-flow/creating-flow-report.md)
         + [Configuración de flujo](analysis-workspace/visualizations/c-flow/flow-settings.md)
         + [Flujos interdimensionales](analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Histograma](analysis-workspace/visualizations/histogram.md)
      + [Venn](analysis-workspace/visualizations/venn.md)
      + [Área y área apilada](analysis-workspace/visualizations/area.md)
      + [Barra y barra apilada](analysis-workspace/visualizations/bar.md)
      + [Gráfico de viñetas](analysis-workspace/visualizations/bullet-graph.md)
      + [Anillo](analysis-workspace/visualizations/donut.md)
      + [Barras horizontales y barras horizontales apiladas](analysis-workspace/visualizations/horizontal-bar.md)
      + [Líneas](analysis-workspace/visualizations/line.md)
      + [Diagrama de dispersión](analysis-workspace/visualizations/scatterplot.md)
      + [Número de resumen y cambio de resumen](analysis-workspace/visualizations/summary-number-change.md)
      + [Texto](analysis-workspace/visualizations/text.md)
      + [Mapa de árbol](analysis-workspace/visualizations/treemap.md)
   + Paneles {#panels}
      + [Resumen de paneles](analysis-workspace/c-panels/panels.md)
      + [Panel de Attribution](analysis-workspace/c-panels/attribution.md)
      + [Panel en blanco](analysis-workspace/c-panels/blank-panel.md)
      + [Panel de forma libre](analysis-workspace/c-panels/freeform-panel.md)
      + [Panel de información rápida](analysis-workspace/c-panels/quickinsight.md)
   + Depuración, uso compartido y programación de proyectos {#curate-share}
      + [Menú Compartir](analysis-workspace/curate-share/send-schedule-files.md)
      + [Depurar proyectos de](analysis-workspace/curate-share/curate.md)
      + [Compartir proyectos](analysis-workspace/curate-share/share-projects.md)
      + [Crear vínculos que se pueden compartir](analysis-workspace/curate-share/shareable-links.md)
      + [Proyectos de solo de vista](analysis-workspace/curate-share/view-only-projects.md)
      + [Descarga de archivos PDF o CSV](analysis-workspace/curate-share/download-send.md)
      + [Programar proyectos](analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [Información general de Attribution](analysis-workspace/attribution/overview.md)
      + [Modelos de atribución y ventanas retroactivas](analysis-workspace/attribution/models.md)
      + [Atribución algorítmica](analysis-workspace/attribution/algorithmic.md)
      + [Prácticas recomendadas de atribución](analysis-workspace/attribution/best-practices.md)
      + [Preguntas más frecuentes](analysis-workspace/attribution/faq.md)
   + Analista virtual {#virtual-analyst}
      + [Descripción general del analista virtual](analysis-workspace/virtual-analyst/overview.md)
      + Detección de anomalías {#anomaly-detection}
         + [Resumen de la Detección de anomalías](analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Visualización de anomalías en Analysis Workspace](analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Técnicas estadísticas utilizadas en la detección de anomalías](analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Preferencias del usuario](analysis-workspace/user-preferences.md)
   + Preguntas frecuentes sobre del Espacio de trabajo {#workspace-faq}
      + [Preguntas frecuentes](analysis-workspace/workspace-faq/faq.md)
      + [Optimizar rendimiento de Analysis Workspace](analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Mensajes de error](analysis-workspace/workspace-faq/error-messages.md)
      + [Limitaciones de Analysis Workspace](analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisitos de administración](analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accesibilidad en Analysis Workspace](analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Long-tail en Analysis Workspace](analysis-workspace/workspace-faq/long-tail.md)
+ Report Builder {#cja-reportbuilder}
   + [Información general de Report Builder](report-builder/report-buider-overview.md)
   + [Configuración de Report Builder](report-builder/report-builder-setup.md)
   + [Creación de un bloque de datos](report-builder/create-a-data-block.md)
   + [Report Builder Hub](report-builder/report-builder-hub.md)
   + [Selección de un intervalo de fechas](report-builder/select-date-range.md)
   + [Trabajo con filtros](report-builder/work-with-filters.md)
   + [Filtrar dimensiones](report-builder/filter-dimensions.md)
   + [Configuración de Report Builder](report-builder/report-builder-settings.md)
+ Componentes {#cja-components}
   + [Resumen de componentes](components/overview.md)
   + Dimensiones {#dimensions}
      + [Vista preliminar de dimensiones](components/dimensions/view-dimensions.md)
      + [Desglose de dimensiones](components/dimensions/t-breakdown-fa.md)
      + [Dimensiones de partición de tiempo](components/dimensions/time-parting-dimensions.md)
      + [Dimensión con muy alta cardinalidad](components/dimensions/high-cardinality.md)
   + [Métricas](components/apply-create-metrics.md)
   + Filtros {#cja-filters}
      + [Información general de Filtros](components/filters/filters-overview.md)
      + [Crear un filtro](components/filters/create-filters.md)
      + [Administrar filtros](components/filters/manage-filters.md)
      + [Filtros rápidos](components/filters/quick-filters.md)
      + [Filtros específicos](components/filters/ad-hoc-filters.md)
      + [Operadores](components/filters/operators.md)
   + Métricas calculadas {#cja-calcmetrics}
      + [Información general sobre las métricas calculadas](components/calc-metrics/calc-metr-overview.md)
      + Flujo de trabajo de las métricas calculadas {#cm-workflow}
         + [Flujo de trabajo de las métricas calculadas](components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Buscar métricas](components/calc-metrics/cm-workflow/cm-finding.md)
         + [Crear métricas](components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Tipo de métrica y atribución](components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Crear una métrica &quot;Vistas de página por visitas&quot; simple](components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Métricas filtradas](components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Apilar y sustituir segmentos](components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Métricas filtradas y ponderadas](components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Uso de funciones](components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Métrica de participación](components/calc-metrics/cm-workflow/participation-metric.md)
         + [Etiquetar métricas calculadas](components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Aprobar métricas calculadas](components/calc-metrics/cm-workflow/cm-approving.md)
         + [Compartir métricas calculadas](components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Administrador de métricas calculadas](components/calc-metrics/cm-workflow/cm-manager.md)
      + [Funciones básicas](components/calc-metrics/cm-functions.md)
      + [Funciones avanzadas](components/calc-metrics/cm-adv-functions.md)
   + Intervalos de fechas {#cja-date-ranges}
      + [Información general sobre los intervalos de fechas](components/date-ranges/overview.md)
      + [Crear un intervalo de fecha](components/date-ranges/create.md)
      + [Administrar intervalos de fechas](components/date-ranges/manage.md)
      + [Información general del calendario](components/date-ranges/calendar.md)
      + [Crear intervalos de fechas](components/date-ranges/custom-date-ranges.md)
      + [Comparación de fechas](components/date-ranges/time-comparison.md)
+ Casos prácticos {#cja-usecases}
   + [Casos de uso de Customer Journey Analytics](use-cases/cja-usecases.md)
   + [Usar matrices de objetos](use-cases/object-arrays.md)
   + [(B2B) Añadir datos de nivel de cuenta como un conjunto de datos de consulta](use-cases/b2b.md)
   + [Analizar datos en varios canales](use-cases/cross-channel.md)
   + [Importación de datos web y de centros de llamadas](use-cases/call-center.md)
   + [Casos de uso sobre ingesta de datos](use-cases/data-ingestion.md)
   + [Uso de dimensiones del canal de marketing](use-cases/marketing-channels.md)
   + [Ingesta de datos de Google Analytics en Adobe Experience Platform](use-cases/ga-to-cja.md)
   + [Informe sobre datos de Google Analytics en CJA](use-cases/ga-to-cja-reporting.md)
+ Paneles de Analytics {#cja-dashboards}
   + [Paneles de Analytics: Información general](mobile-app/home.md)
   + [Tareas del gestor de datos](mobile-app/curator.md)
   + [Creación de un cuadro de resultados](mobile-app/create-scorecard.md)
   + [Configuración de ejecutivos para que utilicen tableros](mobile-app/set-up-execs.md)
   + [Guía de inicio rápida para el usuario ejecutivo](mobile-app/executive.md)
+ Privacidad {#cja-privacy}
   + [Información general de privacidad](privacy/privacy-overview.md)
+ [Actualizaciones de documentación de CJA](doc-changes.md)
