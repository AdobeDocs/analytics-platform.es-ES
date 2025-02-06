---
title: Comprender las opciones de implementación de Web SDK al actualizar a Customer Journey Analytics
description: Obtenga información acerca de las opciones de implementación de Web SDK al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Comprender las opciones de implementación de Web SDK al actualizar a Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Biblioteca JavaScript de Web SDK (alloy.js)"
>abstract="Incluya la biblioteca de SDK web (alloy.js) en todas las páginas del sitio."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Extensión de etiqueta de Web SDK"
>abstract="(Recomendado) Si aún no utiliza Etiquetas, instale el cargador de etiquetas en su sitio. Si ya está utilizando etiquetas, puede añadir la extensión Web SDK a la propiedad de etiquetas. Esta opción incluye implementaciones que utilizan etiquetas en la recopilación de datos de Adobe Experience Platform y sistemas de administración de etiquetas de terceros."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="Paquete NPM"
>abstract="Utilice la API de recopilación de datos para enviar datos directamente a un conjunto de datos. Se admiten los tipos no autenticados (cliente a servidor) y autenticados (servidor a servidor)."

<!-- markdownlint-enable MD034 -->

El proceso recomendado para actualizar de Adobe Analytics a Customer Journey Analytics es una nueva implementación de Experience Platform Web SDK, que es el método de recopilación de datos preferido de Customer Journey Analytics.

Existen tres formas compatibles de utilizar Adobe Experience Platform Web SDK:

* [Extensión de etiquetas Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): El Adobe recomienda utilizar este método. Instale un cargador de etiquetas en el sitio y, a continuación, utilice la IU de recopilación de datos de Adobe Experience Platform para configurar la implementación.

* [Biblioteca Web SDK JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Haga referencia a un archivo de biblioteca alojado en CDN o aloje el archivo de biblioteca utilizando su propia infraestructura. Realice llamadas a la biblioteca dentro del código del sitio.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): instale Web SDK en su sitio mediante el administrador de paquetes NPM.

Para obtener más información, consulte [Información general sobre la instalación de Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) en la Guía de Experience Platform Web SDK.



