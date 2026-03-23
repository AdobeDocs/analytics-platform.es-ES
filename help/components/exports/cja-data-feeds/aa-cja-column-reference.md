---
title: Asignación de columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics
description: Determine cómo tomar una columna de fuente de datos de Adobe Analytics determinada y determine su equivalente aproximado en la implementación de Customer Journey Analytics.
feature: Components
hide: true
hidefromtoc: true
source-git-commit: fbd48b74505e18c24260b87b715ad036a6a60020
workflow-type: tm+mt
source-wordcount: '3236'
ht-degree: 64%

---

# Asignación de columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics

Dado que Adobe Analytics y Customer Journey Analytics funcionan de manera fundamentalmente diferente, no es posible asignar columnas 1:1. Estas diferencias se ven exacerbadas por el hecho de que cada implementación de Adobe Analytics y Customer Journey Analytics difiere considerablemente.

Esta referencia se ha diseñado para ayudar a los ingenieros de datos a ajustar columna por columna sus flujos de trabajo de fuentes de datos centrados en Adobe Analytics a un flujo de trabajo basado en fuentes de datos de Customer Journey Analytics.

>[!NOTE]
>
>Esta referencia solo incluye columnas que Adobe considera actuales, según la [referencia de columna de fuente de datos de Analytics](https://experienceleague.adobe.com/es/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). Si tiene una columna de fuente de datos de Analytics que no aparece en esta tabla y que utiliza de forma activa, consulte el documento de diseño de soluciones de su organización para determinar su mejor equivalente en Customer Journey Analytics.

+++**`accept_language`**

Enumera todos los idiomas aceptados, tal como se indica en el encabezado Accept-Language-HTTP de las solicitudes de imagen.

+++

+++**`adload`**

Cargas de anuncios de medios

{{cja-df-post}}

+++

+++**`aemassetid`**

Variable de varios valores que corresponde a los ID de recurso (GUID) de un conjunto de recursos de Adobe Experience Manager. Aumenta los eventos de impresión.

{{cja-df-post}}

+++

+++**`aemassetsource`**

Identifica el origen del evento del recurso. Se utiliza en Adobe Experience Manager.

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

ID de recurso de un recurso de Adobe Experience Manager. Incrementa los eventos de clic.

{{cja-df-post}}

+++

+++**`amo_cid`**

La dimensión de ID de AMO que se utiliza en las integraciones de Adobe Advertising.

{{cja-df-post}}

+++

+++**`amo_ef_id`**

La dimensión de ID de EF de AMO que se utiliza en las integraciones de Adobe Advertising.

{{cja-df-post}}

+++

+++**`browser`**

Un ID numérico que representa el explorador. Se remite a la tabla de búsqueda `browser.tsv`.

+++

+++**`browser_height`**

La dimensión Altura del explorador.

{{cja-df-post}}

+++

+++**`browser_width`**

La anchura del explorador

{{cja-df-post}}

+++

+++**`campaign`**

La dimensión Código de seguimiento.

{{cja-df-post}}

+++

+++**`carrier`**

Variable de integración de Adobe Advertising. Especifica el operador de telefonía móvil. El valor clave de `carrier.tsv` búsqueda dinámica.

+++

+++**`channel`**

La dimensión Secciones del sitio.

{{cja-df-post}}

+++

+++**`ch_hdr`**

Sugerencias del cliente recopiladas mediante el encabezado de petición HTTP.

+++

+++**`ch_js`**

Sugerencias del cliente recopiladas mediante la API de JavaScript de sugerencias del cliente agente de usuario.

+++

+++**`clickmaplink`**

La dimensión Vínculo de Activity Map.

{{cja-df-post}}

+++

+++**`clickmaplinkbyregion`**

La dimensión Vínculo de Activity Map por región.

{{cja-df-post}}

+++

+++**`clickmappage`**

La dimensión Página de Activity Map.

{{cja-df-post}}

+++

+++**`clickmapregion`**

La dimensión Región de Activity Map.

{{cja-df-post}}

+++

+++**`code_ver`**

Versión de la API o del SDK cliente utilizado para compilar y enviar la solicitud de imagen.

+++

+++**`color`**

ID de profundidad de color basada en el valor de la columna `c_color`. Se remite a la tabla de búsqueda `color_depth.tsv`.

+++

+++**`connection_type`**

ID numérica que representa la dimensión Tipo de conexión. Se remite a la tabla de búsqueda `connection_type.tsv`.

+++

+++**`cookies`**

La dimensión Compatibilidad con cookies.<br>S: Habilitado<br>N: No habilitado<br>D: Desconocido

{{cja-df-post}}

+++

+++**`country`**

Un ID numérico que representa el país del visitante. Se remite a la tabla de búsqueda `country.tsv`.

+++

+++**`currency`**

El código de moneda que se ha utilizado durante la transacción. Configurado mediante `currencyCode`.

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

En relación con la columna `connection_type`. Los valores más comunes son LAN/Wi-Fi, operador de telefonía móvil y módem.

+++

+++**`curr_factor`**

Determina la posición decimal de la moneda. Se utiliza para la conversión de moneda. Por ejemplo, USD utiliza dos decimales, por lo que el valor de esta columna sería `2`.

+++

+++**`curr_rate`**

El tipo de cambio cuando se produjo la transacción. Adobe se asocia con XE para determinar el tipo de cambio del día actual.

+++

+++**`customer_perspective`**

Determina si la visita es una visita en segundo plano de un dispositivo móvil.

{{cja-df-post}}

+++

+++**`cust_hit_time_gmt`**

Solo grupos de informes con marca de tiempo. La marca de tiempo enviada con la visita y basada en el Tiempo UNIX®.

{{cja-df-post}}

+++

+++**`cust_visid`**

El ID de visitante personalizado, si se establece mediante `visitorID`.

{{cja-df-post}}

+++

+++**`c_color`**

Profundidad de bits de la paleta de colores. Se utiliza en el cálculo de la dimensión Profundidad de color. AppMeasurement utiliza la función JavaScript `screen.colorDepth()`.

+++

+++**`daily_visitor`**

Un indicador que determina si la visita es un visitante nuevo diario.

+++

+++**`dataprivacyconsentoptin`**

La dimensión Inclusión en la administración de consentimiento. Puede haber varios valores por visita, separados por una barra vertical (`\|`). Los valores válidos incluyen `DMP` y `SELL`.

+++

+++**`dataprivacyconsentoptout`**

La dimensión Exclusión de la administración de consentimiento. Puede haber varios valores por visita, separados por una barra vertical (`\|`). Los valores válidos incluyen `SSF`, `DMP` y `SELL`.

+++

+++**`date_time`**

La hora de la visita en un formato legible, basada en la zona horaria del grupo de informes.

+++

+++**`domain`**

La dimensión Dominio. Basado en el punto de acceso a Internet del visitante.

+++

+++**`duplicated_from`**

Solo se utiliza en los grupos de informes que contienen las reglas de VISTA de copia de visita. Indica de qué grupo de informes se copió la visita.

+++

+++**`duplicate_events`**

Enumera cada evento que se contó como duplicado.

+++

+++**`duplicate_purchase`**

Un indicador que determina que el evento de compra de esta visita se ignora porque es un duplicado.

+++

+++**`ef_id`**

El EF ID, utilizado en las integraciones de Adobe Advertising.

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

Variables personalizadas 1-250. Se utiliza en dimensiones de eVar. Cada organización utiliza las eVars de forma diferente. El mejor lugar para obtener más información sobre cómo su organización rellena las eVars respectivas es un documento de diseño de solución específico para su organización.

{{cja-df-post}}

+++

+++**`event_list`**

Lista separada por comas de los ID numéricos que representan los eventos activados en la visita. Incluye tanto eventos de comercio como eventos personalizados 1-1000. Utiliza la búsqueda `event.tsv`.

Es probable que esta columna se asigne a docenas de métricas independientes, según la implementación. Adobe recomienda realizar el siguiente proceso para asignar cada métrica respectiva de Customer Journey Analytics a su valor numérico representado en esta columna de fuente de datos de Analytics:

1. Utilice la búsqueda `event.tsv` para asignar cada valor numérico a su nombre de métrica.
1. Utilice el documento de diseño de la solución para asignar cada nombre de evento de Analytics a su nombre de métrica correspondiente en Customer Journey Analytics.
1. Seleccione el componente asignado en la interfaz de usuario de las vistas de datos y anote su ID de componente. Si el ID de componente es demasiado difícil de manejar, puede rellenar el campo ID de alias de fuente de datos y utilizarlo en su lugar.
1. Repita el proceso para cada métrica que utilice su organización.

{{cja-df-post}}

+++

+++**`exclude_hit`**

Un indicador que determina si la visita se excluye de la creación de informes. La columna `visit_num` no aumenta con las visitas excluidas.<br>1: No se usa. Parte de una función limpiada.<br>2: No se usa. Parte de una función limpiada.<br>3: Ya no se utiliza. Exclusión de agente de usuario<br>4: Exclusión basada en la dirección IP<br>5: Falta información clave de visitas, como `page_url`, `pagename`, `page_event` o `event_list`<br>6: JavaScript no ha procesado la visita correctamente<br>7: Exclusión específica de la cuenta, como en reglas VISTA<br>8: Sin usar. Exclusión alternativa específica de la cuenta.<br>9: No se usa. Parte de una función limpiada.<br>10: Código de moneda no válido<br>11: La visita individual no incluye una marca de tiempo en un grupo de informes solo de marca de tiempo o una visita que contiene una marca de tiempo en un grupo de informes que no es de marca de hora<br>12: No se usa. Parte de una función limpiada.<br>13: No se usa. Parte de una función limpiada.<br>14: La visita de Target que no coincide con una visita de Analytics<br>15: No se utiliza actualmente.<br>16: Visita de Advertising Cloud que no coincide con una visita de Analytics

+++

+++**`first_hit_pagename`**

La dimensión Página de entrada original. El nombre de la página de entrada original del visitante.

+++

+++**`first_hit_page_url`**

La primera URL del visitante.

+++

+++**`first_hit_referrer`**

La primera URL de referencia del visitante.

+++

+++**`first_hit_ref_domain`**

La dimensión Dominio de referencia original. Basado en `first_hit_referrer`. El primer dominio de referencia del visitante.

+++

+++**`first_hit_ref_type`**

Un ID numérico que representa el tipo de referente del primer referente del visitante. Se remite a la tabla de búsqueda `referrer_type.tsv`.

+++

+++**`first_hit_time_gmt`**

Marca de tiempo de la primera visita del visitante en tiempo UNIX®.

+++

+++**`geo_city`**

El nombre de la ciudad de la que provino la visita basada en la dirección IP. Se utiliza en la dimensión Ciudades.

+++

+++**`geo_country`**

Abreviatura del país del que provino la visita basada en la dirección IP. Se utiliza en la dimensión Países.

+++

+++**`geo_dma`**

Un ID numérico del área demográfica de la que provino la visita basada en la dirección IP. Se utiliza en la dimensión US DMA.

+++

+++**`geo_region`**

El nombre del estado o región del que provino la visita basada en la dirección IP. Se utiliza en la dimensión Regiones.

+++

+++**`geo_zip`**

El código postal del que provino la visita basada en la dirección IP. Ayuda a rellenar la dimensión Código postal. Consulte también `zip`.

+++

+++**`hitid_high`**

Se utiliza en combinación con `hitid_low` para identificar una visita.

+++

+++**`hitid_low`**

Se utiliza en combinación con `hitid_high` para identificar una visita.

+++

+++**`hit_source`**

Indica la fuente de la que provino la visita. Se facturan las fuentes de visitas 1 y 2. <br>1: Solicitud de imagen estándar sin marca de tiempo <br>2: Solicitud de imagen estándar con marca de tiempo <br>3: Carga del origen de datos activo con marcas de tiempo <br>4: No utilizado <br>5: Carga genérica del origen de datos <br>6: Ya no se utiliza; carga completa del origen de datos de procesamiento <br>7: Carga del origen de datos TransactionID <br>8: Ya no se utiliza; Versiones anteriores de los orígenes de datos de Adobe Advertising <br>9: Ya no se utiliza; Métricas de resumen de Adobe Social <br>10: Reenvío del lado del servidor de Audience Manager utilizado

+++

+++**`hit_time_gmt`**

La marca de tiempo de los servidores de recopilación de datos de visitas de Adobe que recibieron la visita, basada en el tiempo UNIX®.

+++

+++**`hourly_visitor`**

Un indicador que determina si la visita es un visitante nuevo por hora.

+++

+++**`ip`**

La dirección IPv4, basada en el encabezado HTTP de la solicitud de imagen. Exclusivo de forma mutua para `ipv6`; si esta columna contiene una dirección IP no oculta, `ipv6` está en blanco.

+++

+++**`ipv6`**

La dirección IPv6 comprimida, si está disponible. Exclusivo de forma mutua para `ip`; si esta columna contiene una dirección IP no oculta, `ip` está en blanco.

+++

+++**`javascript`**

ID de búsqueda de la versión de JavaScript basado en `j_jscript`. Se remite a la tabla de búsqueda `javascript_version`.

+++

+++**`java_enabled`**

La dimensión Java habilitado. <br>S: Habilitado<br>N: No habilitado<br>D: Desconocido

{{cja-df-post}}

+++

+++**`j_jscript`**

Versión de JavaScript admitida por el explorador.

+++

+++**`language`**

ID numérico que representa el idioma del visitante. Se remite a la tabla de búsqueda `languages.tsv`.

+++

+++**`last_hit_time_gmt`**

Marca de tiempo (en tiempo UNIX®) de la visita anterior. Se utiliza para calcular la dimensión Días desde la última visita.

+++

+++**`last_purchase_num`**

La dimensión Lealtad del cliente. Indica la cantidad de compras anteriores que realizó el visitante. <br>0: Sin compras previas (no es un cliente) <br>1: Una compra anterior (nuevo cliente) <br>2: Dos compras anteriores (cliente de devolución) <br>3: Tres o más compras anteriores (cliente fiel)

+++

+++**`last_purchase_time_gmt`**

Se utiliza en la dimensión Días desde la última compra. Marca de tiempo (en tiempo UNIX®) de la última compra realizada. Para la primera compra y para los visitantes que no hayan realizado ninguna compra anteriormente, este valor es `0`.

+++

+++**`latlon1`**

Ubicación (menos de 10 km)

+++

+++**`latlon23`**

Ubicación (menos de 100 m)

+++

+++**`latlon45`**

Ubicación (menos de 1 m)

+++

+++**`mcvisid`**

ID de visitante de Experience Cloud. Número de 128 bits formado por dos números concatenados de 64 bits con relleno hasta 19 dígitos.

+++

+++**`mc_audiences`**

Lista de ID de segmento de Audience Manager a los que pertenece el visitante. La columna `post_mc_audiences` cambia el delimitador a `--**--`.

{{cja-df-post}}

+++

+++**`mobileaction`**

Acción móvil. Se recopila automáticamente cuando se llama a `trackAction` en implementaciones móviles. Permite establecer automáticamente las rutas de acción en la aplicación.

{{cja-df-post}}

+++

+++**`mobileappid`**

ID de la aplicación móvil. Almacena el nombre y la versión de la aplicación en el siguiente formato: `[AppName] [BundleVersion]`. 

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

Se utiliza en el conector de datos Apteligent. El ID de la aplicación utilizado en Apteligent.

+++

+++**`mobileappperformancecrashid`**

Se utiliza en el conector de datos Apteligent. ID de bloqueo utilizado en Apteligent.

+++

+++**`mobileappstoreobjectid`**

Se utiliza en el conector de datos [!DNL Appfigures]. ID de objeto de App Store.

+++

+++**`mobilebeaconmajor`**

Señalización principal de Mobile Services

+++

+++**`mobilebeaconminor`**

Señalización menor de Mobile Services

+++

+++**`mobilebeaconproximity`**

Proximidad de la señalización de Mobile Services

+++

+++**`mobilebeaconuuid`**

UUID de señalización de Mobile Services

+++

+++**`mobilecampaigncontent`**

Nombre o ID del contenido que muestra el vínculo. Rellenado por Adquisición de aplicación móvil.

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

Medio de marketing, como banner o correo electrónico. Rellenado por Adquisición de aplicación móvil.

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

Nombre de la campaña, también almacenada en la variable de campaña. Rellenado por Adquisición de aplicación móvil.

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

Referente original, como newsletter o red de medios sociales. Rellenado por Adquisición de aplicación móvil.

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

Palabras clave pagas u otros términos que desee rastrear con esta adquisición. Rellenado por Adquisición de aplicación móvil.

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

Número del día de la semana en que se abrió la aplicación.

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

Cantidad de días desde que la aplicación se ejecutó por primera vez.

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

Cantidad de días desde que la aplicación se ejecutó por última vez.

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

Recopilado desde la variable de datos de contexto `a.deeplink.id`. Se utiliza en los informes de adquisición como identificador para el vínculo de adquisición móvil.

+++

+++**`mobiledevice`**

Nombre del dispositivo móvil. En iOS, se almacena como una cadena de 2 dígitos separados por comas. El primer número representa la generación del dispositivo y el segundo representa miembros diferentes de la familia del dispositivo.

{{cja-df-post}}

+++

+++**`mobilehourofday`**

Define la hora del día en que se inició la aplicación. Sigue el formato numérico de 24 horas.

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

Fecha de instalación del móvil. Proporciona la fecha de la primera vez que se abre la aplicación móvil.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

Incrementa de uno en uno cada vez que se abre la aplicación móvil.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

Recopilado desde la variable de datos de contexto `a.message.button.id`. Se utiliza para la mensajería integrada en la aplicación con el objetivo de identificar el botón que cerró el mensaje.

{{cja-df-post}}

+++

+++**`mobilemessageid`**

ID de mensaje en la aplicación

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

Mensaje en línea en la aplicación

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

Recopilado desde la variable de datos de contexto `a.push.optin`. Se establece en “true” cuando el usuario opta por la mensajería emergente; de lo contrario, el valor es “false”.

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

Recopilado desde la variable de datos de contexto `a.push.payloadid`. Se utiliza en los mensajes emergentes como identificador de carga útil.

{{cja-df-post}}

+++

+++**`mobileosversion`**

Versión del sistema operativo de Mobile Services

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

Recopilado desde la variable de datos de contexto `a.loc.acc`. Indica la precisión del GPS en metros en el momento de la recogida.

+++

+++**`mobileplacecategory`**

Recopilado desde la variable de datos de contexto `a.loc.category`. Describe la categoría de un lugar específico.

+++

+++**`mobileplaceid`**

Recopilado desde la variable de datos de contexto `a.loc.id`. Identificador de un punto de interés determinado.

+++

+++**`mobilepushoptin`**

Inclusión push de Mobile Services

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

ID de carga útil push de Mobile Services

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Contenido de inicio de Mobile Services

+++

+++**`mobilerelaunchcampaignmedium`**

Medio de inicio de Mobile Services

+++

+++**`mobilerelaunchcampaignsource`**

Origen del inicio de Mobile Services

+++

+++**`mobilerelaunchcampaignterm`**

Término de inicio de Mobile Services

+++

+++**`mobilerelaunchcampaigntrackingcode`**

Recopilado desde la variable de datos de contexto `a.launch.campaign.trackingcode`. Se utiliza en la adquisición como código de seguimiento para la campaña de inicio.

+++

+++**`mobileresolution`**

Resolución del dispositivo móvil. `[Width] x [Height]` en píxeles.

{{cja-df-post}}

+++

+++**`mobile_id`**
Si el usuario utiliza un dispositivo móvil, es el ID numérico del dispositivo. El valor clave de `mobile_attributes.tsv` búsqueda dinámica.

+++

+++**`monthly_visitor`**

Un indicador que determina si el visitante es único en el mes actual.

+++

+++**`mvvar1`** - **`mvvar3`**

Valores de variable de lista. Contiene una lista delimitada de valores personalizados en función de la implementación. Las columnas `post_mvvar1` - `post_mvvar3` reemplazan el delimitador original por `--**--`.

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

Los valores de variable de lista que se establecieron en la visita actual. Reemplaza el delimitador original por `--**--`. Las columnas `post` no suelen contener datos.

{{cja-df-post}}

+++

+++**`new_visit`**

Un indicador que determina si la visita actual es una visita nueva. Configurado por Adobe tras 30 minutos de inactividad de la visita.

+++

+++**`os`**

ID numérico que representa el sistema operativo del visitante. Se basa en la columna`user_agent`. El valor clave de `operating_system.tsv` búsqueda estándar y `operating_system_type.tsv` búsqueda dinámica.

+++

+++**`pagename`**

La dimensión Página. Si la variable `pagename` está vacía, Analytics utiliza `page_url` en su lugar.

{{cja-df-post}}

+++

+++**`pagename_no_url`**

Similar a `pagename`, excepto que no vuelve a `page_url`. Solo la columna `post` está disponible.

{{cja-df-post}}

+++

+++**`page_event`**

El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo personalizado, vínculo de salida). Consulte Búsqueda de eventos de página.

