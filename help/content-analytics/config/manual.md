---
title: Configuración manual de Content Analytics
description: Cómo configurar Análisis de contenido manualmente
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 1%

---

# Configuración manual de Content Analytics

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Análisis de contenido. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}

Este artículo detalla las acciones manuales necesarias para activar o desactivar una configuración de análisis de contenido o para editar su implementación de análisis de contenido.

Las siguientes acciones de configuración manual están disponibles:

## Activar

Para activar una nueva configuración o los cambios realizados en una configuración existente:

1. Debe seguir el [flujo de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Solo cuando haya publicado correctamente la biblioteca de la propiedad Etiqueta que contiene la configuración de Análisis de contenido, se recopilarán los datos de Análisis de contenido de los dominios, las experiencias y los recursos que haya configurado.

1. Debe [instalar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) el código incrustado en el elemento `<head>` de las páginas en su entorno de desarrollo, ensayo o publicación, sujeto a los análisis de contenido.


## Desactivar

Para desactivar la recopilación de datos de análisis de contenido:

1. Elimine el [código incrustado](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) en el elemento `<head>` de las páginas de su entorno de desarrollo, ensayo o producción, sujeto a Content Analytics.
1. [Elimine](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) la propiedad de etiquetas asociada para la configuración de Análisis de contenido.



## Modificar

En general, debería usar el [asistente de configuración guiada](guided.md) para realizar cambios en su implementación.

También puede usar la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) en la propiedad Tag asociada a la configuración de Content Analytics para realizar cambios en los siguientes artefactos:

* [Flujo de datos y espacio aislado](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Debe comprobar que la zona protegida y el conjunto de datos que configuró en la extensión de Adobe Content Analytics ya están configurados para Content Analytics con la [configuración guiada](guided.md) en una fase anterior. Esta configuración garantiza que todos los artefactos necesarios estén disponibles.<br/><br/>También debe comprobar que las actualizaciones para zonas protegidas o flujos de datos no interfieren con otra configuración de Content Analytics que esté configurada para utilizar la misma zona protegida o flujos de datos.
  >

* [Filtrado de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  Puede editar las expresiones regulares para modificar la forma en que filtra páginas y recursos.


Después de realizar cambios en la extensión de Adobe Content Analytics, asegúrate de usar [flujo de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} para activar los cambios.



>[!MORELIKETHIS]
>
>[Configuración guiada](guided.md)
>[Resumen de publicación de etiquetas de recopilación de datos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Versiones

Si necesita crear versiones de sus experiencias de análisis de contenido, debe agregar una función global `adobe.getContentExperienceVersion` en las páginas que considere que son experiencias que desee analizar.

La función `adobe.getContentExperienceVersion` debe devolver una cadena como valor, que puede ser cualquier cosa que elija para identificar la versión. La versión se adjunta a la dirección URL del Experience ID.

Si la función no está presente o no se devuelve ningún valor desde la función, se utiliza el valor `NoVersion` como predeterminado.

### Ejemplo

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
