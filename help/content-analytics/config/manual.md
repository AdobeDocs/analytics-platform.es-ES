---
title: Configuración manual de Content Analytics
description: Cómo configurar Content Analytics manualmente
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: cf8b14590a99573815c95e863fd26ae5b4244754
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Configuración manual de Content Analytics

{{release-limited-testing}}

Este artículo detalla las acciones manuales necesarias para iniciar o detener la recopilación de datos de una configuración de Content Analytics o para editar la implementación de Content Analytics.

Las siguientes acciones de configuración manual están disponibles:

## Iniciar recopilación de datos

Para iniciar la recopilación de datos para una configuración de Content Analytics implementada:

1. Siga el [flujo de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. La biblioteca de la propiedad Etiquetas que contiene la configuración de Content Analytics se ha publicado correctamente.

1. [Instale](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) el código incrustado en el elemento `<head>` de las páginas en su entorno de desarrollo, ensayo o publicación, sujeto a Content Analytics.


## Detener la recopilación de datos

Para detener la recopilación de datos de una configuración de Content Analytics implementada:

1. Elimine el [código incrustado](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) en el elemento `<head>` de las páginas de su entorno de desarrollo, ensayo o producción, sujeto a Content Analytics.
1. [Eliminar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) la propiedad de etiquetas asociada para la configuración de Content Analytics.



## Modificación de la recopilación de datos

Puede realizar algunos cambios menores en una configuración implementada mediante el [asistente de configuración guiada](guided.md). Por ejemplo, cambiar la vista de datos o habilitar o deshabilitar experiencias.

Utilice la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) en la propiedad Tags asociada con la configuración de Content Analytics para realizar cambios en los siguientes artefactos:

* [Flujo de datos y espacio aislado](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Compruebe que la zona protegida y la secuencia de datos que configuró en la extensión de Adobe Content Analytics ya estén configuradas para Content Analytics mediante la [configuración guiada](guided.md) en una fase anterior. Esta configuración garantiza que todos los artefactos necesarios estén disponibles.<br/><br/>Compruebe también que las actualizaciones para zonas protegidas o flujos de datos no interfieran con otra configuración de Content Analytics configurada para utilizar la misma zona protegida o flujos de datos.
  >

* [Captura y definición de experiencia](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Puede habilitar o deshabilitar las experiencias y editar las combinaciones de expresión regular y parámetros de consulta para determinar cómo se procesa el contenido en el sitio web.

* [Filtrado de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  Puede editar las expresiones regulares para modificar la forma en que filtra páginas y recursos.


Después de realizar cambios en la extensión de Adobe Content Analytics, asegúrese de usar [flujo de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} para iniciar la recopilación de datos en función de los cambios realizados.



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
