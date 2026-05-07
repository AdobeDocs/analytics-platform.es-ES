---
title: Configuración manual de Content Analytics
description: Obtenga información sobre cómo configurar Content Analytics manualmente.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: b8b0237a092b37d28bec56bba05c30a853097d4f
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 62%

---


# Configuración manual de Content Analytics

Este artículo detalla las acciones manuales necesarias para iniciar o detener la recopilación de datos de una configuración de Content Analytics o para editar la implementación de Content Analytics.

Las opciones de configuración disponibles son las siguientes:

## Iniciar la recopilación de datos

Para iniciar la recopilación de datos para una configuración de Content Analytics implementada:

1. Siga el [flujo de publicación](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview){target="_blank"}. La biblioteca de las propiedades de etiquetas que contiene la configuración de Content Analytics se ha publicado correctamente.

1. En función de los canales que haya configurado:

   * Para **web**: [Instale](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/environments/environments#installation) el código incrustado en el elemento `<head>` de las páginas en su entorno de desarrollo, ensayo o publicación, sujeto a Content Analytics.
   * Para **mobile**: consulte la [guía de extensión de Adobe Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) específica de la solución en la [documentación de Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/) sobre cómo configurar e instrumentar su aplicación móvil para Content Analytics.

## Detener la recopilación de datos

Para detener la recopilación de datos de una configuración de Content Analytics implementada, según los canales que haya configurado:

* Para **web**:

   1. Elimine el [código incrustado](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/environments/environments) en el elemento `<head>` de las páginas de su entorno de producción, desarrollo o ensayo, sujeto a Content Analytics.
   1. Elimine la propiedad de etiquetas web asociada para la configuración de Content Analytics.

* Para **mobile**:

   1. Elimine la [extensión de Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) de su aplicación.
   1. Elimine la propiedad de etiquetas móviles asociada a su configuración de Content Analytics.

Siga el [flujo de publicación](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview){target="_blank"} para aplicar los cambios.


## Modificar la recopilación de datos

Puede realizar algunos cambios menores en una configuración implementada mediante el [asistente de configuración guiada](guided.md). Por ejemplo, cambiar la vista de datos o habilitar o deshabilitar experiencias.


### Web

Utiliza la [extensión web de Adobe Content Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview) en la propiedad Tags asociada con la configuración de Content Analytics para realizar cambios en los siguientes artefactos:

* [Zona protegida y secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Compruebe que la zona protegida y la secuencia de datos que configuró en la extensión de Adobe Content Analytics ya estén configuradas para Content Analytics mediante la [configuración guiada](guided.md) en una fase anterior. Esta configuración garantiza que todos los artefactos necesarios estén disponibles.<br/><br/>Compruebe también que las actualizaciones para zonas protegidas o flujos de datos no interfieran con otra configuración de Content Analytics configurada para utilizar la misma zona protegida o flujos de datos.
  >

* [Captura y definición de experiencias](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Puede habilitar o deshabilitar las experiencias y editar las combinaciones de expresión regular y parámetros de consulta para determinar cómo se procesa el contenido en el sitio web.

* [Segmentación de eventos](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Puede editar las expresiones regulares para modificar la forma en que segmenta las páginas y los recursos.


Después de realizar cambios en la extensión web de Adobe Content Analytics, use el [flujo de publicación](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview){target="_blank"} para empezar a recopilar datos.


### Móvil

Para realizar cambios adicionales, usa la [extensión móvil de Adobe Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) en la propiedad Etiquetas asociada a la configuración de Content Analytics.

Después de realizar cambios en la extensión web de Adobe Content Analytics, use el [flujo de publicación](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview){target="_blank"} para empezar a recopilar datos.


## Versiones

>[!NOTE]
>
>Esta sección solo se aplica a Content Analytics para el canal Web.


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

>[!MORELIKETHIS]
>
>[Configuración guiada](guided.md)
>[Información general sobre publicación de etiquetas de recopilación de datos](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview)
>
