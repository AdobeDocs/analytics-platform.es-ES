---
title: Comparación de los datos de Adobe Analytics con los de Customer Journey Analytics
description: Obtenga información sobre cómo comparar sus datos de Adobe Analytics con los de Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 65%

---

# Comparación de los datos de Adobe Analytics con los de Customer Journey Analytics

A medida que su organización adopta Customer Journey Analytics, es posible que observe algunas diferencias en los datos entre Adobe Analytics y Customer Journey Analytics. Esto es normal y puede ocurrir por varios motivos. Customer Journey Analytics está diseñado para permitirle mejorar algunas de las limitaciones de sus datos en AA. Sin embargo, pueden producirse discrepancias inesperadas/no deseadas. Este artículo está diseñado para ayudarle a diagnosticar y solucionar esas diferencias, de modo que usted y su equipo puedan utilizar Customer Journey Analytics sin impedimentos por motivos de integridad de los datos.

Supongamos que ha ingerido datos de Adobe Analytics en Adobe Experience Platform a través de [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es)y, a continuación, creó una conexión de Customer Journey Analytics con este conjunto de datos.

![Flujo de datos](assets/compare.png)

A continuación, creó una vista de datos y, mientras informaba posteriormente de estos datos en Customer Journey Analytics, observó discrepancias con los resultados de los informes en Adobe Analytics.

A continuación, se indican algunos pasos a seguir para comparar los datos originales de Adobe Analytics con los datos de Adobe Analytics que ahora están en Customer Journey Analytics.

## Requisitos previos

* Asegúrese de que el conjunto de datos de Analytics en Adobe Experience Platform contenga datos para el intervalo de fechas que está investigando.

* Asegúrese de que el grupo de informes seleccionado en Analytics coincida con el grupo de informes ingerido en Adobe Experience Platform.

## Paso 1: Ejecute la métrica Ocurrencias en Adobe Analytics

La métrica [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=es) muestra el número de visitas configurado o en las que persiste una dimensión.

1. En Analytics > [!UICONTROL Workspace], arrastre el intervalo de fechas sobre el que desee crear el informe como dimensión a una tabla de [!UICONTROL Forma libre].

1. La variable [!UICONTROL Ocurrencias] se aplica automáticamente a ese intervalo de fechas.

1. Guarde este proyecto para que pueda utilizarlo en la comparación.

## Paso 2: Comparar los resultados con [!UICONTROL Registros totales por marcas de tiempo] en Customer Journey Analytics

Ahora compare la [!UICONTROL Ocurrencias] en Analytics para el total de registros por marcas de tiempo en Customer Journey Analytics.

Los registros totales por marcas de tiempo deben coincidir con Ocurrencias, siempre que el conector de origen de Analytics no haya caído ningún registro; consulte la sección siguiente.

>[!NOTE]
>
>Esto solo funciona para conjuntos de datos de valores medios normales, no para conjuntos de datos (a través de [Análisis en canales múltiples](/help/cca/overview.md)). Tenga en cuenta que la contabilidad del ID de persona que se utiliza en el Customer Journey Analytics es crítica para hacer que la comparación funcione. Puede que no siempre sea fácil replicarlo en Adobe Analytics, especialmente si se ha activado Cross-Channel Analytics.

1. En Adobe Experience Platform [Servicios de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=es), ejecute la siguiente consulta [!UICONTROL Registros totales por marcas de tiempo]:

       &quot;
       SELECT Subcadena(from_utc_timestamp(timestamp,&#39;{timeZone}&#39;), 1, 10) como día, \
       Count(_id) AS Registros
       DESDE  {dataset} \
       WHERE timestamp>=from_utc_timestamp(&#39;{fromDate}&#39;,&#39;UTC&#39;) \
       Y marca de tiempo&lt;from_utc_timestamp span=&quot;&quot; id=&quot;14&quot; translate=&quot;no&quot; />&#39;,&#39;UTC&#39;) \
       Y LA MARCA DE TIEMPO NO ES NULA \
       Y enduserids.{toDate}_experience.aaid.id IS NOT NULL \
       AGRUPAR POR DÍA \
       ORDENAR POR día;
       
       &quot;
   
1. En [Fuentes de datos de Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es), identifique, a partir de los datos sin procesar, si el conector de origen de Analytics puede haber filtrado algunas filas.

   El [conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) podría filtrar determinadas filas durante la transformación al esquema XDM. Puede haber varias razones para que toda la fila no sea apta para la transformación. Si alguno de los campos de Analytics siguientes tiene estos valores, se filtrará toda la fila.

   | Campo de Analytics | Valores que hacen que se borre una fila |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | No 0 |
   | Exclude_hit | No 0 |
   | Bot_id | No 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   Para obtener más información acerca de hit\_source, consulte [Referencia de columnas de datos](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es). Para obtener más información acerca de page\_event, consulte [Búsqueda de eventos de página](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=es).

1. Si el conector filtra filas, reste esas filas de la métrica [!UICONTROL Ocurrencias]. El número resultante debe coincidir con el número de eventos de los conjuntos de datos de Adobe Experience Platform.

## Por qué se pueden filtrar o omitir registros durante la ingesta desde Adobe Experience Platform

Customer Journey Analytics [Conexiones](/help/connections/create-connection.md) le permite unir varios conjuntos de datos en función de un ID de persona común en todos los conjuntos de datos. En el servidor, se aplica la anulación de duplicación: unión externa completa o unión en conjuntos de datos de evento basados en marcas de tiempo y, a continuación, unión interna en el perfil y el conjunto de datos de búsqueda, según el ID de persona.

A continuación se indican algunas de las razones por las que se pueden omitir registros al ingerir datos de Adobe Experience Platform.

* **Marcas de tiempo que faltan**: si faltan marcas de tiempo en los conjuntos de datos de evento, esos registros se ignorarán u omitirán por completo durante la ingesta.

* **ID de persona que faltan**: los ID de persona que faltan (del conjunto de datos de eventos y/o del perfil o conjunto de datos de búsqueda) hacen que esos registros se ignoren o se omitan. El motivo es que no hay ID comunes ni claves coincidentes para unirse a los registros.

* **ID de persona grande o no válida**: con ID no válidos, el sistema no puede encontrar un ID común válido entre los conjuntos de datos para unirse. En algunos casos, la columna ID de persona tiene ID de persona no válidos, como “indefinido” o “00000000”. Un ID de persona (con cualquier combinación de números y letras) que aparezca en un evento más de 1 millón de veces al mes no se puede atribuir a ningún usuario o persona en particular. Se clasificará como no válido. Estos registros no se pueden ingerir en el sistema, y conlleva a la creación de informes e ingestas propensas a errores.
