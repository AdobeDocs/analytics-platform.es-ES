---
title: Guía de Customer Journey Analytics
description: Página de destino de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: d8ff5191ea96b8871f6aaba1fc28211c22a13e0d
workflow-type: ht
source-wordcount: '843'
ht-degree: 100%

---

# Guía de Customer Journey Analytics

Esta guía de documentación técnica proporciona instrucciones para Customer Journey Analytics. Customer Journey Analytics le permite obtener los datos de clientes desde cualquier canal que elija (tanto en línea como sin conexión) e importarlos en Adobe Experience Platform. A continuación, analice estos datos del mismo modo que lo haría con los datos digitales existentes con Analysis Workspace.

Customer Journey Analytics le permite controlar cómo conectar los datos en línea y sin conexión en Analysis Workspace en cualquier ID de cliente común, lo que permite realizar procesos de atribución, segmentos, flujos, visitas en orden previsto, etc. en los datos de sus clientes.

## Novedades

Eche un vistazo a las mejoras más recientes del producto y a la documentación de Customer Journey Analytics. Para obtener una lista completa de funciones, mejoras y correcciones, consulte los detalles en las [notas de la versión](../release-notes/latest.md). Visite la [página de actualizaciones de la documentación](../release-notes/doc-changes.md) para mantenerse al día.

>[!BEGINTABS]

>[!TAB Creación de informes en tiempo real*]

La creación de informes en tiempo real en Customer Journey Analytics muestra y actualiza datos y visualizaciones en uno o varios paneles de Analysis Workspace en tiempo real.

[![imagen](assets/learn-more-button.svg)](/help/components/real-time/real-time.md)

*_Debe tener el paquete Ultimate para la creación de informes en tiempo real._*

>[!TAB B2B Edition]

Customer Journey Analytics B2B Edition ayuda a las empresas B2B a alinear sus equipos de marketing, ventas y productos al proporcionar perspectivas de cuenta procesables que impulsan el crecimiento de los ingresos. Con la cuenta en el centro del modelo de datos, todo el análisis se centra en el recorrido de la cuenta.

[![imagen](assets/learn-more-button.svg)](/help/getting-started/cja-b2b-edition.md)

>[!TAB Funciones de campo derivadas]

