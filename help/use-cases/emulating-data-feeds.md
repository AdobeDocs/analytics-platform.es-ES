---
title: Funcionalidad de emular fuente de datos
description: Descubra cómo puede emular las fuentes de datos de Adobe Analytics con los datos de Experience Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: b41adb3f3fa4abbfa7be491e5a1fbf81e1623598
workflow-type: tm+mt
source-wordcount: '2556'
ht-degree: 4%

---

# Funcionalidad de emular fuente de datos

Las fuentes de datos de Adobe Analytics son una forma eficaz de obtener datos sin procesar de Adobe Analytics. En este caso de uso se describe cómo obtener un tipo similar de datos sin procesar de Experience Platform, para que pueda utilizar los datos en otras plataformas y herramientas fuera del Adobe y según convenga a su organización.

## Primeros pasos

La emulación de una fuente de datos de Adobe Analytics implica:

* definición de un **consulta programada** que genera los datos para la fuente de datos como un conjunto de datos de salida ![conjunto de datos de salida](assets/output-dataset.svg), usando **Servicio de consultas**.
* definición de un **exportación programada del conjunto de datos** que exporta el conjunto de datos de salida a un destino de almacenamiento en la nube mediante **Exportación de conjuntos de datos**.

![Fuente de datos](assets/data-feed.svg)


## Requisitos previos

Asegúrese de cumplir todos los requisitos antes de utilizar la funcionalidad descrita en este caso de uso:

* Implementación de trabajo que recopila datos en el lago de datos de Experience Platform.
* Acceda al complemento Data Distiller para asegurarse de que tiene derecho a ejecutar consultas por lotes. Consulte [Empaquetado del servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) para obtener más información.
* Acceso a la funcionalidad Exportar conjuntos de datos, disponible al adquirir el paquete Real-Time CDP Prime o Ultimate, Adobe Journey Optimizer o Customer Journey Analytics. Consulte [Exportar conjuntos de datos a destinos de almacenamiento en la nube](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=es) para obtener más información.
* Uno o más destinos (por ejemplo: Amazon S3, Google Cloud Storage) configurados para que pueda exportar los datos sin procesar de su fuente de datos.


## Servicio de consultas

El servicio de consultas de Experience Platform le permite consultar y unir cualquier conjunto de datos en el lago de datos de Experience Platform como si fuera una tabla de base de datos. A continuación, puede capturar los resultados como un nuevo conjunto de datos para su uso posterior en la creación de informes o para su exportación.

