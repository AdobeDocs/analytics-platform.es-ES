---
title: Añadir búsquedas globales a sus conjuntos de datos
description: Utilice búsquedas globales para aumentar el sistema de informes con dimensiones útiles en Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: b3c9757421537d2d84a78a4d37e9bfc362438d40
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---


# Añadir búsquedas globales a sus conjuntos de datos

Las búsquedas globales mejoran la capacidad del Customer Journey Analytics para informar sobre algunas dimensiones o atributos que no son útiles por sí mismos pero que son útiles cuando se unen con otros datos. Algunos ejemplos son los atributos de dispositivos móviles y los atributos de dimensiones del sistema operativo y del explorador, como los números de versión del explorador. Una búsqueda global es muy similar a un conjunto de datos de búsqueda (conocido como clasificaciones en Adobe Analytics tradicional). Sin embargo, las búsquedas globales son aplicables en todas las organizaciones Experience Cloud. Las búsquedas globales se aplican automáticamente a todos los conjuntos de datos de evento que contienen determinados campos de esquema XDM (vea a continuación los campos específicos).
Para cada ubicación de esquema que clasifica el Adobe, existe un conjunto de datos de búsqueda global. Puede utilizar conjuntos de datos de búsqueda globales con el conector de origen de Analytics o con otros conjuntos de datos personalizados que puedan aceptarlos.

En Adobe Analytics tradicional, estas dimensiones aparecen por sí solas, mientras que en CJA hay que incluir activamente estas dimensiones al crear vistas de datos. Cuando un usuario, en el flujo de trabajo Conexiones, selecciona un conjunto de datos marcado como uno con una clave para búsquedas globales, la interfaz de usuario de vistas de datos sabe que incluye todas las dimensiones de búsqueda global como disponibles para sistema de informes. El flujo de trabajo de vistas de datos sabe que incluye estas dimensiones de búsqueda global como disponibles para la vista de datos. Los archivos de búsqueda se mantienen actualizados automáticamente y están disponibles en todas las regiones y en todas las cuentas. Se almacenan en organizaciones específicas de la región asociadas con el cliente.

## Usar búsquedas globales con conjuntos de datos del conector de datos de Adobe

Los conjuntos de datos de búsqueda global se aplican automáticamente en el momento del informe. Si está utilizando el [Conector de datos de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#connectors) y trae una dimensión para la que Adobe proporciona una búsqueda global, se aplicará automáticamente esta búsqueda global. Si un conjunto de datos de evento contiene [campos XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en), podemos aplicarle búsquedas globales.

## Usar búsquedas globales con conjuntos de datos personalizados

Debe haber una clave en el conjunto de datos de evento que sea compatible con los conjuntos de datos de búsqueda globales. Siempre que complete los campos XDM adecuados agregando algunas de las [mezclas de esquema de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/xdm/mixins/event/environment-details.html?lang=en#mixins) estándar, puede hacer que los conjuntos de datos personalizados funcionen con búsquedas globales.

## Campos de búsqueda globales disponibles

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`,  `group_id`,  `id`
* `os_group`
   * `os_group`,  `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## Informe sobre dimensiones de búsqueda global

Para informar sobre las dimensiones de búsqueda global, debe agregarlas al crear una vista de datos en Customer Journey Analytics:

![](assets/global-lookup.png)

A continuación, puede ver los datos de búsqueda en Workspace:

![](assets/gl-reporting.png)

