---
title: Configuración manual de Content Analytics
description: Cómo configurar Análisis de contenido manualmente
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

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

Para activar una nueva configuración o los cambios que has realizado en una configuración existente, debes [publicar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} la propiedad de etiqueta asociada. Solo al publicar la propiedad de etiquetas de análisis de contenido, se recopilan datos de análisis de contenido para los dominios, la experiencia y los recursos que ha configurado.


## Desactivar

Para desactivar la recopilación de datos de análisis de contenido, [cancelar la publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} de la propiedad de etiquetas asociada para la configuración de Análisis de contenido.



## Modificar

En general, debería usar el [asistente de configuración guiada](guided.md) para realizar cambios en su implementación.

También puede utilizar la extensión de Adobe Content Analytics en la propiedad Tag asociada a la configuración de Content Analytics para realizar cambios en los siguientes artefactos:

* [Flujo de datos y espacio aislado](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Debe comprobar que la zona protegida y el conjunto de datos que configuró en la extensión de Adobe Content Analytics ya están configurados para Content Analytics con la [configuración guiada](guided.md) en una fase anterior. Esta configuración garantiza que todos los artefactos necesarios estén disponibles.<br/><br/>También debe comprobar que las actualizaciones para zonas protegidas o flujos de datos no interfieren con otra configuración de Content Analytics que esté configurada para utilizar la misma zona protegida o flujos de datos.
  >

* [Filtrado de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}.

  Puede editar las expresiones regulares para modificar la forma en que filtra páginas y recursos.


Después de realizar cambios en la extensión de Adobe Content Analytics, asegúrate de [activar](#activate) los cambios.



>[!MORELIKETHIS]
>
>[Configuración guiada](guided.md)
>[Resumen de publicación de etiquetas de recopilación de datos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>