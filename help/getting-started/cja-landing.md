---
title: Guía de Customer Journey Analytics
description: Página de aterrizaje de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: c29b1b8678579b58c42fce2fc02fffd81c1a633f
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 92%

---

# Guía de Customer Journey Analytics

Esta guía de documentación técnica proporciona instrucciones para Customer Journey Analytics. Customer Journey Analytics le permite obtener los datos de clientes desde cualquier canal que elija (tanto en línea como sin conexión) e importarlos en Adobe Experience Platform. A continuación, analice estos datos del mismo modo que lo haría con los datos digitales existentes con Analysis Workspace.

Customer Journey Analytics permite controlar cómo conectar los datos en línea y sin conexión en Analysis Workspace en cualquier ID de cliente común, lo que permite realizar procesos de atribución, filtración, flujo, visitas en orden previsto, etc. en los datos de sus clientes.

## Novedades

Eche un vistazo a las mejoras más recientes del producto y a la documentación de Customer Journey Analytics. Para obtener una lista completa de funciones, mejoras y correcciones, consulte los detalles de las [Notas de la versión](../release-notes/latest.md). Visite la [página de actualizaciones de documentación](../release-notes/doc-changes.md) para mantenerse al día de los cambios más recientes.

>[!BEGINTABS]

>[!TAB Asistente de IA]

El asistente de IA es una experiencia conversacional que permite a los profesionales realizar tareas a un ritmo rápido, ya sea comprender conceptos, solucionar problemas o buscar información. También permite a los no expertos realizar tareas de expertos y aumenta la calidad global del trabajo.

[![imagen](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Análisis guiado]

El análisis guiado ya está disponible directamente desde Analysis Workspace, lo que permite a los usuarios crear paneles con información completa de paneles, visualizaciones y análisis guiados.

[![imagen](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)


>[!TAB Subtítulos inteligentes v2]

Ahora se admiten subtítulos inteligentes, con mejoras adicionales en la interfaz, para las visualizaciones [Línea](/help/analysis-workspace/visualizations/line.md) (incluidas las de varias líneas), [Barra](/help/analysis-workspace/visualizations/bar.md), [Barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md), [Área](/help/analysis-workspace/visualizations/area.md) (incluidas las de varias líneas de área), [Anillo](/help/analysis-workspace/visualizations/donut.md), [Visita en orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) y [Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md).

[![imagen](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB Alertas]

Las alertas permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos. Puede obtener una vista previa de la frecuencia con la que se activará una alerta, se enviará por correo electrónico o SMS, se crearán alertas apiladas y mucho más.

[![imagen](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB Datos de resumen]

Permiten introducir datos de series temporales que no tienen un ID de persona. Estos datos de series temporales se pueden utilizar para admitir varios casos de uso, como

- Presentar indicadores de rendimiento de alto nivel como parte de los datos de nivel de evento o junto a ellos.
- Cargar objetivos o metas por hora o por día y, a continuación, colocarlos en métricas de nivel de evento.

[![imagen](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

>[!TAB Vinculación basada en gráficos]

Con la vinculación basada en gráficos, puede utilizar el gráfico de identidad del Servicio de identidad de Experience Platform para obtener una mejor vista del recorrido del cliente mediante: <ul><li>La unión de conjuntos de datos con diferentes identificadores sin tener que extraer, transformar ni cargar datos adicionales para reflejar un solo identificador.</li> <li>La mejora de la cobertura de la identidad preferida o dorada para un único conjunto de datos compartiendo identidades entre conjuntos de datos.</li><li>La alineación de perfiles creados en Real-Time Customer Data Platform y Journey Optimizer con personas de Customer Journey Analytics.</li></ul>

[![imagen](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_Debe tener el paquete Prime para la vinculación basada en gráficos._*

>[!TAB Búsquedas B2B]

Como parte de la configuración de una conexión, puede transformar conjuntos de datos para esquemas de búsqueda B2B específicos para admitir mejor las búsquedas basadas en personas en datos B2B.

[![imagen](assets/learn-more-button.svg)](/help/connections/transform-datasets-b2b-lookups.md)

>[!TAB Campos derivados]

Ya están disponibles las nuevas funciones de campos derivados (matemáticas, siguiente, anterior, resumir, deduplicar) y plantillas de función adicionales (como devoluciones, nombre de conjunto de datos descriptivo, temporada de vacaciones, objetivos mensuales, detección simple de bots y otras).

[![imagen](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Extensión de BI*]

La extensión de BI habilita el acceso SQL a las vistas de datos que ha definido en Customer Journey Analytics. Ahora puede utilizar su herramienta de BI favorita (Power BI Desktop, Tableau Desktop, Looker, Juyter Notebook y RStudio) para crear informes y paneles basados en las mismas vistas de datos que los usuarios de Customer Journey Analytics utilizan con sus proyectos de Analysis Workspace. Se han proporcionado [casos de uso](/help/use-cases/data-views/bi-extension-usecases.md).

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
      <strong>Comparación con Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Información general</a> - <a href="/help/getting-started/aa-to-cja.md">Evolución</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Utilización de datos de Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Soporte de funcionalidades</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminología</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Procesamiento de datos</a>
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
      <strong>Compartir, exportar, integrar</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Proyectos</a> - <a href="/help/mobile-app/home.md">Paneles de Analytics</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/components/exports/manage-exports.md">Exportación en la nube</a> - <a href="/help/integrations/overview.md">Integraciones</a>
    </td>
  </tr>
</table>

## Recursos adicionales

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/es/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutoriales</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=es" target="_blank">Descripción del producto Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=es" target="_blank">Descripción del producto Adobe Analytics (Complemento de Customer Journey Analytics)</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">API de Customer Journey Analytics</a> - <a href="/help/ai-assistant.md">Asistente de IA</a>
</td>
<td><strong>Ingestión de datos</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Información general</a> - <a href="/help/data-ingestion/analytics.md">Análisis</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK móvil</a> - <a href="/help/data-ingestion/batch.md">Lote</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Fuentes</a> - <a href="/help/data-ingestion/serverapi.md">API de servidor</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Manténgase informado, contribuya a la comunidad y mejore su experiencia con Customer Journey Analytics.</b><br>Visite la comunidad de Adobe Analytics para comentar las funcionalidades con otros profesionales. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=es">¡Únase a la comunidad hoy mismo!</a></td></tr></tbody></table>
