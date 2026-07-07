---
title: Asignación de columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics
description: Determine cómo tomar una columna de fuente de datos de Adobe Analytics determinada y determine su equivalente aproximado en la implementación de Customer Journey Analytics.
feature: Components
hide: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
autotag-review: '2026-05-19T09:53:49.596Z'
TQID: 'https://experienceleague.adobe.com/Yt2CmGRpO6s8natf9s-KLsMBKHc-qdSQHvi3UyPyLgg'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ae3aff40-b2f6-4df1-8c01-0b0720d1510fid: b3197353-f189-4932-8378-3f3bc40e6071id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5eid: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 66a8a96da6710d20b01b9315fe87ba38c54c2511
workflow-type: tm+mt
source-wordcount: 3920
ht-degree: 48%

---

# Asignación de columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics

{{release-limited-testing}}

No es posible realizar una asignación de true 1:1 entre columnas de fuentes de datos de Adobe Analytics y Customer Journey Analytics. Los dos productos difieren fundamentalmente y la implementación de cada organización puede variar significativamente.

Esta referencia ayuda a los ingenieros de datos a evaluar las columnas de fuentes de datos de Adobe Analytics e identificar los equivalentes de Customer Journey Analytics más cercanos para sus flujos de trabajo.

>[!NOTE]
>
>Esta referencia solo incluye columnas que Adobe considera actuales, según la [referencia de columna de fuente de datos de Analytics](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). Si tiene una columna de fuente de datos de Analytics que no aparece en esta tabla y que utiliza de forma activa, consulte el documento de diseño de soluciones de su organización para determinar su mejor equivalente en Customer Journey Analytics.

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

Un ID numérico que representa el explorador.

{{cja-df-lookup}}

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

Especifica el operador de telefonía móvil.

{{cja-df-lookup}}

{{cja-df-ua}}

+++

+++**`channel`**

La dimensión Secciones del sitio.

{{cja-df-post}}

+++

+++**`ch_hdr`**

Sugerencias del cliente recopiladas mediante el encabezado de petición HTTP.

En Adobe Analytics, las sugerencias del cliente se incluían como una cadena concatenada en esta columna. Se considera un enfoque más moderno que la columna `user_agent`.

{{cja-df-ua}}

+++

+++**`ch_js`**

Sugerencias del cliente recopiladas mediante la API de JavaScript de sugerencias del cliente agente de usuario.

En Adobe Analytics, las sugerencias del cliente se incluían como una cadena concatenada en esta columna. Se considera un enfoque más moderno que la columna `user_agent`.

Puede recopilar estos datos mediante la cadena de contexto [`highEntropyUserAgentHints`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context) al configurar Web SDK. Se rellenan varios campos XDM en lugar de una cadena concatenada larga:

* **Versión del sistema operativo**: `xdm.environment.browserDetails.userAgentClientHints.platformVersion`
* **Arquitectura**: `xdm.environment.browserDetails.userAgentClientHints.architecture`
* **Modelo de dispositivo**: `xdm.environment.browserDetails.userAgentClientHints.model`
* **Bits**: `xdm.environment.browserDetails.userAgentClientHints.bitness`
* **Proveedor del explorador**: `xdm.environment.browserDetails.userAgentClientHints.vendor`
* **Nombre del explorador**: `xdm.environment.browserDetails.userAgentClientHints.brand`
* **Versión del explorador**: `xdm.environment.browserDetails.userAgentClientHints.version`

Consulte [Sugerencias del cliente del agente de usuario](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints) para obtener más información.

{{cja-df-ua}}

+++

+++**`clickmaplink`**

La dimensión Vínculo de Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Esta columna no se aplica porque Customer Journey Analytics aún no admite Activity Map.

+++

+++**`clickmaplinkbyregion`**

La dimensión Vínculo de Activity Map por región.

{{cja-df-post}}

{{cja-df-na}}