{{cja-df-post}}

+++

+++**`page_event_var1`**

Solo se utiliza en solicitudes de imagen de seguimiento de vínculos. URL del vínculo de descarga, de salida o personalizado en el que se hizo clic.

{{cja-df-post}}

+++

+++**`page_event_var2`**

Solo se utiliza en solicitudes de imagen de seguimiento de vínculos. Nombre personalizado (si se especifica) del vínculo. Establece el vínculo personalizado, el vínculo de descarga o el vínculo de salida en función del valor de `page_event`.

{{cja-df-post}}

+++

+++**`page_type`**

La dimensión Páginas no encontradas, que generalmente se utiliza para 404 páginas.

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**: dirección URL de la visita. Utiliza un tipo de datos de texto.<br>**`post_page_url`**: se eliminó para las solicitudes de imagen de seguimiento de vínculos (`tl()`).

{{cja-df-post}}

+++

+++**`paid_search`**

Un indicador que se determina si la visita coincide con la detección de búsquedas de pago.

+++

+++**`persistent_cookie`**

Se utiliza en la dimensión Compatibilidad con cookies persistentes. Indica si el visitante admite cookies que no se descartan después de cada visita.

{{cja-df-post}}

+++

+++**`pointofinterest`**

Nombre del punto de interés de Mobile Services

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Distancia de Mobile Services al centro de puntos de interés

