---
title: Configuración manual de Content Analytics
description: Cómo configurar Content Analytics manualmente
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%

---

# Configuración manual de Content Analytics

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Content Analytics. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}

Este artículo detalla las acciones manuales necesarias para activar o desactivar una configuración de Content Analytics o para editar la implementación de Content Analytics.

Las siguientes acciones de configuración manual están disponibles:

## Activar

Para activar una nueva configuración o los cambios realizados en una configuración existente:

1. Debe seguir el [flujo de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. La biblioteca de la propiedad Etiquetas que contiene la configuración de Content Analytics se ha publicado correctamente. Solo entonces se recopilan los datos de Content Analytics de los dominios, las experiencias y los recursos que ha configurado.

1. Debe [instalar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) el código incrustado en el elemento `<head>` de las páginas en su entorno de desarrollo, ensayo o publicación, sujeto a Content Analytics.


## Desactivar

Para desactivar la recopilación de datos de análisis de contenido:

1. Elimine el [código incrustado](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) en el elemento `<head>` de las páginas de su entorno de desarrollo, ensayo o producción, sujeto a Content Analytics.
1. [Eliminar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) la propiedad de etiquetas asociada para la configuración de Content Analytics.



## Modificar

Puede realizar algunos cambios menores en una configuración implementada mediante el [asistente de configuración guiada](guided.md). Por ejemplo, cambie la vista de datos.

Utilice la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) en la propiedad Tags asociada con la configuración de Content Analytics para realizar cambios en los siguientes artefactos:

* [Flujo de datos y espacio aislado](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Compruebe que la zona protegida y la secuencia de datos que configuró en la extensión de Adobe Content Analytics ya estén configuradas para Content Analytics mediante la [configuración guiada](guided.md) en una fase anterior. Esta configuración garantiza que todos los artefactos necesarios estén disponibles.<br/><br/>Compruebe también que las actualizaciones para zonas protegidas o flujos de datos no interfieran con otra configuración de Content Analytics configurada para utilizar la misma zona protegida o flujos de datos.
  >

* [Filtrado de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  Puede editar las expresiones regulares para modificar la forma en que filtra páginas y recursos.


Después de realizar cambios en la extensión de Adobe Content Analytics, asegúrese de usar [flujo de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} para activar los cambios.



>[!MORELIKETHIS]
>
>[Configuración guiada](guided.md)
>[Resumen de publicación de etiquetas de recopilación de datos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Versiones

Si necesita crear versiones de las experiencias de Content Analytics, debe agregar una función global `adobe.getContentExperienceVersion` en las páginas que considere que son experiencias que desea analizar.

La función `adobe.getContentExperienceVersion` debe devolver una cadena como valor, que puede ser cualquier cosa que elija, para identificar la versión. La versión se agregó a la [URL del Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Si la función no está presente o no se devuelve ningún valor desde la función, se utiliza el valor `NoVersion` como predeterminado.

### Ejemplo

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
