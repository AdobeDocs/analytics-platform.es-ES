---
title: Configuración automática de medios de pago de Content Analytics
description: Obtenga información acerca de la configuración automática de conjuntos de datos, conexiones, vistas de datos y mucho más.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: e9274ad7899537837723e2eb9cd842c5449530ff
workflow-type: tm+mt
source-wordcount: '2309'
ht-degree: 2%
---
# Configuración automática de medios de pago

Al habilitar el canal de medios de pago en Content Analytics y guardar la configuración, Adobe actualiza la conexión seleccionada y las vistas de datos con la configuración de creación de informes para los conjuntos de datos de medios de pago. No es necesario que vuelva a crear las dimensiones, métricas, lógica de búsqueda o grupos de datos de resumen predeterminados.

Se crean tres capas de objetos:

| Objetos | Contiene | Finalidad |
| --- | --- | --- |
| Conjuntos de datos resumidos | Datos de rendimiento de la red de Advertising a nivel de anuncio, ubicación de experiencia o recurso, con desgloses demográficos y geográficos independientes cuando se admite. | Le permite medir la entrega, los clics, los gastos y los resultados de los informes de la red de publicidad |
| Conjuntos de datos de búsqueda de metadatos y atributos | Detalles de cuenta, campaña, grupo de publicidad, publicidad, experiencia y recursos; atributos creativos de Content Analytics. | Permite crear informes con nombres reconocibles, detalles creativos, miniaturas y atributos de contenido en lugar de utilizar identificadores. |
| Configuración y componentes de vista de datos | Dimensiones, métricas, métricas calculadas, campos derivados y grupos de datos de resumen. | Permite generar análisis de Workspace sin reconstruir manualmente las relaciones entre estos conjuntos de datos. |

Al habilitar los medios de pago, no se conectan automáticamente los datos de medios de pago a los pedidos, las reservas o los ingresos del sitio. La correlación entre los datos del evento de experiencia y los datos de medios de pago requiere una asignación de claves de seguimiento y una configuración de informes específicas del cliente.

## Conjuntos de datos resumidos

La siguiente ilustración muestra cómo se generan los conjuntos de datos de resumen al habilitar el canal de medios de pago en Content Analytics para una o varias de las redes de anuncios. Las API relevantes de las redes de publicidad disponibles se utilizan para descargar y transformar datos de experiencia, recursos y publicidad en potencialmente seis conjuntos de datos de resumen.

