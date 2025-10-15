---
title: Comparación de datos del conector fuente de Analytics con Adobe Analytics
description: Conozca las diferencias en los datos cuando visualice informes similares en Adobe Analytics y Customer Journey Analytics.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: servicio de consultas;Servicio de consultas;sintaxis sql
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 100%

---

# Comparación de datos del conector fuente de Analytics con Adobe Analytics

A medida que su organización adopta Customer Journey Analytics, es posible que observe algunas diferencias en los datos entre Adobe Analytics y Customer Journey Analytics. Estas diferencias son normales y pueden ocurrir por varias razones. Customer Journey Analytics se ha diseñado para que pueda mejorar algunas de las limitaciones de sus datos en Adobe Analytics. Esta flexibilidad puede causar algunas diferencias en la forma en que Customer Journey Analytics interpreta los datos. Utilice este artículo para conocer las posibles diferencias en el modo en que Customer Journey Analytics y Adobe Analytics tratan los datos.

En esta página se da por hecho que se han introducido datos de Adobe Analytics en Adobe Experience Platform mediante el [conector fuente de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es), y después se ha creado una [conexión](/help/connections/overview.md) y [vista de datos](/help/data-views/data-views.md) en Customer Journey Analytics.

![El flujo de datos de Adobe Analytics a través del conector de datos a Adobe Experience Platform y a Customer Journey Analytics mediante conexiones de CJA.](assets/compare.png)

Tenga en cuenta las siguientes posibles razones por las que los datos pueden diferir entre las plataformas de creación de informes:

* **Conjuntos de datos o grupos de informes diferentes**: asegúrese de que el grupo de informes de Adobe Analytics y el grupo de informes del cual obtiene los datos el conector fuente sean los mismos.
* **Configuración del calendario**: los grupos de informes de Adobe Analytics contienen una zona horaria y otros ajustes de calendario que puede configurar. Del mismo modo, las vistas de datos de Customer Journey Analytics tienen una configuración independiente que puede controlar. Asegúrese de que esta configuración coincida entre los productos si desea que haya paridad.
* **Conjuntos de datos adicionales**: Customer Journey Analytics ofrece la posibilidad de incluir varios conjuntos de datos en una sola conexión. Estas diferencias incluyen conjuntos de datos de evento, de perfil o de búsqueda adicionales. Esta posibilidad es un diferenciador clave entre Adobe Analytics y Customer Journey Analytics, lo que permite obtener información sobre los datos de canales múltiples.
* **Conjuntos de datos vinculados**: Adobe proporciona la posibilidad de analizar los ID de persona entre dos conjuntos de datos, lo que se traduce en un nuevo conjunto de datos que contiene los ID vinculados. Estos [conjuntos de datos vinculados](/help/stitching/overview.md) contienen datos adicionales además de los que ofrece un grupo de informes de Adobe Analytics.
* **Fuentes de datos**: Customer Journey Analytics no incluye ningún tipo de [Fuentes de datos](https://experienceleague.adobe.com/es/docs/analytics/import/data-sources/overview) cargadas en un grupo de informes de Adobe Analytics, incluidas las fuentes de datos de resumen o las fuentes de datos del ID de transacción.
* **Configuración de dimensión y métrica**: dentro de una vista de datos, cada dimensión y métrica contiene su propia configuración que su organización puede modificar. Estos cambios se aplican en el momento de ejecutar el informe y, por lo tanto, se aplican de forma retroactiva. La configuración de la dimensión y la métrica en Adobe Analytics cambia la forma en que se recopilan los datos, lo que hace que esos cambios se apliquen a partir de ese momento. Si ha cambiado la configuración de los componentes en cualquiera de los productos, pueden crear diferencias en la creación de informes. Si se centra en una dimensión específica, asegúrese de que la configuración de atribución y persistencia coincida entre Adobe Analytics y Customer Journey Analytics.

  >[!TIP]
  >
  >Adobe recomienda muy especialmente que las dimensiones de Adobe Analytics utilicen una asignación de “[!UICONTROL Más reciente (último)]”. Esta configuración de asignación permite una mayor flexibilidad de atribución en Customer Journey Analytics.

* **Definición de visita**: además de la configuración de dimensiones y métricas individuales, la propia vista de datos contiene configuraciones que cambian fundamentalmente la manera en que se interpretan los datos de los visitantes. Por ejemplo, puede aplicar un segmento a toda una vista de datos (similar a un [grupo de informes virtuales](https://experienceleague.adobe.com/es/docs/analytics/components/virtual-report-suites/vrs-about) en Adobe Analytics). También puede cambiar la definición de una duración de visita o iniciar automáticamente una nueva visita en cualquier evento deseado. Cualquiera de estas configuraciones puede tener un impacto notable en las diferencias de creación de informes entre Customer Journey Analytics y Adobe Analytics.

## Comprobación del recuento de registros entre productos

Si todos los ajustes anteriores parecen similares y desea validar al menos el número de registros entre productos, puede seguir estos pasos:

1. En los [Servicios de consulta](https://experienceleague.adobe.com/es/docs/experience-platform/query/home) de Adobe Experience Platform, ejecute la siguiente consulta Registros totales por marcas de tiempo:

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. En [Fuentes de datos](https://experienceleague.adobe.com/es/docs/analytics/export/analytics-data-feed/data-feed-overview) de Adobe Analytics, genere archivos de fuentes para el intervalo de fechas deseado. Cuente el número de filas dentro de cada archivo, identificando y excluyendo las siguientes filas:

   * `exclude_hit` no es `0` (datos excluidos de Analysis Workspace en ambos productos)
   * `hit_source` es `0`, `3`, `5`, `7`, `8`, `9` o `10` (fuentes de datos y otros datos que no son de visitas)
   * `page_event` es `53` o `63` (visitas persistentes de medios de streaming)

   Las filas que coincidan con cualquiera de los criterios anteriores se excluirán del flujo de trabajo de ingesta del conector fuente de Analytics y, por lo tanto, también deben excluirse cuando se cuenten las filas de fuentes de datos.

1. El total de registros de los servicios de consulta debe coincidir con el número de filas de una fuente de datos durante el mismo período de tiempo.
