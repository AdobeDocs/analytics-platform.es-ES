---
title: Configuración manual del análisis de contenido
description: Cómo configurar manualmente el análisis de contenido
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 67%

---

# Configuración manual del análisis de contenido

Este artículo detalla las acciones manuales necesarias para iniciar o detener la recopilación de datos de una configuración de análisis de contenido o para editar la implementación del análisis de contenido.

Las opciones de configuración disponibles son las siguientes:

## Iniciar la recopilación de datos

Para iniciar la recopilación de datos para una configuración de Content Analytics implementada:

1. Siga el [flujo de publicación](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview){target="_blank"}. La biblioteca de la propiedad Etiquetas que contiene la configuración de Content Analytics se ha publicado correctamente.

1. [Instale](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/environments/environments#installation) el código incrustado en el elemento `<head>` de las páginas en su entorno de desarrollo, ensayo o publicación, sujeto a Content Analytics.


## Detener la recopilación de datos

Para detener la recopilación de datos de una configuración de Content Analytics implementada:

1. Elimine el [código incrustado](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/environments/environments) en el elemento `<head>` de las páginas de su entorno de producción, desarrollo o ensayo, sujeto al análisis de contenido.
1. [Elimine](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview) la propiedad Etiquetas asociada a la configuración del análisis de contenido.



## Modificar la recopilación de datos

Puede realizar algunos cambios menores en una configuración implementada mediante el [asistente de configuración guiada](guided.md). Por ejemplo, cambiar la vista de datos o habilitar o deshabilitar experiencias.

Utilice la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview) en la propiedad Etiquetas asociada con la configuración de Content Analytics para realizar cambios en los siguientes artefactos:

* [Zona protegida y secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Compruebe que la zona protegida y la secuencia de datos que configuró en la extensión de Adobe Content Analytics ya estén configuradas para Content Analytics mediante la [configuración guiada](guided.md) en una fase anterior. Esta configuración garantiza que todos los artefactos necesarios estén disponibles.<br/><br/>Compruebe también que las actualizaciones para zonas protegidas o flujos de datos no interfieran con otra configuración de Content Analytics configurada para utilizar la misma zona protegida o flujos de datos.
  >

* [Captura y definición de experiencias](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Puede habilitar o deshabilitar las experiencias y editar las combinaciones de expresión regular y parámetros de consulta para determinar cómo se procesa el contenido en el sitio web.

* [Segmentación de eventos](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Puede editar las expresiones regulares para modificar la forma en que segmenta páginas y recursos.


Después de realizar cambios en la extensión de Adobe Content Analytics, asegúrese de usar el [flujo de publicación](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview){target="_blank"} para iniciar la recopilación de datos en función de los cambios realizados.



>[!MORELIKETHIS]
>
>[Configuración guiada](guided.md)
>&#x200B;>[Información general sobre publicación de etiquetas de recopilación de datos](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview)
>


## Versiones

Si desea recopilar experiencias de Content Analytics, debe considerar implementar el control de versiones para garantizar que las nuevas experiencias (cambios en la página web) se recopilen correctamente.

Para implementar el control de versiones, añada una función global `adobe.getContentExperienceVersion` en las páginas que considere experiencias que desee analizar.

La función `adobe.getContentExperienceVersion` debe devolver una cadena como valor, que puede ser cualquier cosa que elija, para identificar la versión. La versión se añadió a la [URL de Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Si la función no está presente o no se devuelve ningún valor desde la función, se utiliza el valor `NoVersion` como predeterminado.

### Ejemplo

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

## Identidades

Content Analytics gestiona las identidades de la siguiente manera:

* ECID se rellena automáticamente en la parte `identityMap` del esquema de Content Analytics.
* Si necesita otros valores de identidad en `identityMap`, debe establecer estos valores en la llamada de retorno `onBeforeEventSend` dentro de la extensión Web SDK.
* No se admite la vinculación basada en campos porque el esquema es propiedad del sistema. Por lo tanto, no se puede agregar otro campo al esquema para admitir la vinculación basada en el campo


Para asegurarse de que los datos de identidad de Content Analytics y los datos de identidad de Adobe Experience Platform Web SDK se vinculen correctamente en el nivel de campo, debe realizar modificaciones en Web SDK [en antes de la devolución de llamada de evento](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"}.

1. Vaya a la propiedad **[!UICONTROL Tags]** que contiene la extensión Adobe Experience Platform Web SDK y la extensión Adobe Content Analytics.
1. Seleccionar ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Extensiones]**.
1. Seleccione la extensión **[!UICONTROL Adobe Experience Platform Web SDK]**.
1. Seleccione **[!UICONTROL Configurar]**.
1. En la sección **[!UICONTROL Instancias de SDK]**, desplácese hacia abajo hasta **[!UICONTROL Recopilación de datos]** - **[!UICONTROL Activada antes de la devolución de llamada de envío de evento]**.

   ![Activado antes de la devolución de llamada de envío de evento](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Seleccione **[!UICONTROL &lt;/> Proporcionar antes del código de devolución de llamada de envío de evento]**.
1. Añada el siguiente código:

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Activado antes de la devolución de llamada de envío de evento](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Seleccione **[!UICONTROL Guardar]** para guardar el código.
1. Seleccione **[!UICONTROL Guardar]** para guardar la extensión.
1. [Publicar](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview) las actualizaciones de su propiedad Etiquetas.





