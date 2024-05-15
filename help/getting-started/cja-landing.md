---
title: Guía de Customer Journey Analytics
description: Página de aterrizaje de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 6b5a9050d6c13e3c9d637a3ed992840a46058cee
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 59%

---

# Guía de Customer Journey Analytics

Esta guía de documentación técnica proporciona instrucciones para Customer Journey Analytics. Customer Journey Analytics le permite obtener los datos de clientes desde cualquier canal que elija (tanto en línea como sin conexión) e importarlos en Adobe Experience Platform. A continuación, analice estos datos del mismo modo que lo haría con los datos digitales actuales con Analysis Workspace.

Customer Journey Analytics permite controlar cómo conectar los datos en línea y sin conexión en Analysis Workspace en cualquier ID de cliente común, lo que permite realizar procesos de atribución, filtrado, flujo, visitas en orden previsto, etc. en los datos de sus clientes.

## Novedades

Eche un vistazo a las mejoras más recientes del producto y a la documentación de Customer Journey Analytics. Para obtener una lista completa de funciones, mejoras y correcciones, consulte los detalles de las [Notas de la versión](../release-notes/latest.md). Visite la [página actualizaciones de documentación](../release-notes/doc-changes.md) para mantenerse al día con los cambios más recientes.

>[!BEGINTABS]

>[!TAB Extensión de BI*]

La extensión de BI habilita el acceso SQL a las vistas de datos definidas en Customer Journey Analytics. Ahora puede usar su herramienta de BI favorita para crear informes y paneles basados en las mismas vistas de datos que los usuarios de Customer Journey Analytics usan con sus proyectos de Analysis Workspace.

[![image](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

<span style="color:gray">*_Debe tener el paquete Select o superior para utilizar la extensión BI._</span>


<!--
>[!TAB Improved Audience Publising] 

Audiences that are published from Customer Journey Analytics are now available in the new **Audiences** section in Adobe Experience Platform. Audiences are now available in Experience Platform seconds after they are published from Customer Journey Analytics. Improved sorting and filter options in Experience Platform for Customer Journey Analytics audiences. 

[![image](assets/learn-more-button.svg)](/help/components/audiences/publish.md)

-->


>[!TAB Nueva documentación]

La nueva documentación ya está disponible en:<ul><li>Cómo actualizar de Adobe Analytics a Customer Journey Analytics.</li><li>Casos de uso de exportación de datos y las funcionalidades de Experience Platform y Recorrido del cliente requeridas. </li></ul>Seleccionar **[!UICONTROL Más información]** para esta y otras actualizaciones de la documentación.

[![image](assets/learn-more-button.svg)](/help/release-notes/doc-changes.md)

>[!TAB Previsión]

La previsión es una función de Analysis Workspace que permite prever una métrica estándar o calculada con cualquier granularidad de tiempo admitida (por hora, diario, semanal, mensual y anual). La previsión solo está disponible para datos relacionados con series temporales.

[![image](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)

>[!TAB Análisis guiado* - Tasas de retención]

Un nuevo tipo de vista que muestra el porcentaje de usuarios que regresan después de su participación inicial dentro del intervalo de fechas deseado. El eje horizontal representa el número de días transcurridos desde la participación inicial de un usuario. El eje vertical representa el porcentaje de usuarios que vuelven a participar.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/types/retention-rates.md)

<span style="color:gray">*_El análisis guiado forma parte de Adobe Product Analytics, un complemento de pago de Customer Journey Analytics._</span>


>[!TAB Análisis guiado* - Líneas de tendencia]

Las superposiciones de líneas de tendencia están ahora disponibles en la vista Uso, que ayuda a mostrar un patrón más claro en los datos. Los tipos de líneas de tendencia disponibles son lineal, logarítmica y promedio móvil.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_El análisis guiado forma parte de Adobe Product Analytics, un complemento de pago de Customer Journey Analytics._</span>

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
    <div><strong>Ingesta y uso de datos</strong><br/>Obtenga información sobre las opciones que tiene para introducir datos en Experience Platform y utilizarlos para análisis e informes en Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Análisis guiado</strong><br/>Aprenda a utilizar los flujos de trabajo para obtener datos e información sobre la experiencia del cliente con el producto. Product Analytics mediante análisis guiado...
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

Comprender cómo se compara Customer Journey Analytics con Adobe Analytics. Y cómo incluir sus datos en la solución y luego preparar, ver, analizar y democratizar esos datos y el análisis e informes resultantes.

<table style="table-layout:auto">
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
      <strong>Vistas de datos</strong><br/><a href="/help/data-views/data-views.md">Información general</a> - <a href="/help/data-views/create-dataview.md">Crear o editar</a> - <a href="/help/data-views/session-settings.md">Configuración de sesión</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Campos derivados</a> - <a href="/help/data-views/component-reference.md">Referencia del componente</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Proyectos de Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Básico</a> &amp; <a href="/help/analysis-workspace/perform-adv-analysis.md">Análisis avanzado</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Proyectos</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualizaciones</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Paneles</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Análisis guiado</strong><br/><a href="/help/guided-analysis/overview.md">Información general</a> - <a href="/help/guided-analysis/types/active.md">Crecimiento de usuarios</a> - <a href="/help/guided-analysis/types/usage.md">Tendencias</a> - <a href="/help/guided-analysis/types/friction.md">Canal</a> - <a href="/help/guided-analysis/types/release.md">Impacto</a> - <a href="/help/guided-analysis/industry-use-cases.md">Casos de uso en el sector</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>Compartir, exportar, integrar</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Proyectos</a> - <a href="/help/mobile-app/home.md">Paneles de Analytics</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a> - <a href="/help/integrations/overview.md">Integraciones</a>
    </td>
  </tr>
</table>

## Recursos adicionales

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutoriales</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=es" target="_blank">Descripción del producto Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=es" target="_blank">Descripción del producto Adobe Analytics (complemento de Customer Journey Analytics)</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">API de Customer Journey Analytics</a>
</td>
<td><strong>Ingestión de datos</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Información general</a> - <a href="/help/data-ingestion/analytics.md">Análisis</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK móvil</a> - <a href="/help/data-ingestion/batch.md">Lote</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Fuentes</a> - <a href="/help/data-ingestion/serverapi.md">API de servidor</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Manténgase informado, contribuya a la comunidad y mejore su experiencia con Customer Journey Analytics.</b><br>Visite la comunidad de Adobe Analytics para analizar la funcionalidad con otros profesionales. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=es">¡Únase a la comunidad hoy mismo!</a></td></tr></tbody></table>