Utilice el servicio de consultas [interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [cliente conectado a través del protocolo PostgresQL](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=es), o [API de RESTful](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) para crear y programar consultas que recopilen los datos de la fuente de datos.

### Crear consulta

Puede utilizar todas las funciones de ANSI SQL estándar para instrucciones SELECT y otros comandos limitados para crear y ejecutar consultas que generen los datos para la fuente de datos. Consulte [Sintaxis SQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) para obtener más información. Más allá de esta sintaxis SQL, Adobe admite:

* precompilado [Funciones definidas por el Adobe (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) que ayudan a realizar tareas comunes relacionadas con la empresa en los datos de evento almacenados en el lago de datos de Experience Platform, incluidas funciones para [Sessionization](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=es) y [Atribución](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=es),
* varios integrados [Funciones SQL de Spark](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [comandos PostgreSQL de metadatos](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [declaraciones preparadas](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Identidades

En Experience Platform, hay varias identidades disponibles. Al crear las consultas, asegúrese de que está consultando las identidades correctamente.

A menudo, las identidades se encuentran en un grupo de campos independiente. En un ECID de implementación (`ecid`) se puede definir como parte de un grupo de campos con un `core` que forma parte de un objeto `identification` objeto. (por ejemplo: `_sampleorg.identification.core.ecid`). Los ECID pueden estar organizados de forma diferente en los esquemas.

Como alternativa, puede utilizar `identityMap` para consultar identidades. Este objeto es de tipo `Map` y usa un [estructura de datos anidada](#nested-data-structure).


#### Columnas de fuente de datos

Los campos XDM que puede utilizar en la consulta dependen de la definición de esquema en la que se basen los conjuntos de datos. Asegúrese de comprender el esquema subyacente del conjunto de datos.

Para facilitar la asignación entre las columnas de fuente de datos y los campos XDM, se debe tener en cuenta incluir los campos [Plantilla de Adobe Analytics ExperienceEvent](https://github.com/adobe/xdm/blob/master/extensions/adobe/experience/analytics/experienceevent-all.schema.json) grupo de campos en el esquema de evento de experiencia. Consulte [Prácticas recomendadas para el modelado de datos](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en) y más específicamente [grupos de campos de esquema de aplicación de Adobe](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en#adobe-application-schema-field-groups).

Por ejemplo, en caso de que desee utilizar *nombre de página* como parte de la fuente de datos:

* En la interfaz de usuario de la fuente de datos de Adobe Analytics, debe seleccionar **[!UICONTROL pagename]** como la columna que se agregará a la definición de fuente de datos.
* En el servicio de consultas, incluye lo siguiente `web.webPageDetails.name` desde el `sample_event_dataset_for_website_global_v1_1` conjunto de datos (basado en el **Esquema de evento de muestra para el sitio web (Global v1.1)** experience event (esquema) en la consulta. Consulte la [grupo de campos de esquema de detalles web](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) para obtener más información.

Para comprender la asignación entre columnas de fuentes de datos de Adobe Analytics anteriores y campos XDM en el conjunto de datos de evento de experiencia y el esquema subyacente, consulte [Asignación de campos de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=es) y el [Grupo de campos de esquema de extensión completa de Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) para obtener más información.

Además, la [información recopilada automáticamente por el SDK web de Experience Platform (de forma predeterminada)](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) puede ser relevante para identificar columnas para la consulta.

#### Identificación y datos de nivel de visita individual

En función de la implementación, los datos de nivel de visita recopilados tradicionalmente en Adobe Analytics ahora se almacenan como datos de evento con marca de tiempo en Experience Platform. La siguiente tabla se extrae de [Asignación de campos de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en#generated-mapping-fields) y muestra ejemplos de cómo asignar columnas de fuentes de datos de Adobe Analytics específicas del nivel de visita con los campos XDM correspondientes en las consultas. La tabla también muestra ejemplos de cómo se identifican las visitas, las visitas y los visitantes mediante campos XDM.

| Columna de fuente de datos | Campo XDM | Tipo | Descripción |
|---|---|---|---|
| hitid_high + hitid_low | _id | string | Un identificador único para identificar una visita. |
| hitid_low | _id | string | Se utiliza junto con hitid_high para identificar una visita de forma exclusiva. |
| hitid_high | _id | string | Se utiliza junto con hitid_high para identificar una visita de forma exclusiva. |
| hit_time_gmt | receivedTimestamp | string | La marca de tiempo de la visita basada en la hora Unix. |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | string | Marca de tiempo de la primera visita del visitante en Tiempo Unix. |
| cust_hit_time_gmt | timestamp | string | Esto solo se utiliza en conjuntos de datos con marca de tiempo habilitada. Esta es la marca de tiempo que se envía con la misma, en función de la hora Unix. |
| visid_high + visid_low | identityMap | objeto | Un identificador único de una visita. |
| visid_high + visid_low | endUserID._experience.aaid.id | string | Un identificador único de una visita. |
| visid_high | endUserID._experience.aaid.primary | booleano | Se utiliza junto con visid_low para identificar una visita de forma exclusiva. |
| visid_high | endUserID._experience.aaid.namespace.code | string | Se utiliza junto con visid_low para identificar una visita de forma exclusiva. |
| visid_low | identityMap | objeto | Se utiliza junto con visid_high para identificar una visita de forma exclusiva. |
| cust_visid | identityMap | objeto | El ID de visitante del cliente |
| cust_visid | endUserID._experience.aacustomid.id | objeto | El ID de visitante de cliente. |
| cust_visid | endUserID._experience.aacustomid.primary | booleano | El código del área de nombres de ID de visitante de cliente. |
| cust_visid | endUserID._experience.aacustomid.namespace.code | string | Se utiliza junto con visid_low para identificar de forma exclusiva el ID de visitante de cliente. |
| geo\_* | placeContext.geo.* | cadena, número | Datos de geolocalización, como país, región, ciudad y otros |
| visit_page_num | _experience.analytics.session.depth | number | Variable utilizada en la dimensión Profundidad de visita. Este valor aumenta en 1 por cada visita que genera el usuario y se restablece después de cada visita. |
| event_list | commerce.purchases, commerce.productViews, commerce.productListOpens, commerce.checkouts, commerce.productListAdds, commerce.productListRemovals, commerce.productListViews, \_experience.analytics.event101to200.*, ..., \_experience.analytics.event901_1000.\* | string | Eventos comerciales y personalizados estándar activados en la visita. |
| page_event | web.webInteraction.type | string | El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo de salida o vínculo personalizado en el que se hace clic). |
| page_event | web.webInteraction.linkClicks.value | number | El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo de salida o vínculo personalizado en el que se hace clic). |
| page_event_var_1 | web.webInteraction.URL | string | Variable que solo se utiliza en las solicitudes de imagen de seguimiento de vínculos. Esta variable contiene la dirección URL del vínculo de descarga, de salida o personalizado en el que se hizo clic. |
| page_event_var_2 | web.webInteraction.name | string | Variable que solo se utiliza en las solicitudes de imagen de seguimiento de vínculos. Muestra el nombre personalizado del vínculo, si se especifica. |
| first_hit_ref_type | _experience.analytics.endUser.firstWeb.webReferrer.type | string | El ID numérico, que representa el tipo de referente del primer referente del visitante. |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | entero | Marca de tiempo de la primera visita del visitante en Tiempo Unix. |
| paid_search | search.isPaid | booleano | Un indicador que se establece si la visita coincide con la detección de búsquedas de pago. |
| ref_type | web.webReferrertype | string | Una ID numérica que representa el tipo de referente de la visita. |

#### Publicar columnas

Las fuentes de datos de Adobe Analytics utilizan el concepto de columnas con una `post_` prefijo, que son columnas que contienen datos después del procesamiento. Consulte [Preguntas frecuentes sobre fuentes de datos](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html?lang=en#post) para obtener más información.

Los datos recopilados en conjuntos de datos a través de la red perimetral de Experience Platform (SDK web, SDK móvil, API de servidor) no tienen concepto de `post_` campos, lo que explica por qué `post_` con el prefijo y *non* `post_` las columnas de fuentes de datos prefijadas en la asignación de campos de Analytics se asignan a los mismos campos XDM. Por ejemplo, ambas `page_url` y `post_page_url` las columnas de fuentes de datos se asignan al mismo `web.webPageDetails.URL` Campo XDM.

Consulte [Comparar el procesamiento de datos entre Adobe Analytics y Customer Journey Analytics.](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=es) para obtener una descripción general de las diferencias en el procesamiento de datos.

El `post_` el tipo de columna de prefijo de datos, cuando se recopila en el lago de datos de Experience Platform, sin embargo requiere transformaciones avanzadas para poder utilizarse correctamente en un caso de uso de fuente de datos. La realización de estas transformaciones avanzadas en las consultas implica el uso de [Funciones definidas por el Adobe](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) para la creación de sesiones, atribución y deduplicación. Consulte [Ejemplos](#examples) sobre cómo utilizar estas funciones.

#### Búsquedas

Para buscar datos de otros conjuntos de datos, se utiliza la funcionalidad estándar de SQL (`WHERE` cláusula, `INNER JOIN`, `OUTER JOIN`, y otros).

#### Cálculos

Para realizar cálculos en campos (columnas), utilice las funciones SQL estándar (por ejemplo `COUNT(*)` o el [operadores y funciones matemáticos y estadísticos](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) forma parte de Spark SQL. Además, [funciones de ventana](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en#window-functions) proporciona soporte para actualizar acumulaciones y devolver elementos únicos para cada fila en un subconjunto ordenado. Consulte [Ejemplos](#examples) sobre cómo utilizar estas funciones.

#### Estructura de datos anidada

Los esquemas en los que se basan los conjuntos de datos suelen contener tipos de datos complejos, incluidas estructuras de datos anidadas. Mencionado anteriormente `identityMap` es un ejemplo de estructura de datos anidada. Consulte a continuación un ejemplo de `identityMap` datos.

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

Puede usar el complemento [`explode()` u otras funciones de matrices](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) desde Spark SQL para llegar a los datos dentro de una estructura de datos anidada, por ejemplo:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Como alternativa, puede hacer referencia a elementos individuales utilizando la notación de puntos. Por ejemplo:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Consulte [Trabajar con estructuras de datos anidadas en el servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) para obtener más información.


#### Ejemplos

Por ejemplo, las consultas que utilizan datos de conjuntos de datos en el lago de datos de Experience Platform, están tocando las capacidades adicionales de Funciones definidas por Adobe o Spark SQL y que ofrecerían resultados similares a los de una fuente de datos de Adobe Analytics equivalente, consulte

* [exploración abandonada](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en),
* [análisis de atribución](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en),
* [filtrado de bots](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en),
* y otros casos de uso de ejemplo en la guía del servicio de consultas.


### Programar consulta

Programe la consulta para asegurarse de que se ejecuta y de que los resultados se generan a su intervalo preferido.

#### Uso del Editor de consultas

Puede programar una consulta mediante el Editor de consultas. Al programar la consulta, se define un conjunto de datos de salida. Consulte [Programaciones de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) para obtener más información.


#### Uso de la API del servicio de consultas

También puede utilizar las API de RESTful para definir una consulta y una programación para la consulta. Consulte [Guía de API del servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) para obtener más información.
Asegúrese de definir el conjunto de datos de salida como parte del `ctasParameters` al crear la consulta ([Creación de una consulta](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) o al crear la programación para una consulta ([Creación de una consulta programada](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exportación de conjuntos de datos

Una vez que haya creado y programado la consulta, y verificado que los resultados de los conjuntos de datos de salida están en línea con los requisitos, puede exportar los conjuntos de datos sin procesar a destinos de almacenamiento en la nube. Esta exportación se realiza en la terminología Destinos de Experience Platform, que se denomina destinos de exportación de conjuntos de datos. Consulte [Exportar conjuntos de datos a destinos de almacenamiento en la nube](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=es) para obtener una descripción general.

Se admiten los siguientes destinos de almacenamiento en la nube:

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [Zona de aterrizaje de datos](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Almacenamiento de Google Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### IU de Experience Platform

Puede exportar y programar la exportación de los conjuntos de datos de salida a través de la interfaz de usuario de Experience Platform. En esta sección se describen los pasos que debe seguir.

#### Seleccionar destino

Cuando haya determinado a qué destino de almacenamiento en la nube desea exportar el conjunto de datos de salida, [seleccionar el destino](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). Cuando aún no haya configurado un destino para su almacenamiento en la nube preferido, debe [crear una nueva conexión de destino](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en).

Como parte de la configuración de un destino, puede definir el tipo de archivo (JSON o Parquet), si el archivo resultante debe comprimirse o no y si un archivo de manifiesto debe incluirse o no.


#### Seleccionar conjunto de datos

Cuando haya seleccionado el destino, en el siguiente **[!UICONTROL Seleccionar conjuntos de datos]** paso tiene que seleccionar el conjunto de datos de salida de la lista de conjuntos de datos. Si ha creado varias consultas programadas y desea que los conjuntos de datos de salida se envíen al mismo destino de almacenamiento en la nube, puede seleccionar los conjuntos de datos de salida correspondientes. Consulte [Seleccione sus conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) para obtener más información.

#### Programación de exportación del conjunto de datos

Por último, desea programar la exportación del conjunto de datos como parte del **[!UICONTROL Programación]** paso. En ese paso puede definir la programación y si la exportación del conjunto de datos de salida debe ser incremental o no. Consulte [Programar exportación del conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) para obtener más información.


#### Pasos finales

[Revisar](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) Haga su selección y cuando empiece a exportar correctamente el conjunto de datos de salida al destino de almacenamiento en la nube.

Usted debe [verificar](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) exportación de datos correcta. Al exportar conjuntos de datos, Experience Platform crea uno o varios `.json` o `.parquet` archivos en la ubicación de almacenamiento definida en el destino. Se espera que los nuevos archivos se depositen en su ubicación de almacenamiento según la programación de exportación configurada. Experience Platform crea una estructura de carpetas en la ubicación de almacenamiento especificada como parte del destino seleccionado, donde deposita los archivos exportados. Se crea una nueva carpeta para cada tiempo de exportación, siguiendo el patrón: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. El nombre de archivo predeterminado se genera de forma aleatoria y garantiza que los nombres de archivo exportados sean únicos.

### API de Flow Service

También puede exportar y programar la exportación de conjuntos de datos de salida mediante API. Los pasos involucrados se documentan en [Exportación de conjuntos de datos mediante la API de Flow Service](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### Introducción

Asegúrese de que dispone de [permisos necesarios](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) para exportar conjuntos de datos de y que el destino al que desea enviar el conjunto de datos de salida admita la exportación de conjuntos de datos. Entonces, debe [recopilar los valores de los encabezados obligatorios y opcionales](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) que utiliza en las llamadas API de, así como [identificar las especificaciones de conexión y los ID de especificación de flujo del destino](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) tiene intención de exportar conjuntos de datos a.

#### Recuperar conjuntos de datos aptos

Puede [recuperar una lista de conjuntos de datos aptos](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) para la exportación y compruebe si el conjunto de datos de salida forma parte de esa lista utilizando [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Crear conexión de origen

A continuación, debe [crear una conexión de origen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) para el conjunto de datos de salida, con su ID único, que desea exportar al destino de almacenamiento en la nube. Utilice el [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Autenticar en el destino (crear conexión base)

Ahora debe [crear una conexión base](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) para autenticar correctamente y almacenar de forma segura las credenciales en su destino de almacenamiento en la nube mediante el [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Proporcionar parámetros de exportación

A continuación, debe [crear una conexión de destino adicional que almacene los parámetros de exportación](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) para el conjunto de datos de salida utilizando, una vez más, la [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Estos parámetros de exportación incluyen ubicación, formato de archivo, compresión, etc.

#### Configurar flujo de datos

Finalmente, usted [configuración del flujo de datos](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) para asegurarse de que el conjunto de datos de salida se exporta al destino de almacenamiento en la nube mediante [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. En este paso, puede definir la programación de la exportación mediante el `scheduleParams` parámetro.

#### Validar flujo de datos

Hasta [compruebe las ejecuciones correctas del flujo de datos](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs), use el [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, especificando el ID del flujo de datos como parámetro de consulta. Este ID de flujo de datos es un identificador que se devuelve al configurar el flujo de datos.

[Verificar](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) exportación de datos correcta. Al exportar conjuntos de datos, Experience Platform crea uno o varios `.json` o `.parquet` archivos en la ubicación de almacenamiento definida en el destino. Se espera que los nuevos archivos se depositen en su ubicación de almacenamiento según la programación de exportación configurada. Experience Platform crea una estructura de carpetas en la ubicación de almacenamiento especificada como parte del destino seleccionado, donde deposita los archivos exportados. Se crea una nueva carpeta para cada tiempo de exportación, siguiendo el patrón: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. El nombre de archivo predeterminado se genera de forma aleatoria y garantiza que los nombres de archivo exportados sean únicos.

## Conclusión

En resumen, emular la funcionalidad de la fuente de datos de Adobe Analytics implica configurar consultas programadas mediante el servicio de consulta y utilizar los resultados de estas consultas en exportaciones de conjuntos de datos programados.

>[!IMPORTANT]
>
>En este caso de uso están involucrados dos programadores. Para garantizar el correcto funcionamiento de la funcionalidad de fuente de datos emulada, asegúrese de que las programaciones configuradas en el servicio de consulta y las exportaciones de datos no interfieran.