![Generación de medios de pago de conjuntos de datos de resumen](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

La red de anuncios específica determina qué conjuntos de datos de resumen se crean. No todas las redes de anuncios para las que se ha configurado un conector de origen generan los seis conjuntos de datos de resumen posibles. Consulte la tabla siguiente para obtener una descripción general de los conjuntos de datos de resumen con la siguiente información:

* Nombre del conjunto de datos de resumen, tipo de evento y sufijo de componente
* Entidad
* Desgloses
* Qué conjuntos de datos se han rellenado ![Marca de verificación](/help/assets/icons2/Checkmark.svg) para las siguientes redes:
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest, Snapchat y TikTok se encuentran en la fase de prueba limitada de su versión y es posible que aún no estén disponibles en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Customer Journey Analytics, consulte [lanzamientos de características de Customer Journey Analytics](/help/release-notes/releases.md)
    >


* Lo que representa cada fila de un conjunto de datos de resumen.

| Conjunto de datos de resumen<br/>Tipo de evento<br/>Sufijo de componente | Entidad<br/>Desglose | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Cada fila representa |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Agregar<br/>ninguno | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario de un anuncio sin desgloses demográficos o geográficos. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Anuncio<br/>edad, sexo | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario de un anuncio<br/>desglosado por edad y sexo. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Agregar<br/>país, región | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario de un anuncio<br/>desglosado por país y región. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experience<br>platform, position | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario asociado<br/>con la experiencia creativa de un anuncio,<br/>desglosado por plataforma y posición. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Recurso<br/>ninguno | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | | | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario de nivel de recurso<br/>en su contexto de anuncio/campaña<br/>sin desglose demográfico o geográfico. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Recurso<br/>edad, sexo | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | | | | | Rendimiento diario de nivel de recurso<br/>en su contexto de anuncio/campaña<br/>desglosado por edad y sexo. |


En esta tabla se describe la cobertura del conjunto de datos, no la garantía de que una red en particular rellene todos los campos de métricas o metadatos. Compruebe los campos necesarios para el análisis. Un campo no disponible o un desglose no admitido no es lo mismo que un valor cero medido para un campo.

Los conjuntos de datos de búsqueda independientes describen Cuenta, Campaña, Grupo de publicidad, Publicidad, Experiencia y Recurso. Proporcionan nombres y metadatos mediante GUID de entidad. No existe un emparejamiento uno a uno entre los conjuntos de datos de resumen y los seis conjuntos de datos de búsqueda.

La agrupación de datos de resumen reúne dimensiones equivalentes; la agrupación no suma los seis totales de métricas de rendimiento.

## Componentes

El canal de medios de pago de Content Analytics, una vez activado, también genera una serie de componentes de vista de datos. Estos componentes se proporcionan con un sufijo de componente para distinguir componentes con nombres similares entre sí.

### Métricas

Las distintas redes de anuncios devuelven desgloses de rendimiento diferentes. Content Analytics conserva esas distinciones en lugar de tratar cada versión de una métrica como intercambiable.

Por ejemplo:

| Componente | Significado | Análisis inicial adecuado |
| --- | --- | --- |
| Clics \| Resumen de publicidad | Clics notificados en el nivel sin desglose de anuncios | Rendimiento de la campaña o del anuncio |
| Clics \| Resumen de recursos | Clics notificados en el nivel de recurso | Rendimiento de recursos de Creative |
| Clics \| Información geográfica del anuncio | Clics del informe de ubicación geográfica de la publicidad | Rendimiento por país o región |
| Clics \| Ubicación de la experiencia | Clics del informe de ubicación de la experiencia | Rendimiento de Creative por ubicación |

Cada componente de métrica de clics sirve para un contexto de informe diferente. No puede sumar estos componentes de métricas en un total general. La misma actividad publicitaria subyacente se puede representar en más de un conjunto de datos de resumen.

### Dimensiones

Cada conjunto de datos de resumen contiene ID y GUID. El identificador es la identidad (de cuenta, campaña, grupo de anuncios, anuncio, experiencia y recurso) proporcionada por la red de anuncios y es único **en** los datos de la red de anuncios. El GUID es una identidad proporcionada por Adobe (para cuenta, campaña, grupo de anuncios, anuncio, experiencia y recurso) y es único **en** redes de anuncios. Los identificadores y GUID se utilizan para buscar los nombres y metadatos correspondientes.

### Campos derivados

Los campos derivados forman parte de la configuración automática de creación de informes. Los campos derivados traducen los identificadores en nombres y metadatos, exponen atributos creativos y admiten dimensiones equivalentes utilizadas en las fuentes de informes. No crean actividad publicitaria adicional ni atribuyen automáticamente una conversión de sitio web.

Utilice el mismo desglose para las métricas de un análisis y las dimensiones que admite ese desglose. Tenga en cuenta que los totales demográficos y geográficos no coinciden necesariamente con los totales sin desglose de una red de publicidad y no implican un error de ingesta.

## Informes y análisis

Una vez que haya terminado la configuración y la ingesta de medios de pago de Content Analytics, puede empezar con los informes y análisis. Consulte la tabla siguiente para ver algunos ejemplos. Utilice las dimensiones agrupadas canónicas cuando estén disponibles y elija las métricas en el nivel de sistema de informes correspondiente.

| Pregunta empresarial | Nivel inicial | Filas y desgloses | Inicio de métricas | Límite importante |
| --- | --- | --- | --- | --- |
| ¿Qué rendimiento tienen mis campañas y anuncios? | Resumen de publicidad | Nombre de campaña, Nombre de grupo de publicidad, Nombre de publicidad; opcionalmente Red de publicidad y Nombre de cuenta | Impresiones \| Resumen de publicidad, Clics \| Resumen de publicidad, Gasto \| Resumen de publicidad, CTR y CPC coincidentes | Utilice un nivel para los totales de envío/gasto; valide la moneda antes de combinar cuentas |
| ¿Qué recursos creativos obtienen la respuesta más sólida? | Resumen de recursos | Nombre del recurso (medios de pago), identidad del recurso; red de publicidad opcional | Impresiones \| Resumen de recursos, Clics \| Resumen de recursos, Tasa de pulsaciones \| Resumen de recursos | Se trata del rendimiento de los recursos informado por la red, no una prueba de una conversión in situ posterior |
| ¿Qué características de imagen están asociadas con el rendimiento? | Resumen de recursos | Etiquetas de recursos, objetos de recursos, categorías de personas de recursos, escenas de recursos u otros atributos de recursos disponibles | Impresiones, clics y CTR del resumen de recursos | La extracción de atributos debe estar disponible; las categorías de atributos multivalor pueden superponerse |
| ¿Qué características de mensajería están asociadas con el rendimiento de pago? | Ubicación de experiencia | Palabras clave de experiencia, tonos de experiencia, estrategias de persuasión de experiencia u otros atributos de experiencia disponibles; opcionalmente, Plataforma y ubicación | Impresiones \| Ubicación de la experiencia, Clics \| Ubicación de la experiencia, CTR coincidente | Requiere atributos de experiencia rellenados; los resultados son específicos de la ubicación y describen la asociación, no el impacto causal |
| ¿Qué ubicaciones funcionan mejor? | Ubicación de experiencia | Nombre de experiencia, plataforma, ubicación | Impresiones \| Ubicación de la experiencia, Clics \| Ubicación de la experiencia, CTR coincidente | Las definiciones de ubicación y los valores disponibles varían según la red de publicidad |
| ¿En qué se parecen los anuncios, activos y experiencias de Meta y Google? | Resumen de anuncio, Resumen de recursos o Ubicación de experiencia, seleccionados para la pregunta | Agregar una red con la campaña, el recurso o la dimensión de experiencia adecuados | El mismo nivel y definición de métrica para ambas redes | Comparar solo los campos rellenados por ambas redes; Google no rellena los tres resúmenes demográficos/geográficos en este modelo |

Estos informes pueden revelar asociaciones entre atributos creativos y rendimiento, no probar que un atributo haya causado un resultado.

Evitar combinaciones incompatibles: El nombre del recurso (medios de pago) con las métricas de resumen de publicidad no sustituye a un informe de recursos. Utilice las métricas de Resumen de recursos para las métricas de Análisis de recursos y Geografía de anuncios para el análisis de regiones. Las celdas vacías o nulas de un emparejamiento incompatible no deben interpretarse como prueba de que no hay actividad.

### Ejemplos

A continuación se muestran ejemplos de cómo informar y analizar el rendimiento de los medios de pago y cómo combinar los datos de experiencia y activos de Content Analytics con los datos de medios de pago.

#### Rendimiento de campaña de publicidad

Desea informar sobre el rendimiento de la campaña en el nivel de anuncio. En Analysis Workspace, utilice el nombre de la campaña como dimensión (filas) y utilice las métricas como se describe en la tabla siguiente. Cada métrica tiene el mismo sufijo de componente.

| Métricas | Nivel de informes |
| --- | --- |
| Impresiones | Resumen de publicidad |
| Clics | Resumen de publicidad |
| Gastar | Resumen de publicidad |
| Tasa de clics | Resumen de publicidad |
| Costo por clic | Resumen de publicidad |

Si lo desea, puede desglosar Nombre de campaña por Nombre de anuncio, pero mantener las cinco columnas en el nivel de Resumen de anuncio.

Para investigar recursos individuales, utilice una tabla independiente con Nombre del recurso (medios de pago) y las columnas Resumen del recurso coincidentes. No agregue los totales de las dos tablas.

#### Identificación de anuncios con mejor rendimiento

¿Quiere saber dónde está el mejor rendimiento de sus anuncios de Meta?

Para investigar, utilice desgloses adicionales para la geografía y la demografía. Utilice el nombre de la campaña o el nombre del anuncio como dimensión y utilice las métricas como se describe en la siguiente tabla. Cada métrica tiene el mismo sufijo de componente.

| Métricas | Nivel de informes |
| --- | --- |
| Impresiones | Geo del anuncio |
| Clics | Geo del anuncio |
| Gastar | Resumen de publicidad |
| Tasa de clics | Geo del anuncio |
| Costo por clic | Resumen de publicidad |


#### Unir datos de medios de pago con datos de eventos de experiencia

Únase al rendimiento de medios de pago con datos de comportamiento en el sitio para comprender cómo las campañas y los anuncios están asociados con la participación del sitio web, las conversiones y los ingresos. Por ejemplo, compare los clics en redes de publicidad y los gastos con los pedidos atribuidos a las visitas de la misma campaña.

Para configurar este sistema de informes, incluya los conjuntos de datos de resumen de medios de pago y el conjunto de datos de evento en el sitio en la misma conexión de Customer Journey Analytics. Capture identificadores de recursos estables de campaña, publicidad o admitidos a partir de parámetros de URL de página de aterrizaje o campos de evento existentes. Utilice campos derivados según sea necesario para analizar y asignar esos valores a los identificadores de medios de pago correspondientes, preservando el contexto de red y cuenta requerido. Mantenga los identificadores como cadenas. Para asociar las dimensiones de evento y resumen coincidentes, configure un Grupo de datos de resumen en la vista de datos. Al habilitar el canal de medios de pago, no se configura automáticamente este seguimiento y asignación de URL específicos de la implementación.


| Opción de seguimiento | Consideraciones |
|---|---|
| Meta Ads | Configure los parámetros de URL de destino mediante identificadores dinámicos como `campaign.id`, `adset.id` y `ad.id` donde se admita. Capture los valores resueltos en el sitio web. Al habilitar el conector, no se añaden automáticamente estos parámetros a las direcciones URL de los anuncios. |
| Google Ads | |
| Recursos individuales | La creación de informes a nivel de recurso de resultados descendentes requiere un identificador capturado que se asigna al recurso específico asociado con el clic. Un parámetro de URL personalizado puede admitir esto cuando el formato de anuncio permite el seguimiento específico del recurso. Un identificador de anuncio por sí solo no puede distinguir varios recursos dentro de un anuncio y un parámetro de recurso estático aplicado a un anuncio de varios recursos completo no identifica qué recurso se asoció con el clic. |

En Analysis Workspace, use las métricas **[!UICONTROL Resumen de anuncios]** para comparaciones de campañas o anuncios y las métricas **[!UICONTROL Resumen de recursos]** para comparaciones de recursos admitidas. Aplique un modelo de atribución y una ventana retrospectiva a las métricas de conversión en el sitio que reflejen su pregunta sobre la creación de informes.

Tenga en cuenta lo siguiente:

* Los datos de medios de pago son datos de resumen agregados sin un ID de persona. El comportamiento en el sitio son los datos de evento.
* La agrupación de dimensiones coincidentes admite la creación de informes entre estas fuentes, pero no coincide con las conversiones de red de anuncios individuales a las conversiones de sitios web o realiza la vinculación a nivel de persona.
* La comparación muestra una asociación, no un alza causal.
* Los resultados pueden diferir debido a las definiciones de conversión, las ventanas de atribución, las conversiones visualizadas o modeladas, el consentimiento y las fechas de los informes o las zonas horarias.
* Valide el origen de las visitas etiquetadas con campañas cuando se reutilizan los parámetros de seguimiento en los distintos canales.


#### Comparar el rendimiento de la campaña con los pedidos in situ

Una dirección URL de página de aterrizaje puede contener varios parámetros de seguimiento. En este ejemplo, el identificador de campaña de `utm_id` se usa para comparar el gasto de campaña con los pedidos de sitios web.

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

El parámetro usado para esta comparación: `utm_id=120218706543980215`. Los demás parámetros describen la etiqueta de origen, medio y campaña, pero no se utilizan como campo coincidente en este ejemplo.

Si la dirección URL se captura en los datos de evento del sitio web y tanto el conjunto de datos de evento del sitio web como los conjuntos de datos de medios de pago forman parte de la misma conexión de Customer Journey Analytics:

1. Identifique la campaña. Utilice un campo derivado para leer `utm_id` de la dirección URL y asignar su valor al identificador de campaña correspondiente en los datos de medios de pago.
1. Agrupe las dimensiones coincidentes. En la vista de datos, agregue la dimensión de campaña del sitio web a `Summary Data Group` de la dimensión de campaña de pago, conservando los miembros existentes.
1. Comparar gastos y pedidos. En Analysis Workspace, utilice la dimensión de campaña agrupada como las filas de una tabla de forma libre. Agregue `Ad Summary` gasto y sitio web `Orders` como columnas. Establezca el modelo de atribución y la ventana retrospectiva para `Orders`.


La tabla de forma libre muestra el gasto de red de anuncios junto con los pedidos de sitios web atribuidos a cada campaña. Dos campañas con un gasto en publicidad similar tienen un número diferente de acciones de sitio web descendentes atribuidas. Utilice esta comparación para identificar campañas y experiencias de página de aterrizaje para realizar más investigaciones o pruebas, en lugar de evaluar el rendimiento únicamente a partir de métricas de publicidad.

El ejemplo utiliza un ID de campaña, pero el mismo método puede utilizar identificadores de grupo de anuncios, publicidad o recurso cuando se pueden capturar valores coincidentes. Los atributos de Content Analytics, como **[!UICONTROL Colores de primer plano de recursos]**, le permiten comparar características creativas con el rendimiento de medios de pago. Con las dimensiones de atributos de coincidencia y seguimiento específicas del recurso configuradas en ambos orígenes, puede ampliar esa comparación a pedidos de sitios web atribuidos y utilizar los resultados para guiar las pruebas creativas.

#### Combinación del rendimiento del recurso con los datos web

Si desea informar y analizar el rendimiento de los recursos relacionados con sus inversiones en medios de pago, considere la posibilidad de agregar un parámetro de UTM de recursos específico en la configuración de medios de pago de la red de publicidad. Por ejemplo, además de parámetros dinámicos estándar como s`ite_source_name`, `campaign.id`, `adset.id` o `placement`, agregue parámetros personalizados estáticos, como `aca_asset_id=999999`.

Este parámetro personalizado se añade a la dirección URL de la página de aterrizaje. Por ejemplo: https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&amp;aca_id_2=8888888&amp;utm_medium=paid&amp;utm_source=fb&amp;utm_id=120241705099830539&amp;utm_term=120241705099840539&amp;utm_campaign=120241705099830539

Ahora tiene una relación entre un recurso de una página y los datos de medios de pago. Use esa relación en Analysis Workspace para ver cómo los metadatos de recursos de Content Analytics (por ejemplo, **[!UICONTROL Colores de primer plano de los recursos]**) contribuyen al éxito de la campaña de medios de pago.


<!--

Do we need to include the tables from the Wiki?

## Reference

The following table lists paid media fields, their XDM paths, provisioned components, and reporting visibility.

+++ Paid media fields

| Field name | XDM path | ACA Paid Media component | Provisioning status | Reporting visibility |
| --- | --- | --- | --- | --- |
| Ad Network | `paidMedia.adNetwork` | Ad Network (dimension) | existing | visible through shared grouping: Ad Network |
| Channel | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | existing | visible through shared grouping: Content Channel |
| Account GUID | `paidMedia.accountGUID` | Account GUID (dimension) | existing | visible through shared grouping: Account GUID |
| Campaign GUID | `paidMedia.campaignGUID` | Campaign GUID (dimension) | existing | visible through shared grouping: Campaign GUID |
| Ad Group GUID | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | existing | visible through shared grouping: AdGroup GUID |
| Ad GUID | `paidMedia.adGUID` | Ad GUID (dimension) | existing | visible through shared grouping: Ad GUID |
| Experience GUID | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | existing | visible through shared grouping: Experience Id |
| Asset GUID | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | existing | visible through shared grouping: Asset Id |
| Name | `paidMedia.metadata.name` | Ad Name (derived field)<br/>Ad Name (shared dimension)<br/>AdGroup Name (derived field)<br/>AdGroup Name (shared dimension)<br/>Asset Name (Paid Media) (derived field)<br/>Asset Name (Paid Media) (shared dimension)<br/>Campaign Name (derived field)<br/>Campaign Name (shared dimension)<br/>Experience Name (derived field)<br/>Experience Name (shared dimension) | existing | visible through shared grouping: Ad Name, AdGroup Name, Asset Name (Paid Media), Campaign Name, Experience Name |
| Status | `paidMedia.metadata.status` | Ad Status (derived field)<br/>Ad Status (shared dimension)<br/>Ad Group Status (derived field)<br/>Ad Group Status (shared dimension)<br/>Campaign Status (derived field)<br/>Campaign Status (shared dimension) | curated net-new | visible through shared grouping: Ad Status, Ad Group Status, Campaign Status |
| Serving Status | `paidMedia.metadata.servingStatus` | | excluded | missing provisioned component |
| Updated Time | `paidMedia.metadata.updatedTime` | | excluded | missing provisioned component |
| Account Name | `paidMedia.accountDetails.accountName` | Account Name (derived field)<br/>Account Name (shared dimension) | existing | visible through shared grouping: Account Name |
| Currency | `paidMedia.accountDetails.currency` | Account Currency (derived field)<br/>Account Currency (shared dimension) | curated net-new | visible through shared grouping: Account Currency |
| Timezone | `paidMedia.accountDetails.timezone` | Account Timezone (derived field)<br/>Account Timezone (shared dimension) | curated net-new | visible through shared grouping: Account Timezone |
| Account Type | `paidMedia.accountDetails.accountType` | Account Type (derived field)<br/>Account Type (shared dimension) | curated net-new | visible through shared grouping: Account Type |
| Business Name | `paidMedia.accountDetails.businessName` | Account Business Name (derived field)<br/>Account Business Name (shared dimension) | curated net-new | visible through shared grouping: Account Business Name |
| Campaign Type | `paidMedia.campaignDetails.campaignType` | Campaign Type (derived field)<br/>Campaign Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Type |
| Objective | `paidMedia.campaignDetails.objective` | Campaign Objective (derived field)<br/>Campaign Objective (shared dimension) | curated net-new | visible through shared grouping: Campaign Objective |
| Is Automated Campaign | `paidMedia.campaignDetails.isAutomatedCampaign` | Campaign Is Automated \| Ad Summary (derived field) | curated net-new | hidden |
| Bid Strategy | `paidMedia.campaignDetails.budgetSettings.bidStrategy` | Campaign Bid Strategy (derived field)<br/>Campaign Bid Strategy (shared dimension) | curated net-new | visible through shared grouping: Campaign Bid Strategy |
| Budget Type | `paidMedia.campaignDetails.budgetSettings.budgetType` | Campaign Budget Type (derived field)<br/>Campaign Budget Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Budget Type |
| Daily Budget | `paidMedia.campaignDetails.budgetSettings.dailyBudget` | Campaign Daily Budget (derived field)<br/>Campaign Daily Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Daily Budget |
| Lifetime Budget | `paidMedia.campaignDetails.budgetSettings.lifetimeBudget` | Campaign Lifetime Budget (derived field)<br/>Campaign Lifetime Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Lifetime Budget |
| Campaign Budget Optimization | `paidMedia.campaignDetails.budgetSettings.isCampaignBudgetOptimization` | Campaign Budget Optimization \| Ad Summary (derived field) | curated net-new | hidden |
| Catalog ID | `paidMedia.campaignDetails.catalogId` | Campaign Catalog ID \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.campaignDetails.startTime` | Campaign Start Time (derived field)<br/>Campaign Start Time (shared dimension) | curated net-new | visible through shared grouping: Campaign Start Time |
| End Time | `paidMedia.campaignDetails.endTime` | Campaign End Time (derived field)<br/>Campaign End Time (shared dimension) | curated net-new | visible through shared grouping: Campaign End Time |
| Ad Group Type | `paidMedia.adGroupDetails.adGroupType` | Ad Group Type (derived field)<br/>Ad Group Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Type |
| Bid Strategy Type | `paidMedia.adGroupDetails.budgetSettings.bidStrategyType` | Ad Group Bid Strategy Type (derived field)<br/>Ad Group Bid Strategy Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Bid Strategy Type |
| Optimization Goal | `paidMedia.adGroupDetails.optimizationSettings.optimizationGoal` | Ad Group Optimization Goal (derived field)<br/>Ad Group Optimization Goal (shared dimension) | curated net-new | visible through shared grouping: Ad Group Optimization Goal |
| Delivery Status | `paidMedia.adGroupDetails.deliverySettings.deliveryStatus` | Ad Group Delivery Status \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.adGroupDetails.startTime` | Ad Group Start Time (derived field)<br/>Ad Group Start Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group Start Time |
| End Time | `paidMedia.adGroupDetails.endTime` | Ad Group End Time (derived field)<br/>Ad Group End Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group End Time |
| Ad Type | `paidMedia.adDetails.adType` | Ad Type (derived field)<br/>Ad Type (shared dimension) | curated net-new | visible through shared grouping: Ad Type |
| Delivery Status | `paidMedia.adDetails.deliveryStatus` | Ad Delivery Status (derived field)<br/>Ad Delivery Status (shared dimension) | curated net-new | visible through shared grouping: Ad Delivery Status |
| Review Status | `paidMedia.adDetails.reviewStatus` | Ad Review Status (derived field)<br/>Ad Review Status (shared dimension) | curated net-new | visible through shared grouping: Ad Review Status |
| Creative Type | `paidMedia.adDetails.creative.paidMediaCreative.creativeType` | Ad Creative Type (derived field)<br/>Ad Creative Type (shared dimension) | curated net-new | visible through shared grouping: Ad Creative Type |
| Title | `paidMedia.adDetails.creative.paidMediaCreative.title` | Ad Title (derived field)<br/>Ad Title (shared dimension) | curated net-new | visible through shared grouping: Ad Title |
| Call to Action | `paidMedia.adDetails.creative.paidMediaCreative.callToAction` | Ad Call to Action (derived field)<br/>Ad Call to Action (shared dimension) | curated net-new | visible through shared grouping: Ad Call to Action |
| Destination URL | `paidMedia.adDetails.creative.paidMediaCreative.destinationURL` | Ad Destination URL (derived field)<br/>Ad Destination URL (shared dimension) | curated net-new | visible through shared grouping: Ad Destination URL |
| Display URL | `paidMedia.adDetails.creative.paidMediaCreative.displayURL` | Ad Display URL (derived field)<br/>Ad Display URL (shared dimension) | curated net-new | visible through shared grouping: Ad Display URL |
| Experience Type | `paidMedia.experienceDetails.experienceType` | Experience Type (derived field)<br/>Experience Type (shared dimension) | curated net-new | visible through shared grouping: Experience Type |
| Landing Page URL | `paidMedia.experienceDetails.landingPageURL` | Experience Landing Page URL (derived field)<br/>Experience Landing Page URL (shared dimension) | curated net-new | visible through shared grouping: Experience Landing Page URL |
| Call To Action | `paidMedia.experienceDetails.callToAction` | Experience Call to Action (derived field)<br/>Experience Call to Action (shared dimension) | curated net-new | visible through shared grouping: Experience Call to Action |
| Card Count | `paidMedia.experienceDetails.carouselProperties.cardCount` | Experience Card Count \| Ad Summary (derived field) | curated net-new | hidden |
| Asset Type | `paidMedia.assetDetails.assetType` | Asset Type (derived field)<br/>Asset Type (shared dimension) | curated net-new | visible through shared grouping: Asset Type |
| Permalink URL | `paidMedia.assetDetails.mediaProperties.permalinkURL` | Asset Permalink URL \| Ad Summary (derived field) | curated net-new | hidden |
| Width | `paidMedia.assetDetails.dimensions.width` | Asset Width (derived field)<br/>Asset Width (shared dimension) | curated net-new | visible through shared grouping: Asset Width |
| Height | `paidMedia.assetDetails.dimensions.height` | Asset Height (derived field)<br/>Asset Height (shared dimension) | curated net-new | visible through shared grouping: Asset Height |
| Aspect Ratio | `paidMedia.assetDetails.dimensions.aspectRatio` | Asset Aspect Ratio (derived field)<br/>Asset Aspect Ratio (shared dimension) | curated net-new | visible through shared grouping: Asset Aspect Ratio |
| Orientation | `paidMedia.assetDetails.dimensions.orientation` | Asset Orientation \| Ad Summary (derived field)<br/>Asset Orientation (shared dimension) | curated net-new | visible through shared grouping: Asset Orientation |
| MIME Type | `paidMedia.assetDetails.fileProperties.mimeType` | Asset MIME Type \| Ad Summary (derived field) | curated net-new | hidden |
| Impressions | `paidMedia.metrics.impressions` | Impressions \| Ad Summary (metric) | existing | visible |
| Clicks | `paidMedia.metrics.clicks` | Clicks \| Ad Summary (metric) | existing | visible |
| Spend | `paidMedia.metrics.spend` | Spend \| Ad Summary (metric) | existing | visible |
| Reach | `paidMedia.metrics.reach` | Reach \| Ad Summary (metric) | curated net-new | visible |
| Conversions | `paidMedia.metrics.conversions` | Conversions \| Ad Summary (metric) | curated net-new | visible |
| Conversion Value | `paidMedia.metrics.conversionValue` | Conversion Value \| Ad Summary (metric) | curated net-new | visible |
| Video Views | `paidMedia.metrics.videoViews` | Video Views \| Ad Summary (metric) | curated net-new | visible |
| Engagements | `paidMedia.metrics.engagements` | Engagements \| Ad Summary (metric) | curated net-new | visible |
| Post-Click Conversions | `paidMedia.conversionMetrics.postClickConversions` | Post-Click Conversions \| Ad Summary (metric) | curated net-new | visible |
| Post-View Conversions | `paidMedia.conversionMetrics.postViewConversions` | Post-View Conversions \| Ad Summary (metric) | curated net-new | visible |
| Purchases | `paidMedia.conversionMetrics.conversionsByType.purchases` | Purchases \| Ad Summary (metric) | curated net-new | visible |
| Add to Cart | `paidMedia.conversionMetrics.conversionsByType.addToCart` | Add to Cart \| Ad Summary (metric) | curated net-new | visible |
| Leads | `paidMedia.conversionMetrics.conversionsByType.leads` | Leads \| Ad Summary (metric) | curated net-new | visible |
| Registrations | `paidMedia.conversionMetrics.conversionsByType.registrations` | Registrations \| Ad Summary (metric) | curated net-new | visible |
| Downloads | `paidMedia.conversionMetrics.conversionsByType.downloads` | Downloads \| Ad Summary (metric) | curated net-new | visible |
| Subscriptions | `paidMedia.conversionMetrics.conversionsByType.subscriptions` | Subscriptions \| Ad Summary (metric) | curated net-new | visible |
| Landing Page View | `paidMedia.conversionMetrics.conversionsByType.landingPageView` | Landing Page Views \| Ad Summary (metric) | curated net-new | visible |
| Total Order Value | `paidMedia.conversionMetrics.totalOrderValue` | Total Order Value \| Ad Summary (metric) | curated net-new | visible |
| Video Plays | `paidMedia.videoMetrics.videoPlays` | Video Plays \| Ad Summary (metric) | curated net-new | visible |
| Video Completions | `paidMedia.videoMetrics.videoCompletions` | Video Completions \| Ad Summary (metric) | curated net-new | visible |
| Link Clicks | `paidMedia.extendedMetrics.linkClicks` | Link Clicks \| Ad Summary (metric) | curated net-new | visible |
| Outbound Clicks | `paidMedia.extendedMetrics.outboundClicks` | Outbound Clicks \| Ad Summary (metric) | curated net-new | visible |
| App Installs | `paidMedia.extendedMetrics.appInstalls` | App Installs \| Ad Summary (metric) | curated net-new | visible |
| Lead Submissions | `paidMedia.extendedMetrics.leadSubmissions` | Lead Submissions \| Ad Summary (metric) | curated net-new | visible |
| Device Type | `paidMedia.dimensionalBreakdowns.deviceType` | | excluded | removed in source range |
| Placement | `paidMedia.dimensionalBreakdowns.placement` | Placement (dimension) | curated net-new | visible through shared grouping: Placement |
| Platform | `paidMedia.dimensionalBreakdowns.platform` | Platform (dimension) | curated net-new | visible through shared grouping: Platform |
| Country | `paidMedia.dimensionalBreakdowns.country` | Country (dimension) | curated net-new | visible through shared grouping: Country |
| Region | `paidMedia.dimensionalBreakdowns.region` | Region (dimension) | curated net-new | visible through shared grouping: Region |
| Other connector-populated fields | See field tables | No named component | excluded | not surfaced |

+++

### Identifiers

| Field name | Description | XDM path | ACA Paid Media component | ACA context label | Meta | Google Ads | Pinterest | Snapchat | TikTok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Record ID | *Unique record URI, inherited from data/record.* | `@id` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (pinterest:&lt;entity&gt;: source-derived composite record ID; GUIDs use pinterest_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (snapchat:&lt;entity&gt;: source-derived composite record ID; GUIDs use snapchat_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (tiktok:&lt;entity&gt;: source-derived composite record ID; GUIDs use tiktok_; summary IDs omit dimension values; writer emits _id.) |
| Entity Type | The type of paid media entity | `entityType` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) |
| Ad Network | The advertising platform/network | `paidMedia.adNetwork` | Ad Network (dimension) | Ad Network | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads`) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Network | Alias of adNetwork for migration from GenStudio templates | `paidMedia.network` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Channel | Content channel indicating the source of the data (e.g., Web, Mobile, PaidMedia). Used as a reporting dimension for cross-channel breakdowns. | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | Content Channel (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) |
| Hierarchy Path | Full hierarchical path showing parent-child relationships (e.g., account_id/campaign_id/adgroup_id/ad_id) | `paidMedia.hierarchyPath` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account ID | Unique identifier for the ad account within the network | `paidMedia.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Unique identifier for the ad account across all networks | `paidMedia.accountGUID` | Account GUID (dimension) | Account Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign ID | Unique identifier for the campaign within the network | `paidMedia.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign GUID | Unique identifier for the campaign across all networks | `paidMedia.campaignGUID` | Campaign GUID (dimension) | Campaign Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group ID | Unique identifier for the ad group/ad set/ad squad within the network | `paidMedia.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group GUID | Unique identifier for the ad group/ad set/ad squad across all networks | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | AdGroup Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad ID | Unique identifier for the individual ad within the network | `paidMedia.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad GUID | Unique identifier for the individual ad across all networks | `paidMedia.adGUID` | Ad GUID (dimension) | Ad Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Experience ID | Unique identifier for creative experience (multi-asset compositions) within the network | `paidMedia.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Ad ID on Experience lookup and summaries; null on Ad lookup; asset reverse join recovers ad ID when metadata matches.) |
| Experience GUID | Unique identifier for creative experience (multi-asset compositions) across all networks | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | Experience Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset ID | Unique identifier for creative assets (images, videos, etc.) within the network | `paidMedia.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset GUID | Unique identifier for creative assets (images, videos, etc.) across all networks | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | Asset Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Account GUID (class entityIDs hierarchy) | `entityIDs.account.accountGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Account ID | Account ID (class entityIDs hierarchy) | `entityIDs.account.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign GUID | Campaign GUID (class entityIDs hierarchy) | `entityIDs.campaign.campaignGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign ID | Campaign ID (class entityIDs hierarchy) | `entityIDs.campaign.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group GUID | Ad Group GUID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group ID | Ad Group ID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad GUID | Ad GUID (class entityIDs hierarchy) | `entityIDs.ad.adGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad ID | Ad ID (class entityIDs hierarchy) | `entityIDs.ad.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience GUID | Experience GUID (class entityIDs hierarchy) | `entityIDs.experience.experienceGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience ID | Experience ID (class entityIDs hierarchy) | `entityIDs.experience.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset GUID | Asset GUID (class entityIDs hierarchy) | `entityIDs.asset.assetGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset ID | Asset ID (class entityIDs hierarchy) | `entityIDs.asset.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group Name | Display name of the ad group/ad set/ad squad. Mirrors metadata.name from the ad group lookup. | `paidMedia.denormalizedNames.adGroupName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad group name"))`) | | |
| Ad Name | Display name of the individual ad. Mirrors metadata.name from the ad lookup. | `paidMedia.denormalizedNames.adName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad name"))`) | | |
| Campaign Name | Display name of the campaign. Mirrors metadata.name from the campaign lookup. | `paidMedia.denormalizedNames.campaignName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Campaign name"))`) | | |

-->