Nuevas funciones de campo derivadas: [Aritmética de datos](/help/data-views/derived-fields/derived-fields.md#date-math), [Profundidad](/help/data-views/derived-fields/derived-fields.md#depth) y [Conversión de tipos](/help/data-views/derived-fields/derived-fields.md#typecast).

[![imagen](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Análisis de contenido]

Adobe Content Analytics le permite investigar rápida y fácilmente grandes volúmenes de datos de contenido para descubrir tendencias, detectar anomalías, identificar la saturación de contenidos y obtener información de la exposición de contenidos.

[![imagen](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB Profundidad del evento]

La profundidad del evento es una nueva dimensión estándar y proporciona nuevas formas de medir y comprender mejor cómo se colocan los eventos dentro de las sesiones de los clientes. La dimensión Profundidad del evento permite realizar un seguimiento y un análisis detallados de dónde se producen eventos específicos en el flujo secuencial de interacciones del usuario dentro de una sesión.

[![imagen](assets/learn-more-button.svg)](/help/components/dimensions/overview.md#standard-dimensions)


>[!TAB Métricas y dimensiones compartidas]

Las métricas y dimensiones compartidas proporcionan una ubicación central para administrar las dimensiones y métricas que se pueden utilizar en cualquier número de vistas de datos. Estos componentes son especialmente valiosos para las organizaciones que utilizan varias vistas de datos, especialmente si esas vistas de datos comparten la configuración de componentes comunes.

[![imagen](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)


<!--
>[!TAB AI Assistant] 

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace - whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

[![image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guided Analysis] 

Guided Analysis is now available directly from within Analysis Workspace, enabling users to create dashboards with comprehensive insights from panels, visualizations, and guided analyses.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)



>[!TAB Intelligent captions v2] 

Intelligent captions are now supported, with additional interface improvements, for [Line](/help/analysis-workspace/visualizations/line.md) (including multi-line), [Bar](/help/analysis-workspace/visualizations/bar.md), [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md), [Area](/help/analysis-workspace/visualizations/area.md) (including multiple Area lines), [Donut](/help/analysis-workspace/visualizations/donut.md), [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) visualizations.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Alerts] 

Alerts allow you to be notified based on changed percentages or specific data points. You can preview how often an alert will trigger, send alerts by email or SMS, create stacked alerts, and more.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Summary data] 

Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as 

- Presenting high-level performance indicators as part of or next to event-level data. 
- Uploading targets or goals at an hourly or daily basis, then positioning these targets or goals against event-level metrics. 

[![image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

-->

>[!TAB Vinculación basada en gráficos]

Con la vinculación basada en gráficos, puede utilizar el gráfico de identidad del Servicio de identidad de Experience Platform para obtener una mejor vista del recorrido del cliente mediante: <ul><li>La unión de conjuntos de datos con diferentes identificadores sin tener que extraer, transformar ni cargar datos adicionales para reflejar un solo identificador.</li> <li>La mejora de la cobertura de la identidad preferida o dorada para un único conjunto de datos compartiendo identidades entre conjuntos de datos.</li><li>La alineación de perfiles creados en Real-Time Customer Data Platform y Journey Optimizer con personas de Customer Journey Analytics.</li></ul>

[![imagen](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_Debe tener el paquete Prime para la vinculación basada en gráficos._*

>[!TAB Extensión de BI*]

La extensión de BI habilita el acceso SQL a las vistas de datos que ha definido en Customer Journey Analytics. Ahora puede usar su herramienta de BI favorita (Power BI Desktop, Tableau Desktop, Looker, Juyter Notebook y RStudio) para crear informes y tableros basados en las mismas vistas de datos que los usuarios de Customer Journey Analytics utilizan con sus proyectos de Analysis Workspace. Se han proporcionado [casos de uso](/help/use-cases/data-views/bi-extension-usecases.md).

[![imagen](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_Debe tener el paquete Select o superior para utilizar la extensión de BI._*


>[!ENDTABS]

## Empiece con lo básico

Empiece por leer el material de los vínculos siguientes para familiarizarse con las capacidades y funcionalidades de Customer Journey Analytics.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Más allá de los datos en línea</strong><br/>Descubra cómo se compara Customer Journey Analytics con Adobe Analytics, qué funciones se comparten y cómo puede utilizar sus datos de Analytics.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Ingesta y uso de datos</strong><br/>Descubra las opciones que tiene para introducir datos en Experience Platform y utilizarlos para el análisis y la creación de informes en Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Análisis guiado</strong><br/>Aprenda a utilizar los flujos de trabajo para obtener datos e información sobre la experiencia del cliente con el producto. Product Analytics mediante análisis guiado…
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Utilice Analysis Workspace para realizar análisis básico y avanzado, como diagramas de atribución, flujos y visitas en orden previsto, y desgloses de dimensiones.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## Explore la documentación

Comprenda cómo se compara Customer Journey Analytics con Adobe Analytics. Y cómo incluir sus datos en la solución para luego preparar, ver, analizar y democratizar esos datos y los análisis e informes resultantes.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Comparación con Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Información general</a> - <a href="/help/getting-started/aa-to-cja.md">Evolución</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Utilizar datos de Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Soporte de funcionalidades</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminología</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Procesamiento de datos</a> - <a href="/help/getting-started/cja-b2b-edition.md">Customer Journey Analytics B2B Edition</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Conexiones</strong><br/><a href="/help/connections/overview.md">Información general</a> - <a href="/help/connections/create-connection.md">Crear</a> - <a href="/help/connections/manage-connections.md">Administrar</a> - <a href="/help/stitching/overview.md">Unir</a> - <a href="/help/connections/combined-dataset.md">Conjuntos de datos de eventos combinados</a> - <a href="/help/connections/standard-lookups.md">Búsquedas estándar</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>Vistas de datos</strong><br/><a href="/help/data-views/data-views.md">Información general</a> - <a href="/help/data-views/create-dataview.md">Crear o editar</a> - <a href="/help/data-views/session-settings.md">Configuración de sesión</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Campos derivados</a> - <a href="/help/data-views/summary-data.md">Datos de resumen</a> - <a href="/help/data-views/component-reference.md">Referencia de componentes</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Proyectos de Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Análisis básico</a> y <a href="/help/analysis-workspace/perform-adv-analysis.md">avanzado</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Proyectos</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualizaciones</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Paneles</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Análisis guiado</strong><br/><a href="/help/guided-analysis/overview.md">Información general</a> - <a href="/help/guided-analysis/types/active-growth.md">Crecimiento de usuarios</a> - <a href="/help/guided-analysis/types/trends.md">Tendencias</a> - <a href="/help/guided-analysis/types/funnel.md">Canal</a> - <a href="/help/guided-analysis/types/release-impact.md">Impacto</a> - <a href="/help/guided-analysis/industry-use-cases.md">Casos de uso en el sector</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>Compartir, exportar, integrar</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Proyectos</a> - <a href="/help/mobile-app/home.md">Paneles de Analytics</a> - <a href="/help/report-builder/rb-overview.md">Report Builder</a>  - <a href="/help/components/exports/manage-exports.md">Exportación en la nube</a> - <a href="/help/integrations/overview.md">Integraciones</a>
    </td>
  </tr>
</table>

## Recursos adicionales

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/es/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutoriales</a> - <a href="https://helpx.adobe.com/es/legal/product-descriptions/customer-journey-analytics.html?lang=es" target="_blank">Descripción del producto de Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/es/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=es" target="_blank">Descripción del producto de Adobe Analytics (complemento de Customer Journey Analytics)</a> - <a href="https://helpx.adobe.com/es/legal/product-descriptions/customer-journey-analytics-b2b.html" target="_blank">Descripción del producto de Customer Journey Analytics B2B Edition</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">API de Customer Journey Analytics</a> - <a href="/help/ai-assistant.md">Asistente de IA</a>
</td>
<td><strong>Ingesta de datos</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Información general</a> - <a href="/help/data-ingestion/analytics.md">Análisis</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK móvil</a> - <a href="/help/data-ingestion/batch.md">Lote</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Fuentes</a> - <a href="/help/data-ingestion/serverapi.md">API de servidor</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Manténgase informado, contribuya a la comunidad y mejore su experiencia con Customer Journey Analytics.</b><br>Visite la comunidad de Adobe Analytics para comentar las funcionalidades con otros profesionales. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=es">¡Únase a la comunidad hoy mismo!</a></td></tr></tbody></table>
