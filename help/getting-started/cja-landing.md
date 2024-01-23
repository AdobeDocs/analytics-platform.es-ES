---
title: Guía de Customer Journey Analytics
description: Página de aterrizaje de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 79234ee442e49ebf7f5a08bd0214e8c9d547485e
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 21%

---

# Guía de Customer Journey Analytics

Esta guía de documentación técnica proporciona instrucciones para Customer Journey Analytics. Customer Journey Analytics le permite obtener los datos de clientes desde cualquier canal que elija (tanto en línea como sin conexión) e importarlos en Adobe Experience Platform y, a continuación, analizarlos del mismo modo que lo haría con los datos digitales actuales con Analysis Workspace.

Customer Journey Analytics permite controlar cómo conectar los datos en línea y sin conexión en Analysis Workspace en cualquier ID de cliente común, lo que permite realizar procesos de atribución, filtración, flujo, visitas en orden previsto, etc. en los datos de sus clientes.

## Novedades

Eche un vistazo a las mejoras más recientes en el producto y la documentación de Customer Journey Analytics. Para obtener una lista completa de funciones, mejoras y correcciones, consulte los detalles de las [Notas de la versión](../release-notes/latest.md). Manténgase al tanto de los cambios más recientes en nuestra documentación. Para ello, visite la [página de actualizaciones de la documentación](../release-notes/doc-changes.md).

>[!BEGINTABS]

>[!TAB Análisis guiado*: tasas de retención]

Un nuevo tipo de vista que muestra el porcentaje de usuarios que regresan después de su participación inicial dentro del intervalo de fechas deseado. El eje horizontal representa el número de días desde la participación inicial de un usuario. El eje vertical representa el porcentaje de usuarios que vuelven a interactuar.

[![image](assets/learn-more-button.svg)](/help//guided-analysis/types/retention-rates.md)

<span style="color:gray">*_El análisis guiado forma parte de Adobe Product Analytics, que es un complemento de pago para Customer Journey Analytics._</span>




>[!TAB Análisis guiado*: líneas de tendencia]

Las superposiciones de líneas de tendencia ahora están disponibles en la vista Uso, lo que ayuda a mostrar un patrón más claro en los datos. Los tipos de líneas de tendencia disponibles son lineales, logarítmicas y de promedio móvil.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_El análisis guiado forma parte de Adobe Product Analytics, que es un complemento de pago para Customer Journey Analytics._</span>


>[!TAB Visualización Resumen de métricas clave]

Al utilizar la visualización Resumen de métricas clave, el intervalo de fechas de comparación ahora se puede actualizar automáticamente, en función de si la opción Intervalo de fechas de comparación que elija es relativa al intervalo de fechas principal o fija.

[![image](assets/learn-more-button.svg)](/help/analysis-workspace/visualizations/key-metric.md)

>[!ENDTABS]

## Empiece con lo básico

Comience por leer el material de los vínculos siguientes para familiarizarse con las capacidades y funcionalidades de los Customer Journey Analytics.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Más allá de los datos en línea</strong><br/>Descubra cómo se compara Customer Journey Analytics con Adobe Analytics, qué funciones se comparten y cómo puede utilizar los datos de Analytics.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Ingesta y uso de datos</strong><br/>Obtenga información sobre las opciones que tiene para introducir datos en Experience Platform y utilizarlos para análisis e informes en Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Análisis guiado</strong><br/>Aprenda a utilizar flujos de trabajo para obtener datos y perspectivas sobre la experiencia del cliente con el producto. Product Analytics mediante análisis guiado...
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Utilice Analysis Workspace para realizar análisis básicos y avanzados, como diagramas de atribución, flujo y visitas en el orden previsto, desgloses de dimensión.</div>
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

Comprenda cómo Customer Journey Analytics se compara con Adobe Analytics y cómo obtener los datos en la solución y luego preparar, ver, analizar y democratizar esos datos y los análisis e informes resultantes.

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Comparar con Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Información general</a> - <a href="/help/getting-started/aa-to-cja.md">Evolución</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Uso de datos de Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Compatibilidad de funciones</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminología</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Procesamiento de datos</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Conexiones</strong><br/><a href="/help/connections/overview.md">Información general</a> - <a href="/help/connections/create-connection.md">Crear</a> - <a href="/help/connections/manage-connections.md">Administrar</a> - <a href="/help/stitching/overview.md">Puntada</a> - <a href="/help/connections/combined-dataset.md">Conjuntos de datos de evento combinados</a> - <a href="/help/connections/standard-lookups.md">Búsquedas estándar</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>Vistas de datos</strong><br/><a href="/help/data-views/data-views.md">Información general</a> - <a href="/help/data-views/create-dataview.md">Crear o editar</a> - <a href="/help/data-views/session-settings.md">Configuración de sesión</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Campos derivados</a> - <a href="/help/data-views/component-reference.md">Referencia del componente</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Proyectos de Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Básico </a> &amp; <a href="/help/analysis-workspace/perform-adv-analysis.md">Análisis avanzado</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Proyectos</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualizaciones</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Paneles</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Análisis guiado</strong><br/><a href="/help/guided-analysis/overview.md">Información general</a> - <a href="/help/guided-analysis/types/active.md">Crecimiento de usuarios</a> - <a href="/help/guided-analysis/types/usage.md">Tendencias</a> - <a href="/help/guided-analysis/types/friction.md">Canal</a> - <a href="/help/guided-analysis/types/release.md">Impacto</a> - <a href="/help/guided-analysis/industry-use-cases.md">Casos de uso del sector</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>Compartir, exportar e integrar</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Proyectos</a> - <a href="/help/mobile-app/home.md">Paneles de Analytics</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/integrations/overview.md">Integraciones</a>
    </td>
  </tr>
</table>

## Recursos adicionales

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/overview.html" target="_blank">Tutorials</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Descripción del producto del Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Descripción del producto de Adobe Analytics (complemento de Customer Journey Analytics)</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">API de Customer Journey Analytics</a>
</td>
<td><strong>Ingesta de datos</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Información general</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">Lote</a> - <a href="/help/data-ingestion/streaming.md">Transmisión</a> - <a href="/help/data-ingestion/sources.md">Fuentes</a> - <a href="/help/data-ingestion/serverapi.md">API de servidor</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Manténgase informado, contribuya a la comunidad y mejore su experiencia como Customer Journey Analytics.</b><br>Visite la comunidad de Adobe Analytics para hablar sobre la funcionalidad con otros profesionales. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=es">¡Únase a la comunidad hoy mismo!</a></td></tr></tbody></table>