{{cja-df-post}}

+++

+++**`product_list`**

La variable de página `products`. Ayuda a rellenar varias dimensiones y métricas, incluidas Categoría, Producto, Unidades e Ingresos.

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

Variables de tráfico personalizadas 1-75. Se utiliza en dimensiones Prop.

{{cja-df-post}}

+++

+++**`purchaseid`**

Identificador único de una compra, tal y como se establece mediante la variable `purchaseID`. Lo utiliza la columna `duplicate_purchase`.

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

Un indicador que determina si la visita es un visitante nuevo trimestral.

+++

+++**`referrer`**

La dimensión Referente. Tenga en cuenta que mientras `referrer` utiliza un tipo de datos de varchar(255), `post_referrer` emplea un tipo de datos de varchar(244).

{{cja-df-post}}

+++

+++**`ref_domain`**

La dimensión Dominio de referencia. Se basa en la columna`referrer`.

+++

+++**`ref_type`**


ID numérico que representa el tipo de referente de la visita. Se utiliza en la dimensión Tipo de referente.<br>1: Dentro del sitio<br>2: Otros sitios web<br>3: Motores de búsqueda<br>4: Disco duro<br>5: USENET<br>6: Escritos o marcadores (sin referente)<br>7: Correo electrónico<br>8: Sin JavaScript<br>9: Redes sociales<br>10: Herramientas de IA conversacional

