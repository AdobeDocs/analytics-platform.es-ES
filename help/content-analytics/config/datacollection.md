---
title: Recopilación de datos de Content Analytics
description: Información general sobre cómo se recopilan los datos en Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d835411beba3d40f67d2f93ee76aa5eda6f45041
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---


# Recopilación de datos de Content Analytics

Este artículo explica en detalle cómo Analytics de contenido recopila datos


## Definiciones

En el contexto de este artículo se utilizan las definiciones siguientes:

* **Experiencia**: Una experiencia se define como el contenido de texto de toda una página web. Para la recopilación de datos, Content Analytics registra el Experience ID. Content Analytics no registra el texto de la página.
* **Recurso**: Una imagen. Content Analytics registra la dirección URL del recurso.
* **URL relevante**: La URL base más cualquier parámetro que dirija el contenido de la página.
* **Experience ID**: Una combinación única de la URL y la versión de la experiencia relevantes.
   * Usted especifica, como parte de la [configuración](configuration.md), qué parámetros son relevantes para cualquier URL completa dada.
   * Puede definir el [identificador de versión](manual.md#versioning) que se usa. Para la recopilación de datos, no se tiene en cuenta la versión. Solo se recopila la dirección URL correspondiente.

## Funcionalidad

La biblioteca Content Analytics recopila datos cuando:

* Content Analytics se incluye en la biblioteca de etiquetas que se carga en la página.
* La dirección URL de la página está configurada en la [extensión Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, que forma parte de la biblioteca de etiquetas incluida.


### Evento de Content Analytics

Un evento de Content Analytics consta de:

* Campos estándar
   * Marca de tiempo
   * Identidad
* Vistas de experiencias (si las hay, y si están configuradas)
* Clics en experiencias (si los hay y si están configurados)
* Vistas de recursos (si las hay y si están configuradas)
* Clics en recursos (si los hay y si están configurados)

#### Vistas o clics registrados

Se registra una vista de recursos cuando:

* El recurso no se ha excluido por la configuración de la extensión de ACA.
* El recurso está al 75% en la vista.
* Ese recurso aún no se ha registrado para esta página.

Se registra un clic en el recurso cuando:

* Se ha visto el recurso.
* El recurso no se ha excluido por la configuración de la extensión de ACA.
* Un clic directamente en el recurso, que es un vínculo, que lleva a otra página.

Se registra una vista de experiencia cuando:

* Las experiencias están habilitadas en la configuración de Content Analytics.

Se registra un clic en la experiencia cuando:

* Cualquier clic se produce en un vínculo de la página para la que las experiencias están habilitadas.


#### Eventos enviados

Los eventos de Content Analytics se envían cuando se dan las dos condiciones siguientes:

* El contenido se envía, lo que ocurre cuando:

   * Se registra una vista de recursos o un clic en.
   * Se registra una vista de experiencia o un clic.

* Se activa un déclencheur para enviar un evento, que se produce cuando:

   * Web SDK o AppMeasurement envían un evento.
   * La visibilidad cambia a oculta, por ejemplo:
      * Descargas de página
      * Pestaña Cambiar
      * Minimizar explorador
      * Cerrar explorador
      * Bloquear pantalla
   * La dirección URL cambia, lo que da como resultado una dirección URL relevante modificada.
   * Las vistas de recursos superan el límite de lotes de 32.


## Esquemas

Los datos de Content Analytics se recopilan en conjuntos de datos en Experience Platform, según esquemas de Content Analytics específicos. Los esquemas de referencia están disponibles públicamente y se utilizan en una implementación predeterminada de Content Analytics.

* [Esquema de recursos digitales](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiencia digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema de contenido de evento de experiencia](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
