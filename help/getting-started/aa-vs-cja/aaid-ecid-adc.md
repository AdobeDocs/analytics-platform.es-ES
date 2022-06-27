---
source-git-commit: f97439676c61acf1b6ba8818ef1d06542402e675
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 9%

---
# AAID, ECID, AACUSTOMID y el conector de origen de Analytics

Los datos de Adobe Analytics contienen varios campos de identidad. Tres campos de identidad importantes reciben un trato especial por parte de la [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es):

* **AAID** es el identificador de dispositivo principal de Adobe Analytics y se garantiza que exista en todos los eventos pasados a través del conector de origen de Analytics. A veces, AAID se denomina &quot;ID de Analytics heredado&quot; o &quot;id de cookie s\_vi&quot;, aunque se crea un AAID incluso si la cookie s\_vi no está presente. AAID se representa mediante la variable **_post\_visid\_high/post\_visid\_low_** columnas de [Fuentes de datos de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es#columns%2C-descriptions%2C-and-data-types). En el conector de origen de Analytics, AAID se transforma en **HEX(post_visid_high) + &quot;-&quot; + HEX(host_visid_low)**. El campo AAID de un evento determinado contiene una sola identidad que puede ser de varios tipos diferentes, tal como se describe en [Orden de operaciones para los ID de Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Dentro de un grupo de informes completo, AAID puede contener una combinación de tipos entre eventos. El tipo de cada visita se indica en la variable **_[post\_]visid\_type_** en las fuentes de datos de Analytics). Consulte también: [Referencia de columnas de datos](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es).
* **ECID** (ID de Experience Cloud), también denominada a veces MCID (ID de Marketing Cloud), es un campo de identificador de dispositivo independiente que se rellena en Adobe Analytics cuando Adobe Analytics se implementa mediante la variable [Servicio de identidad de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=es). ECID se representa mediante la variable **_mcvisid_** en las fuentes de datos de Adobe Analytics. Si existe un ECID en un evento, el AAID puede basarse en el ECID en función de si Analytics [período de gracia](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=es) está configurado. Consulte también: [Solicitudes de ID de Experience Cloud y Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).
* **AACUSTOMID** es un campo de identificador independiente que se rellena en Adobe Analytics en función del uso de la variable s.VisitorID en la implementación de Analytics. AACUSTOMID se representa mediante la variable **_cust_visid_** en las fuentes de datos de Adobe Analytics. Si AACUSTOMID está presente, AAID se basará en AACUSTOMID. (AACUSTOMID supera todos los demás identificadores según el orden de operaciones mencionado anteriormente).

El conector de origen de Analytics pasa estas identidades a AEP en formato XDM de la siguiente manera:

* endUserIDs.\_experience.aaid.id
* endUserIDs.\_experience.mcid.id
* endUserIDs.\_experience.acustomid.id

Estos campos no están marcados como identidades. En cambio, las mismas identidades se copian en el **_identityMap_** como pares de valor clave de la siguiente manera:

* { &quot;key&quot;: &quot;AAID&quot;, &quot;value&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;principal&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_**} ] }
* { &quot;key&quot;: &quot;ECID&quot;, &quot;valor&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;principal&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_** } ] }
* { &quot;key&quot;: &quot;AACUSTOMID&quot;, &quot;value&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;principal&quot;: **false** } ] }

Dentro de identityMap:

* Si ECID está presente, se marca como la identidad principal del evento. Tenga en cuenta que, en este caso, AAID puede basarse en ECID según el análisis anterior.
De lo contrario, AAID se marca como la identidad principal del evento.
* AACUSTOMID nunca se marca como ID principal para el evento. Sin embargo, si AACUSTOMID está presente, AAID se basa en AACUSTOMID según la conversación anterior.

En lo que respecta a CJA, la definición de ID principal solo es importante si el usuario final decide utilizar el ID principal como ID de persona. Sin embargo, hacerlo no es obligatorio. El usuario puede elegir otra columna de identidad como ID de persona.