+++

+++**`resolution`**

ID numérico que representa la resolución del monitor. Se utiliza en la dimensión Resolución del monitor. Utiliza la tabla de búsqueda `resolution.tsv`.

+++

+++**`search_engine`**

ID numérico que representa el motor de búsqueda que redirigió al visitante a su sitio. Se utiliza en dimensiones del motor de búsqueda. Se remite a la tabla de búsqueda `search_engines.tsv`.

{{cja-df-post}}

+++

+++**`search_page_num`**

Lo utiliza la dimensión Rango de todas las páginas de búsqueda. Indica en qué página de resultados de búsqueda apareció su sitio antes de que se hiciera clic para acceder a él.

+++

+++**`secondary_hit`**

Un indicador que determina si la visita es una visita secundaria. Por lo general, este indicador se origina a partir del etiquetado de grupos múltiples y las reglas de VISTA que copian las visitas.

+++

+++**`sourceid`**

ID de origen

+++

+++**`stats_server`**

Sin uso. Servidor interno de Adobe que ha procesado la visita.

+++

+++**`s_kwcid`**

ID de palabra clave utilizado en las integraciones de Adobe Advertising.

{{cja-df-post}}

+++

+++**`s_resolution`**

Valor no procesado de resolución de pantalla. Se recopila mediante la función de JavaScript `screen.width x screen.height`.

