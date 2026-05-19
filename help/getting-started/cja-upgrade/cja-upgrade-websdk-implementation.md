---
title: Información sobre las opciones de implementación del SDK web al actualizar a Customer Journey Analytics
description: Obtenga información sobre las opciones de implementación del SDK web al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
autotag-review: '2026-05-19T08:21:32.040Z'
TQID: 'https://experienceleague.adobe.com/5mjQHmjaBfxAusSR3EuDykYxJzgaR6P9jiL3HH09Bns'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 100%

---

# Información sobre las opciones de implementación del SDK web al actualizar a Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Biblioteca JavaScript del SDK web (alloy.js)"
>abstract="Incluya la biblioteca del SDK web (alloy.js) en todas las páginas del sitio."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Extensión de etiquetas del SDK web"
>abstract="(Recomendado) Si aún no utiliza etiquetas, instale el cargador de etiquetas en su sitio. Si ya está utilizando etiquetas, puede añadir la extensión del SDK web a la propiedad de su etiqueta. Esta opción incluye implementaciones que utilizan etiquetas en la recopilación de datos de Adobe Experience Platform y sistemas de administración de etiquetas de terceros."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="Paquete NPM"
>abstract="Utilice la API de recopilación de datos para enviar datos directamente a una secuencia de datos. Se admiten los tipos no autenticados (cliente a servidor) y autenticados (servidor a servidor)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="Implementar el SDK web para una propiedad determinada"
>abstract="Seleccione el tipo de implementación deseado en la guía de actualización para obtener instrucciones más detalladas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Añadir la biblioteca del SDK web al sistema de administración de etiquetas de terceros"
>abstract="Trabaje con el administrador sobre el sistema de administración de etiquetas para añadir la biblioteca del SDK web al sitio.<br><br>El tiempo de finalización de esta tarea depende en gran medida de la capacidad de respuesta de la persona responsable de su sistema de administración de etiquetas. La adición de la biblioteca del SDK web puede incluirse con la lógica de implementación asociada e implementarse durante los ciclos de lanzamiento estándar de su organización."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

El proceso recomendado para actualizar de Adobe Analytics a Customer Journey Analytics es una nueva implementación del SDK web de Experience Platform, que es el método de recopilación de datos preferido para Customer Journey Analytics.

Existen tres formas compatibles de utilizar el SDK web de Adobe Experience Platform:

* [Extensión de etiquetas del SDK web](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/install/extension): Adobe recomienda utilizar este método. Instale un cargador de etiquetas en su sitio y, a continuación, utilice la IU de recopilación de datos de Adobe Experience Platform para configurar la implementación.

* [Biblioteca JavaScript del SKD web](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/install/library): haga referencia a un archivo de biblioteca alojado en CDN o aloje el archivo de biblioteca utilizando su propia infraestructura. Realice llamadas a la biblioteca dentro del código del sitio.

* [NPM](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/install/npm): instale el SDK web en su sitio mediante el administrador de paquetes NPM.

Para obtener más información, consulte [Información general sobre la instalación del SDK web](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/install/overview) en la Guía del SDK web de Experience Platform.
