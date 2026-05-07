---
title: Configuración de Content Analytics
description: Información general sobre cómo configurar Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: beb2e35354d3da1fe6d22f4221e30ff0ccde3138
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 77%

---

# Configuración de Content Analytics

Este artículo describe, en un nivel superior, cómo configurar Content Analytics.

Antes de configurar Content Analytics, debe asegurarse de que se cumplan [los requisitos previos](#prerequisites), de que dispone del [control de acceso](#access-control) necesario y de que conoce las [limitaciones](#limitations).


Pasos de alto nivel

![Configuración de Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Utilice la [configuración guiada](guided.md) del asistente de análisis de contenido para guiarle por todos los pasos necesarios para establecer los requisitos previos de una configuración de Content Analytics. Puede guardar las configuraciones en cualquier momento y volver más tarde.
1. Una vez que se sienta cómodo con los valores de configuración, puede implementar la configuración. Esta implementación crea todos los artefactos necesarios en función de lo que haya configurado en el asistente.
1. Solo cuando [publica manualmente](manual.md), la propiedad Etiquetas es la configuración de Content Analytics que se implementó de manera efectiva y se inició la recopilación de datos.

1. Solo puede realizar algunos cambios menores en una configuración implementada mediante el asistente de [configuración guiada](guided.md). Por ejemplo, cambie la [vista de datos](/help/data-views/data-views.md).
1. Puede realizar otros cambios en una configuración implementada mediante la extensión de Adobe Content Analytics en la propiedad Tags asociada para [web](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview) o [mobile](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).
1. Las modificaciones de configuración se implementan de forma eficaz y la recopilación de datos se inicia solo cuando se vuelve a publicar manualmente la propiedad Tags.


## Requisitos previos

Antes de configurar Content Analytics, asegúrese de que se cumplen los siguientes requisitos previos:

### Web

* Ha incluido en la lista de permitidos el agente de usuario y la dirección IP para el servicio de caracterización que se utiliza en Content Analytics. La cadena del agente de usuario que se va a configurar es: <code>AdobeFeaturization/1.0</code>.
* Si ha implementado [Web SDK mediante JavaScript](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/install/library){target="_blank"} para la recopilación de datos de comportamiento normal, asegúrese de que está utilizando el nombre predeterminado <code>alloy</code> Actualice la biblioteca de JavaScript.
* Tiene una función de administrador de productos de Customer Journey Analytics, con los permisos adicionales para administrar conexiones y para administrar vistas de datos.
* Si decide recopilar experiencias de Content Analytics, asegúrese de configurar y actualizar el control de versiones de Content Analytics en función de los cambios realizados en las páginas web.
* Debe tener [permisos para la recopilación de datos](https://experienceleague.adobe.com/es/docs/experience-platform/collection/permissions){target="_blank"}:
   * Permisos de [Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}.
   * Permisos de [Experience Platform Data Collection](https://experienceleague.adobe.com/es/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}.
* Ha considerado detenidamente las siguientes opciones de configuración importantes:

   * Su sitio es adecuado para el sistema de informes de experiencias. Un informe de experiencia adecuado solo es posible cuando se cumplen las siguientes condiciones:
      * Las páginas del sitio deben poder reproducirse utilizando la dirección URL de la página.
      * El contenido de texto que vea un usuario determinado se puede reproducir mediante la dirección URL de la página y no depende de las cookies u otros mecanismos de personalización.
   * Tiene una comprensión clara de qué páginas desea capturar para el análisis y las perspectivas de participación de contenido.
   * Tiene una idea clara de para qué (tipo de) recursos desea capturar el análisis y la información de participación en el contenido.

### Móvil

* Asegúrese de que las extensiones [Experience Platform Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) y [Experience Platform Identity for Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) estén habilitadas para la aplicación móvil.
* Tiene una función de administrador de productos de Customer Journey Analytics, con los permisos adicionales para administrar conexiones y para administrar vistas de datos.
* Debe tener [permisos para la recopilación de datos](https://experienceleague.adobe.com/es/docs/experience-platform/collection/permissions){target="_blank"}:
   * Permisos de [Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}.
   * Permisos de [Experience Platform Data Collection](https://experienceleague.adobe.com/es/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}.



## Control de acceso

>[!IMPORTANT]
>
>No hay permisos de Content Analytics que se puedan configurar para habilitar o deshabilitar el acceso de Content Analytics para usuarios individuales o grupos de usuarios.
>

Para que un usuario o grupo de usuarios tenga acceso a Content Analytics, debe proporcionarle acceso a una o más [vistas de datos configuradas para Content Analytics](guided.md#data-view).

Este acceso implica:

1. La vista de datos habilitada para Content Analytics se incluye como parte de los permisos de vista de datos para un perfil de producto de Customer Journey Analytics específico.
1. Ese perfil de producto de Customer Journey Analytics específico es uno de los perfiles de producto asignados al usuario o grupo de usuarios.

## Limitaciones

El esquema utilizado para los datos de evento de Content Analytics es propiedad del sistema. No se puede modificar un esquema propiedad del sistema, lo que implica lo siguiente:

* No se pueden incluir grupos de campos para admitir funcionalidades como la geolocalización, la detección de bots o la búsqueda de dispositivos.
* No puede añadir un identificador específico para admitir la [vinculación basada en el campo](/help/stitching/fbs.md).

>[!MORELIKETHIS]
>
>* [Configuración guiada](guided.md)
>* [Configuración manual](manual.md)
>* [Control de acceso](/help/technotes/access-control.md)
>