+++

+++**`tnt`**

Se utiliza en las integraciones de Adobe Target. Representa todas las pruebas para las que está cualificado actualmente. El formato es: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`.

{{cja-df-post}}

+++

+++**`tnt_action`**

Se utiliza en las integraciones de Adobe Target. Representa todas las pruebas para las que se calificó la visita.

{{cja-df-post}}

+++

+++**`tnt_instances`**

Se utiliza en las integraciones de Adobe Target. Variable de instancias de Target.

+++

+++**`transactionid`**

Un identificador único donde, más tarde, se pueden cargar diversos puntos de datos a través de fuentes de datos. Recopilado mediante la variable `transactionID`.

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

Un indicador que indica que se truncó la solicitud de imagen (se recibió una visita parcial). <br>S: Se truncó la visita; visita parcial recibida <br>N: La visita no se truncó; visita completa recibida

+++

+++**`t_time_info`**

Hora local del visitante. El formato es: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

Sin uso. ID numérico del ID del grupo de informes. Utilice `username` en su lugar.

+++

+++**`username`**

ID del grupo de informes para la visita.

+++

+++**`user_agent`**

La cadena del agente de usuario enviada en el encabezado HTTP de la solicitud de imagen.

+++

+++**`user_hash`**

Sin uso. Hash en el ID del grupo de informes. Utilice `username` en su lugar.

+++

+++**`user_server`**

Se utiliza en la dimensión Servidor.

{{cja-df-post}}

+++

+++**`va_closer_detail`**

La dimensión Detalle del último contacto.

+++

+++**`va_closer_id`**

ID numérico que identifica la dimensión Canal del último contacto. La búsqueda de este ID se encuentra en el administrador de canales de marketing.

+++

+++**`va_finder_detail`**

La dimensión Detalle del primer contacto.

+++

+++**`va_finder_id`**

ID numérico que identifica la dimensión Canal del primer contacto. La búsqueda de este ID se encuentra en el administrador de canales de marketing.

+++

+++**`va_instance_event`**

Un indicador que identifica las instancias del canal de marketing.

+++

+++**`va_new_engagement`**

Un indicador que identifica las nuevas participaciones en el canal de marketing.

+++

+++**`video`**

La dimensión Servicios de medios de streaming de contenido.

{{cja-df-post}}

+++

+++**`videoad`**

La dimensión Servicios de medios de streaming de publicidad.

{{cja-df-post}}

+++

+++**`videoadinpod`**

La dimensión Servicios de medios de streaming de la posición del anuncio en el pod.

{{cja-df-post}}

+++

+++**`videoadlength`**

La dimensión Duración de la publicidad (variable) de los servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videoadname`**

