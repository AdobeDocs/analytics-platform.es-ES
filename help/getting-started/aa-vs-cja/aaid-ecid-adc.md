---
title: AAID, ECID, AACUSTOMID y el conector de origen de Analytics
description: Descubra cómo el conector de origen de Analytics trata los campos de identidad de Adobe Analytics.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
source-git-commit: 20ebfb36e769f7d683ad44ec84b11aafb301a737
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 9%

---

# AAID, ECID, AACUSTOMID y el conector de origen de Analytics

Los datos de Adobe Analytics contienen varios campos de identidad. Tres campos de identidad importantes reciben un trato especial por parte de la [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es): AAID, ECID, AACUSTOMID.

## AAID

Adobe Analytics ID (AAID) es el identificador de dispositivo principal de Adobe Analytics y se garantiza que existe en todos los eventos que se pasan a través del conector de origen de Analytics. A veces, AAID se denomina &quot;ID de Analytics heredado&quot; o `s_vi` id de cookie. Sin embargo, se crea un AAID incluso si la variable `s_vi` no está presente. AAID se representa mediante la variable `post_visid_high/post_visid_low` columnas de [Fuentes de datos de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es#columns%2C-descriptions%2C-and-data-types).

En el conector de origen de Analytics, AAID se transforma en `HEX(post_visid_high) + "-" + HEX(post_visid_low)`. El campo AAID de un evento determinado contiene una sola identidad que puede ser de varios tipos diferentes según se describe en [Orden de operaciones para los ID de Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Dentro de un grupo de informes completo, AAID puede contener una combinación de tipos entre eventos. El tipo de cada visita se indica en la variable `post _visid_type` en las fuentes de datos de Analytics). Consulte también: [Referencia de columnas de datos](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es).

## ECID

ECID (ID de Experience Cloud), también conocido como MCID (ID de Marketing Cloud), es un campo de identificador de dispositivo independiente que se rellena en Adobe Analytics cuando Analytics se implementa mediante la [Servicio de identidad de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=es). ECID se representa mediante la variable `mcvisid` en las fuentes de datos de Adobe Analytics.

Si existe un ECID en un evento, el AAID puede basarse en el ECID en función de si Analytics [período de gracia](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=es) está configurado. Consulte también: [Solicitudes de ID de Experience Cloud y Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUSTOMID

AACUSTOMID es un campo de identificador independiente que se rellena en Adobe Analytics según el uso de la variable `s.VisitorID` en la implementación de Analytics. AACUSTOMID se representa mediante la variable `cust_visid` en las fuentes de datos de Adobe Analytics. Si AACUSTOMID está presente, AAID se basará en AACUSTOMID. (AACUSTOMID supera todos los demás identificadores según el orden de operaciones mencionado anteriormente).

## Cómo trata el conector de origen de Analytics estas identidades

El conector de origen de Analytics pasa estas identidades a Adobe Experience Platform en forma XDM de la siguiente manera:

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

Estos campos no están marcados como identidades. En cambio, las mismas identidades se copian en el **_identityMap_** como pares de valor clave de la siguiente manera:

* `{ “key”: “AAID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “<identity>”, “primary”: false } ] }`

Los elementos entre corchetes

Dentro de identityMap:

* Si ECID está presente, se marca como la identidad principal del evento. Tenga en cuenta que, en este caso, AAID puede basarse en ECID según el análisis anterior.
De lo contrario, AAID se marca como la identidad principal del evento.
* AACUSTOMID nunca se marca como ID principal para el evento. Sin embargo, si AACUSTOMID está presente, AAID se basa en AACUSTOMID según la conversación anterior.

En lo que respecta a CJA, la definición de ID principal solo es importante si el usuario final decide utilizar el ID principal como ID de persona. Sin embargo, hacerlo no es obligatorio. El usuario puede elegir otra columna de identidad como ID de persona.
