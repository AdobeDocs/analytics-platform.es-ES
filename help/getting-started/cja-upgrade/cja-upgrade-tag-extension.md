---
title: Creación de una propiedad de etiqueta y adición de la extensión del SDK web
description: Obtenga información sobre cómo crear una propiedad de etiqueta y añadir la extensión del SDK web
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
autotag-review: '2026-05-19T08:18:58.656Z'
TQID: 'https://experienceleague.adobe.com/8Wld534ijt7cmJnlbq4cB7tURTb8hch99Z6FIrhzAcQ'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9efc51843684b8cad96d01f7ada99eafc5950b42
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 92%

---

# Añada la extensión del SDK web a la etiqueta {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Añada la extensión del SDK web de Platform a su propiedad de etiqueta"
>abstract="Añada la extensión del SDK web de Adobe Experience Platform a su propiedad de etiqueta Añadir la extensión del SDK web a la propiedad de etiquetas es más sencillo y solo le llevará unos minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Utilice la función Etiquetas de Adobe Experience Platform a fin de implementar código en el sitio para recopilar datos. Esta solución de administración de etiquetas le permite implementar código de junto con otros requisitos de etiquetado. Las etiquetas ofrecen una integración perfecta con Adobe Experience Platform mediante la extensión del SDK web de Adobe Experience Platform.

En la siguiente información se describe cómo añadir la extensión del SDK web a la etiqueta. Para obtener información adicional, consulte [Configuración de la extensión de la etiqueta del SDK web](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) en la documentación de Experience Platform. Web SDK incluye el servicio de identidad de Experience Platform, por lo que no es necesario agregar la extensión del [!UICONTROL Servicio de Experience Cloud ID] a su etiqueta.

Después de [crear una etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), debe configurarla con la extensión del SDK web de Adobe Experience Platform. Esto garantiza que se puedan enviar datos a Adobe Experience Platform (a través de la secuencia de datos).

Para añadir la extensión del SDK web a la etiqueta:

1. Inicie sesión en experience.adobe.com con sus credenciales de Adobe ID.

1. En Adobe Experience Platform, vaya a **[!UICONTROL Recopilación de datos]** > **[!UICONTROL Etiquetas]**.

1. Seleccione la etiqueta recién creada de la lista de [!UICONTROL Propiedades de la etiqueta] para abrirla.

1. Seleccione **[!UICONTROL Extensiones]** en el carril izquierdo.

1. Seleccione **[!UICONTROL Catálogo]** en la barra superior.

1. Busque o desplácese hasta la **[!UICONTROL extensión del SDK web de Adobe Experience Platform]** y seleccione **[!UICONTROL Instalar]** para instalarla.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Seleccione la zona protegida y la secuencia de datos que ha creado anteriormente para su [!UICONTROL Entorno de producción], (opcionalmente) su [!UICONTROL Entorno de ensayo] y su [!UICONTROL Entorno de desarrollo].

   ![Configuración de la extensión del SDK web de AEP](assets/aepwebsk-extension-datastreams.png)

1. Seleccione **[!UICONTROL Guardar]**.

{{upgrade-final-step}}