La dimensión Nombre del anuncio (variable) de los servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videoadplayername`**

La dimensión Servicios de medios de streaming del nombre del reproductor de publicidad.

{{cja-df-post}}

+++

+++**`videoadpod`**

La dimensión Servicios de medios de streaming de pod de anuncios.

{{cja-df-post}}

+++

+++**`videoadvertiser`**

La dimensión Servicios de medios de streaming del anunciante.

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

La dimensión Servicios de medios de streaming de álbum.

+++

+++**`videoaudioartist`**

La dimensión Servicios de medios de streaming de artista.

+++

+++**`videoaudioauthor`**

La dimensión Servicios de medios de streaming de autor.

+++

+++**`videoaudiolabel`**

La dimensión Servicios de medios de streaming de etiqueta.

+++

+++**`videoaudiopublisher`**

La dimensión Servicios de medios de streaming de Publisher.

+++

+++**`videoaudiostation`**

La dimensión Servicios de medios de streaming de Station.

+++

+++**`videocampaign`**

La dimensión Servicios de medios de streaming del ID de campaña.

{{cja-df-post}}

+++

+++**`videochannel`**

La dimensión Servicios de medios de streaming del canal de contenido.

{{cja-df-post}}

+++

+++**`videochapter`**

La dimensión Servicios de medios de streaming de capítulo.

{{cja-df-post}}

+++

+++**`videocontenttype`**

La dimensión Tipo de contenido de los servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videodaypart`**