Esta columna no se aplica porque Customer Journey Analytics aún no admite Activity Map.

+++

+++**`clickmappage`**

La dimensión Página de Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Esta columna no se aplica porque Customer Journey Analytics aún no admite Activity Map.

+++

+++**`clickmapregion`**

La dimensión Región de Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Esta columna no se aplica porque Customer Journey Analytics aún no admite Activity Map.

+++

+++**`code_ver`**

Versión de la API o del SDK cliente utilizado para compilar y enviar la solicitud de imagen.

+++

+++**`color`**

ID de profundidad de color basada en el valor de la columna `c_color`.

{{cja-df-lookup}}

+++

+++**`connection_type`**

ID numérica que representa la dimensión Tipo de conexión.

{{cja-df-lookup}}

+++

+++**`cookies`**

Dimensión de compatibilidad con cookies.<br>Y: Habilitado<br>N: Deshabilitado<br>U: Desconocido

{{cja-df-post}}

+++

+++**`country`**

Un ID numérico que representa el país del visitante. Se remite a la tabla de búsqueda `country.tsv`.

{{cja-df-lookup}}

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

Determina si la visita fue una visita móvil en segundo plano.

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics no tiene un concepto nativo de tipo de evento en el que incluya o excluya automáticamente las visitas en función del contexto de la visita. Puede usar `xdm.eventType` para determinar qué eventos se deben incluir y excluir en la mayoría de los informes.

+++

+++**`cust_hit_time_gmt`**

Solo grupos de informes con marca de tiempo. La marca de tiempo enviada con la visita y basada en el Tiempo UNIX®.

Customer Journey Analytics no incluye un concepto de grupos de informes con marca de tiempo frente a los que no lo son. Use `xdm.timestamp` en su lugar y ajuste la configuración de componentes como desee.

{{cja-df-post}}

+++

+++**`cust_visid`**

El ID de visitante personalizado, si se establece mediante `visitorID`.

Customer Journey Analytics admite cualquier número de identidades usando [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap). Si su organización utiliza identidades personalizadas, es probable que esto ocurra dentro del mapa de identidad.

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

Si su organización tiene una plataforma de administración de datos, probablemente rellene los campos XDM deseados para esta dimensión.

+++

+++**`dataprivacyconsentoptout`**

La dimensión Exclusión de la administración de consentimiento. Puede haber varios valores por visita, separados por una barra vertical (`\|`). Los valores válidos incluyen `SSF`, `DMP` y `SELL`.

Si su organización tiene una plataforma de administración de datos, probablemente rellene los campos XDM deseados para esta dimensión.

+++

+++**`date_time`**

La hora de la visita en un formato legible, basada en la zona horaria del grupo de informes.

Puede usar `xdm.timestamp` y aplicar la configuración del componente **[!UICONTROL Fecha]** o **[!UICONTROL Fecha-hora]** [Formato](/help/data-views/component-settings/format.md).

+++

+++**`domain`**

La dimensión Dominio. Basado en el punto de acceso a Internet del visitante.

Habilitar **[!UICONTROL búsqueda de red]** al [configurar una secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure). El campo XDM es `xdm.environment.domain` si se incluye en el esquema.

+++

+++**`duplicated_from`**

Solo se utiliza en los grupos de informes que contienen las reglas de VISTA de copia de visita. Indica de qué grupo de informes se copió la visita.

{{cja-df-na}}

Esta columna no se aplica porque Customer Journey Analytics no tiene un concepto de reglas VISTA.

+++

+++**`duplicate_events`**

Enumera cada evento que se contó como duplicado.

{{cja-df-na}}

Customer Journey Analytics no tiene un solo campo que actúe como un indicador de deduplicación para todas las métricas. En su lugar, cada métrica contiene su propia [configuración del componente de anulación de duplicación de métricas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication). Como tal, no hay ningún campo equivalente en Customer Journey Analytics para esta columna de fuente de datos de Adobe Analytics.

