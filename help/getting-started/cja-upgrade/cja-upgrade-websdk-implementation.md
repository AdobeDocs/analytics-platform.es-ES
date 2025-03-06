---
title: Descripción de las opciones de implementación del SDK web al actualizar a Customer Journey Analytics
description: Obtenga información acerca de las opciones de implementación de Web SDK al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ac7059e76797b14c00993a2a46aa51b1ebfe6a2
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 38%

---

# Descripción de las opciones de implementación del SDK web al actualizar a Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Biblioteca JavaScript del SDK web (alloy.js)"
>abstract="Incluya la biblioteca del SDK web (alloy.js) en todas las páginas del sitio."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Extensión de la etiqueta del SDK web"
>abstract="(Recomendado) Si aún no utiliza Etiquetas, instale el cargador de etiquetas en su sitio. Si ya está utilizando etiquetas, puede añadir la extensión del SDK web a la propiedad de etiqueta. Esta opción incluye implementaciones que utilizan etiquetas en la recopilación de datos de Adobe Experience Platform y sistemas de administración de etiquetas de terceros."

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
>title="Implemente el SDK web para su propiedad determinada"
>abstract="Seleccione el tipo de implementación deseado en el cuestionario para obtener instrucciones más detalladas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Añada la biblioteca de SDK web a su sistema de administración de etiquetas de terceros"
>abstract="Trabaje con el administrador sobre el sistema de administración de etiquetas para agregar la biblioteca de Web SDK al sitio.<br><br>El tiempo de finalización de esta tarea depende en gran medida de la capacidad de respuesta de la persona responsable de su sistema de administración de etiquetas. La adición de la biblioteca Web SDK puede agruparse con la lógica de implementación asociada e implementarse durante los ciclos de lanzamiento estándar de su organización."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

El proceso recomendado para actualizar de Adobe Analytics a Customer Journey Analytics es una nueva implementación de Experience Platform Web SDK, que es el método de recopilación de datos preferido para Customer Journey Analytics.

Existen tres formas compatibles de utilizar Adobe Experience Platform Web SDK:

* [Extensión de etiquetas Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): Adobe recomienda utilizar este método. Instale un cargador de etiquetas en el sitio y, a continuación, utilice la IU de recopilación de datos de Adobe Experience Platform para configurar la implementación.

* [Biblioteca Web SDK JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Haga referencia a un archivo de biblioteca alojado en CDN o aloje el archivo de biblioteca utilizando su propia infraestructura. Realice llamadas a la biblioteca dentro del código del sitio.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): instale Web SDK en su sitio mediante el administrador de paquetes NPM.

Para obtener más información, consulte [Información general sobre la instalación de Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) en la Guía de Experience Platform Web SDK.