La dimensión Servicios de medios de streaming de la parte Día.

{{cja-df-post}}

+++

+++**`videoepisode`**

La dimensión Servicios de medios de streaming de episodio.

{{cja-df-post}}

+++

+++**`videofeedtype`**

La dimensión Servicios de medios de streaming de tipo de fuente de medios.

{{cja-df-post}}

+++

+++**`videogenre`**

La dimensión Servicios de medios de streaming de género. Esta dimensión permite varios valores en la misma visita, delimitados por una coma.

{{cja-df-post}}

+++

+++**`videolength`**

La dimensión Longitud del contenido (variable) de los servicios de medios de transmisión.

{{cja-df-post}}

+++

+++**`videomvpd`**

La dimensión Servicios de medios de streaming de MVPD.

{{cja-df-post}}

+++

+++**`videoname`**

La dimensión Nombre del contenido (variable) de los servicios de medios de transmisión.

{{cja-df-post}}

+++

+++**`videonetwork`**

La dimensión Servicios de medios de streaming de red.

{{cja-df-post}}

+++

+++**`videopath`**

La dimensión Ruta de medios de los servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videoplayername`**

La dimensión Nombre del reproductor de contenido: Servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

La dimensión Velocidad de bits promedio de los servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

La velocidad de bits cambia la dimensión de servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

La dimensión Servicios de medios de streaming de eventos de búfer.

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

La dimensión Duración total del búfer de los servicios de medios de transmisión.

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

La dimensión Servicios de medios de streaming de fotogramas perdidos.

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

La dimensión Errores en los servicios de medios de streaming.

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

La dimensión ID de error externo de servicios de medios de streaming. Esta dimensión permite varios valores en la misma visita.

+++

+++**`videoqoeplayersdkerrors`**

La dimensión Servicios de medios de streaming de ID de error del reproductor de SDK. Esta dimensión permite varios valores en la misma visita.

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

La dimensión Tiempo para el inicio de los servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videoseason`**

