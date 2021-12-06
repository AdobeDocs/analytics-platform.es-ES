---
title: Agregar búsquedas estándar a sus conjuntos de datos
description: Utilice búsquedas estándar para aumentar los informes con dimensiones útiles en el Customer Journey Analytics.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
source-git-commit: 067502a0d69bd0b085ecb5e6cbd3ae062f33daef
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 28%

---

# Agregar búsquedas estándar a sus conjuntos de datos

>[!IMPORTANT]
>Las búsquedas estándar solo están disponibles para fuentes de datos de conectores de datos de Analytics en CJA. Solo se pueden usar si se usa la variable [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) o las API de recopilación de datos del Experience Platform.

Las búsquedas estándar (también conocidas como búsquedas suministradas por Adobe) mejoran la capacidad del Customer Journey Analytics para informar sobre algunas dimensiones/atributos que no son útiles por sí mismos pero que son útiles cuando se unen con otros datos. Algunos ejemplos son los atributos de dispositivos móviles y los atributos de dimensiones del sistema operativo y del explorador, como, por ejemplo, los números de versión del explorador. Una &quot;búsqueda estándar&quot; es similar a un conjunto de datos de búsqueda. Las búsquedas estándar son aplicables en todas las organizaciones de Experience Cloud. Se aplican automáticamente a todos los conjuntos de datos de evento que contienen determinados campos de esquema XDM (consulte la información sobre campos específicos a continuación). Existe un conjunto de datos de consulta estándar para cada ubicación de esquema que clasifica el Adobe.

En Adobe Analytics tradicional, estas dimensiones aparecen por sí solas, mientras que en CJA hay que incluir activamente estas dimensiones al crear las vistas de datos. En el flujo de trabajo Conexiones , seleccione un conjunto de datos que esté marcado como uno con una clave para la búsqueda estándar. La interfaz de usuario de vistas de datos sabe automáticamente que debe incluir todas las dimensiones de búsqueda estándar que estén disponibles para los informes. Los archivos de búsqueda se mantienen actualizados automáticamente y están disponibles en todas las regiones y todas las cuentas. Se almacenan en organizaciones específicas de la región asociadas con el cliente.

## Uso de búsquedas estándar con conjuntos de datos del conector de datos de Adobe

Los conjuntos de datos de búsqueda estándar se aplican automáticamente en el momento del informe. Si utiliza el conector de datos de Analytics y añade una dimensión para la que el Adobe proporciona una búsqueda estándar, aplicamos automáticamente esta búsqueda estándar. Si un conjunto de datos de evento contiene campos XDM, podemos aplicarle búsquedas estándar.

### Campos de búsqueda estándar disponibles

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
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

## Informe sobre dimensiones de búsqueda estándar

Para informar sobre las dimensiones de búsqueda estándar, debe agregarlas al crear una vista de datos en Customer Journey Analytics:

![](assets/global-lookup.png)

A continuación, podrá ver los datos de búsqueda en Workspace:

![](assets/gl-reporting.png)