+++

+++**`duplicate_purchase`**

Un indicador que determina que el evento de compra de esta visita se ignora porque es un duplicado.

Aunque no hay una traducción directa a esta columna de fuente de datos de Analytics, su funcionalidad de actuar para deduplicar compras sigue existiendo. Si usa el grupo de campos [[!UICONTROL Detalles de Commerce]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details), puede establecer la [configuración del componente de anulación de duplicación de métricas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication) donde **[!UICONTROL ID de anulación de duplicación]** es `xdm.commerce.purchases.id`.

Si se requiere una traducción directa donde desee un indicador para compras duplicadas, puede utilizar un [campo derivado](/help/data-views/derived-fields/derived-fields.md) mediante la función **Deduplicar** en el conjunto de reglas.

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

Si el esquema utiliza el grupo de campos [[!UICONTROL Detalles de Commerce]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details), algunas métricas podrían asignarse directamente a los siguientes campos XDM:

* **Cierres de compra**: `xdm.commerce.checkouts.value`
* **Adiciones al carro de compras**: `xdm.commerce.productListAdds.value`
* **Aperturas del carro de compras**: `xdm.commerce.productListOpens.value`
* **Eliminaciones del carro de compras**: `xdm.commerce.productListRemovals.value`
* **Vistas del carro de compras**: `xdm.commerce.productListViews.value`
* **Vistas del producto**: `xdm.commerce.productViews.value`
* **Pedidos**: `xdm.commerce.purchases.value`

Algunas métricas pueden utilizar la serialización de eventos, que es la forma en que Adobe Analytics permite un control total sobre la deduplicación. Puede usar la configuración del componente [Anulación de duplicación de métricas](/help/data-views/component-settings/metric-deduplication.md) para lograr la paridad de anulación de duplicación.

* Si la métrica se deduplica por visita en Adobe Analytics, puede establecer el ámbito de deduplicación en sesión en la configuración de componentes de esa métrica.
* Si la métrica anula la duplicación por ID de evento en Adobe Analytics, es probable que el objeto XDM de esa métrica contenga un campo `value` y `id`. Si el esquema utiliza el grupo de campos [[!UICONTROL Detalles de Commerce]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details), es probable que esas métricas residan en estos campos XDM, en los que puede establecer el campo **[!UICONTROL ID de anulación de duplicación]** en la configuración de componentes de la métrica:

   * **Cierres de compra**: `xdm.commerce.checkouts.id`
   * **Adiciones al carro de compras**: `xdm.commerce.productListAdds.id`
   * **Aperturas del carro de compras**: `xdm.commerce.productListOpens.id`
   * **Eliminaciones del carro de compras**: `xdm.commerce.productListRemovals.id`
   * **Vistas del carro de compras**: `xdm.commerce.productListViews.id`
   * **Vistas del producto**: `xdm.commerce.productViews.id`

Si desea anular la duplicación de la métrica Pedidos, consulte `duplicate_purchase`.

+++

+++**`exclude_hit`**

Un indicador que determina si la visita se excluye de la creación de informes. La columna `visit_num` no aumenta con las visitas excluidas.

Customer Journey Analytics no acepta &quot;visitas excluidas&quot; de forma predeterminada. Sin embargo, puede volver a crear esta funcionalidad si tiene un campo XDM que marca determinadas visitas que se deben excluir:

1. Asegúrese de que el campo XDM que marca las visitas excluidas se incluye como componente (dimensión o métrica, según cómo tenga configurado este indicador). Seleccionar [Ocultar componente en los informes](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview) es probablemente beneficioso para este campo.
1. En [Configuración de vista de datos](/help/data-views/session-settings.md), seleccione el menú desplegable **[!UICONTROL Agregar segmento]** y seleccione **[!UICONTROL Crear segmento]**.
1. Cree un segmento que excluya todos los eventos en los que el componente Excluir visita existe o contiene valores que desea excluir.
1. Seleccione **[!UICONTROL Guardar]** tanto en el segmento como en la vista de datos.