La dimensión Servicios de medios de streaming de temporada.

{{cja-df-post}}

+++

+++**`videosegment`**

La dimensión Servicios de medios de streaming del segmento de contenido.

{{cja-df-post}}

+++

+++**`videosessionid`**

La dimensión Servicios de medios de streaming de ID de sesión de medios.

{{cja-df-post}}

+++

+++**`videoshow`**

La dimensión Servicios de medios de streaming.

{{cja-df-post}}

+++

+++**`videoshowtype`**

La dimensión Servicios de medios de streaming de tipo Mostrar.

{{cja-df-post}}

+++

+++**`videostreamtype`**

La dimensión Servicios de medios de streaming de tipo de emisión.

+++

+++**`visid_high`**

Se utiliza con `visid_low` para identificar un visitante de forma exclusiva.

{{cja-df-post}}

+++

+++**`visid_low`**

Se utiliza con `visid_high` para identificar un visitante de forma exclusiva.

{{cja-df-post}}

+++

+++**`visid_new`**

Un indicador que determina si la visita contiene un ID de visitante recién generado.

+++

+++**`visid_timestamp`**

Si el ID de visitante se ha generado recientemente, proporciona la marca de tiempo en tiempo UNIX® del momento en que se generó el ID de visitante.

+++

+++**`visid_type`**

No para uso externo; Adobe lo utiliza internamente para procesar optimizaciones. ID numérico que representa el método utilizado para identificar al visitante.<br>`0`: ID de visitante personalizado o desconocido/no aplicable<br>`1`: IP y reserva del agente de usuario <br>`2`: encabezado de suscriptor móvil HTTP <br>`3`: valor de la cookie heredada (`s_vi`) <br>`4`: valor de la cookie de reserva (`s_fid`) <br>`5`: servicio de identidad

{{cja-df-post}}

+++

+++**`visit_keywords`**

La dimensión Palabra clave de búsqueda. Esta columna utiliza un límite de caracteres no estándar de varchar(244) para dar cabida a la lógica back-end que utiliza Adobe. La columna posprocesada es `**post_keywords**`, no `**post_visit_keywords**`.

{{cja-df-post}}

+++

+++**`visit_num`**

La dimensión Número de visita. Empieza en 1 y aumenta cada vez que se inicia una nueva visita por visitante.

+++

+++**`visit_page_num`**

La dimensión Profundidad de la visita. Aumenta en 1 por cada visita que genera el visitante. Restablece cada visita.

+++

+++**`visit_referrer`**

El primer referente de la visita.

+++

+++**`visit_ref_domain`**

Se basa en la columna `visit_referrer`. El primer dominio de referencia de la visita.

+++

+++**`visit_ref_type`**

ID numérico que representa el tipo de referente del primer referente de la visita. Se remite a la tabla de búsqueda `referrer_type.tsv`.

+++

+++**`visit_search_engine`**

ID numérico que representa el primer motor de búsqueda de la visita. Se remite a la tabla de búsqueda `search_engines.tsv`.

+++

+++**`visit_start_pagename`**

Página de la primera visita individual de la visita.

+++

+++**`visit_start_page_url`**

URL de la primera visita individual de la visita.

+++

+++**`visit_start_time_gmt`**

Marca de tiempo (en tiempo UNIX®) de la primera visita.

+++

+++**`weekly_visitor`**

Indicador que determina si la visita es un visitante nuevo semanal.

+++

+++**`yearly_visitor`**

Indicador que determina si la visita es un visitante nuevo anual.

+++

+++**`zip`**

Ayuda a rellenar la dimensión Código postal. Consulte también `geo_zip`.

{{cja-df-post}}

+++
