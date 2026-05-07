---
title: Recopilación de datos de Content Analytics
description: Información general sobre cómo se recopilan los datos en Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: a593221a9eb81d747777aedb323fd44a32c470be
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 53%

---

# Recopilación de datos de Content Analytics

Este artículo explica en detalle cómo Content Analytics recopila datos

## Definiciones

En el contexto de este artículo se utilizan las definiciones siguientes:

* **Experiencia**:
   * Para el canal **web**, una experiencia se define como el contenido de texto de una página web completa. Para la recopilación de datos, Content Analytics registra el Experience ID que se basa en la dirección URL de la página. Posteriormente, el texto de la página se captura mediante el servicio de recuperación.
   * Para el canal **mobile**, se define y rastrea una experiencia en la aplicación móvil con la extensión Content Analytics para Adobe Experience Platform Mobile SDK.
* **Experience ID**:
   * Para el canal web, el ID de experiencia es una combinación única de la URL relevante (URL base más cualquier parámetro que dirija el contenido de la página) y [versión de experiencia](manual.md#versioning).
      * Usted especifica, como parte de la [configuración](configuration.md), qué parámetros son relevantes para cualquier URL completa dada.
      * Usted define un [identificador de versión](manual.md#versioning) para usar, de modo que recopile correctamente los cambios en sus experiencias.
   * Para el canal **mobile**, el ID de experiencia es el valor devuelto por el uso de la llamada a la API `registerExperience`.
* **Recurso**: Una imagen. Content Analytics registra la dirección URL del recurso.
* **ID de recurso**: La dirección URL del recurso.
* **URL relevante**: La URL base más cualquier parámetro que dirija el contenido de la página.


## Funcionalidad

Content Analytics requiere Experience Platform Edge Network Web SDK (para el canal web) y Experience Platform Edge Network Mobile SDK (para el canal móvil) para recopilar datos de evento de contenido. Estos datos de evento se combinan con los datos de comportamiento existentes mediante Experience Platform Edge Network (Web SDK, Mobile SDK o la API de servidor) o un conector de origen de Analytics, como Adobe AppMeasurement.

La biblioteca Content Analytics recopila datos cuando:

* Content Analytics se incluye en la biblioteca de etiquetas que se carga en la página o se utiliza en la aplicación móvil.
* La URL de la página y la URL del recurso están configuradas en la [extensión web de Content Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, que forma parte de la biblioteca de etiquetas incluida.
* La dirección URL del recurso, la ubicación del recurso o la ubicación de la experiencia no se excluyen en la [extensión móvil de Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).


## Evento de Content Analytics

Esta sección detalla los eventos específicos de Content Analytics web. Consulte [Seguimiento de experiencias](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/) para obtener más información sobre los eventos de Content Analytics móvil.
Un evento de Content Analytics consta de:

* Campos estándar
   * Marca de tiempo
   * Identidad
* Vistas de experiencias (si las hay, y si están configuradas)
* Clics en experiencias (si los hay y si están configurados)
* Vistas de recursos (si las hay y si están configuradas)
* Clics en recursos (si los hay y si están configurados)

Los eventos de Content Analytics se recopilan como una secuencia de:

1. [clic o vista grabada](#recorded-view-or-click).
1. Un [déclencheur para enviar un evento de Content Analytics](#trigger-to-send-a-content-analytics-event).

El análisis de contenido recopila datos de esta manera para reflejar esa secuencia, en lugar de recopilar una vista o un clic por separado de la recopilación del evento inmediatamente posterior a esa vista o clic. Esta forma de recopilar datos de Content Analytics también reduce la cantidad de datos recopilados.

### Vista registrada o clic

Se registra una vista de recursos cuando:

* La configuración de la extensión de Content Analytics no ha excluido el recurso.
* El recurso está al 75 % en la vista.
* Ese recurso aún no se ha registrado para esta página.

Se registra un clic en el recurso cuando:

* Se ha visualizado el recurso.
* La configuración de la extensión de Content Analytics no ha excluido el recurso.
* Un clic directamente en el recurso, que es un vínculo, lleva a otra página.

Se registra una vista de experiencia cuando:

* Las experiencias están habilitadas en la configuración de Content Analytics.

Se registra un clic en la experiencia cuando:

* Cualquier clic en un vínculo habilitado déclencheur una experiencia.


### Activador para enviar un evento de Content Analytics

Para reducir el número de solicitudes de red enviadas desde la página, Content Analytics recopila información, pero no la envía inmediatamente. La información de interacción de contenido se recopila y un evento que contiene esa información solo se envía cuando se produce uno de los siguientes activadores:

* Web SDK o Adobe AppMeasurement envían un evento.
* La visibilidad cambia a oculta, por ejemplo:
   * La página se descarga
   * Se cambia de pestaña
   * Se minimiza el explorador
   * Se cierra el explorador
   * Se bloquea la pantalla
* La dirección URL cambia, lo que da como resultado una dirección URL relevante modificada.
* Las vistas de recursos registradas y listas para enviar superan las 32.

>[!NOTE]
>
>Es muy probable que los eventos adicionales de Content Analytics afecten a cualquier definición de tasa de salida hacia otro sitio basada en el número de eventos en una sesión o una página.
>

## Identidades

En esta sección se explica cómo gestiona Content Analytics las identidades.

### Web

Content Analytics administra las identidades del canal web de la siguiente manera:

* ECID se rellena automáticamente en la parte `identityMap` del esquema de Content Analytics.
* Si necesita otros valores de identidad en `identityMap`, debe establecer estos valores en la llamada de retorno `onBeforeEventSend` dentro de la extensión del SDK web.
* No se admite la vinculación basada en campos porque el esquema es propiedad del sistema. Por lo tanto, no se puede añadir otro campo al esquema para admitir la vinculación basada en el campo


Para asegurarse de que los datos de identidad de Content Analytics y los datos de identidad de Web SDK se vinculan correctamente en el nivel de campo, modifique la llamada de retorno de Web SDK [en antes del envío de evento](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"}.

1. Vaya a la propiedad **[!UICONTROL Etiquetas]** que contiene las extensiones del SDK web de Adobe Experience Platform y de Adobe Content Analytics.
1. Seleccione ![Complemento](/help/assets/icons/Plug.svg) **[!UICONTROL Extensiones]**.
1. Seleccione la extensión del **[!UICONTROL SDK web de Adobe Experience Platform]**.
1. Seleccione **[!UICONTROL Configurar]**.
1. En la sección **[!UICONTROL Instancias de SDK]**, desplácese hacia abajo hasta **[!UICONTROL Recopilación de datos]** - **[!UICONTROL Activada antes de la devolución de llamada de envío de evento]**.

   ![Activada antes de la devolución de llamada de envío de evento](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Seleccione **[!UICONTROL &lt;/> Proporcionar antes del código de devolución de llamada de envío de evento]**.
1. Añada el siguiente código:

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Activada antes de la devolución de llamada de envío de evento](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Seleccione **[!UICONTROL Guardar]** para guardar el código.
1. Seleccione **[!UICONTROL Guardar]** para guardar la extensión.
1. [Publique](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview) las actualizaciones de su propiedad Etiquetas.


### Móvil

Consulte la [extensión del servicio de identidad para Experience Cloud ID](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/) y la [extensión móvil de identidad para Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) para obtener más información sobre cómo trabajar con identidades en su aplicación móvil.

Tan pronto como cambie la identidad en la aplicación móvil, se restablecerá el [lote](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings) actual de datos de Content Analytics para iniciar una nueva recopilación de datos de Content Analytics para la nueva identidad.

## Esquemas

Experience Platform recopila datos de Content Analytics en conjuntos de datos basados en esquemas de Content Analytics específicos. Los esquemas de referencia están disponibles públicamente:

* [Esquema de recursos digitales](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiencia digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema de contenido de evento de experiencia](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