Las visitas excluidas ahora no existen en los informes de Customer Journey Analytics, pero siguen estando disponibles en las exportaciones de fuentes de datos.

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

Un ID numérico que representa el tipo de referente del primer referente del visitante.

{{cja-df-lookup}}

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

ID de búsqueda de la versión de JavaScript basado en `j_jscript`.

{{cja-df-lookup}}

+++

+++**`java_enabled`**

La dimensión Java habilitado. <br>S: Habilitado<br>N: No habilitado<br>D: Desconocido

{{cja-df-post}}

+++

+++**`j_jscript`**

Versión de JavaScript admitida por el explorador.

+++

+++**`language`**

ID numérico que representa el idioma del visitante.

{{cja-df-lookup}}

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
Si el usuario utiliza un dispositivo móvil, es el ID numérico del dispositivo.

{{cja-df-lookup}}

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

ID numérico que representa el sistema operativo del visitante. Se basa en la columna `user_agent`.

{{cja-df-lookup}}

Al [configurar una secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure), puede habilitar la **[!UICONTROL búsqueda de dispositivos]**. Si está habilitado, marque la casilla de verificación **[!UICONTROL Sistema operativo]**. Al hacerlo, se rellenan automáticamente los siguientes campos XDM si se han incluido estos campos en el esquema:

* **Proveedor de SO**: `xdm.environment.operatingSystemVendor`
* **Nombre del SO**: `xdm.environment.operatingSystem`
* **Versión del SO**: `xdm.environment.operatingSystemVersion`

{{cja-df-ua}}

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

El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo personalizado, vínculo de salida).

{{cja-df-post}}

{{cja-df-lookup}}

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

**`page_url`**: dirección URL de la visita. Utiliza un tipo de datos de texto.<br>**`post_page_url`**: Eliminado para las solicitudes de imagen de seguimiento de vínculos (`tl()`).

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

La dimensión Dominio de referencia. Se basa en la columna `referrer`.

+++

+++**`ref_type`**


ID numérico que representa el tipo de referente de la visita. Se utiliza en la dimensión Tipo de referente.<br>1: Dentro del sitio<br>2: Otros sitios web<br>3: Motores de búsqueda<br>4: Disco duro<br>5: USENET<br>6: Escritos o marcadores (sin referente)<br>7: Correo electrónico<br>8: Sin JavaScript<br>9: Redes sociales<br>10: Herramientas de IA conversacional

+++

+++**`resolution`**

ID numérico que representa la resolución del monitor. Se utiliza en la dimensión Resolución del monitor.

{{cja-df-lookup}}

+++

+++**`search_engine`**

ID numérico que representa el motor de búsqueda que redirigió al visitante a su sitio. Se utiliza en dimensiones del motor de búsqueda.

{{cja-df-post}}

{{cja-df-lookup}}

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

ID numérico que identifica la dimensión Canal del último contacto.

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

La dimensión Detalle del primer contacto.

+++

+++**`va_finder_id`**

ID numérico que identifica la dimensión Canal del primer contacto.

{{cja-df-lookup}}

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

No para uso externo; Adobe lo utiliza internamente para procesar optimizaciones. Identificador numérico que representa el método utilizado para identificar al visitante.<br>`0`: Id. de visitante personalizado o desconocido/no aplicable<br>`1`: IP y reserva del agente de usuario <br>`2`: Encabezado de suscriptor móvil HTTP <br>`3`: Valor de la cookie heredada (`s_vi`) <br>`4`: Valor de la cookie de reserva (`s_fid`) <br>`5`: Servicio de identidad

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

ID numérico que representa el tipo de referente del primer referente de la visita.

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

ID numérico que representa el primer motor de búsqueda de la visita.

{{cja-df-lookup}}

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
