---
title: 'Información sobre las opciones de implementación del SDK web al actualizar a Customer Journey Analytics '
description: Obtenga información sobre las opciones de implementación del SDK web al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '350'
ht-degree: 100%

---

# Información sobre las opciones de implementación del SDK web al actualizar a Customer Journey Analytics  {#web-sdk-implementation-options}

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
