---
title: Recopilación de datos de Content Analytics
description: Información general sobre cómo se recopilan los datos en Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 02d24416bd1f56417005dfa1b693964073fb8a59
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 1%

---

# Recopilación de datos de Content Analytics

{{release-limited-testing}}

Este artículo explica en detalle cómo Analytics de contenido recopila datos


## Definiciones

En el contexto de este artículo se utilizan las definiciones siguientes:

* **Experiencia**: Una experiencia se define como el texto contenido en todo un Página web. Por recopilación de datos, el Analytics de contenido registra el ID de experiencia que se basa en la URL Página. Posteriormente, el texto del Página se captura mediante el servicio de recuperación.
* **ID** de experiencia: una combinación única de URL relevantes (URL base más cualquier parámetro que dirigir contenido en el Página) y [experiencia versión](manual.md#versioning).
   * Usted especifica, como parte de la [configuración](configuration.md), qué parámetros son relevantes para cualquier URL completa dada.
   * Puede definir el [identificador de versión](manual.md#versioning) que se usa.
* **Recurso**: Una imagen. El Analytics de contenido registra el URL recurso.
* **ID del recurso**: el URL del recurso.
* **URL** relevante: La URL base más los parámetros que dirigir contenido en el Página.


## Funcionalidad

El biblioteca Content Analytics recopila datos cuando:

* El contenido Analytics se incluye en el biblioteca Tags que se carga en el Página.
* La dirección URL de la página está configurada en la [extensión Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, que forma parte de la biblioteca de etiquetas incluida.


## Evento de Content Analytics

Un evento de Content Analytics consta de:

* Campos estándar
   * Marca de tiempo
   * Identidad
* Vistas de experiencias (si las hay, y si están configuradas)
* Clics en experiencias (si los hay y si están configurados)
* Vistas de recursos (si las hay y si están configuradas)
* Clics en recursos (si los hay y si están configurados)


Los eventos de Content Analytics se recopilan como una secuencia de:

1. [Un vista o clic](#recorded-view-or-click) registrado.
1. [Un evento](#regular-or-specific-behaviorial-event) regular o específico (conductual).

Content Analytics recopila datos de esta manera para reflejar esa secuencia, en lugar de recopilar una vista o un clic por separado para no recopilar el evento inmediatamente posterior a esa vista o clic. Esta forma de recopilar datos de análisis de contenido también reduce la cantidad de datos recopilados.

### Vista grabada o clic

Se registra una vista de recursos cuando:

* El recurso no se ha excluido por la configuración de la extensión de Content Analytics.
* El recurso es del 75% en vista.
* Ese recurso no se ha registrado ya para este Página.

Un clic recurso se registra cuando:

* Se ha visto el recurso.
* El recurso no se ha excluido por la configuración de la extensión de Content Analytics.
* Un clic directamente en el recurso, que es un vínculo, que lleva a otra página.

Se registra una vista de experiencia cuando:

* Las experiencias están habilitadas en la configuración de Content Analytics.

Se registra un clic en la experiencia cuando:

* Cualquier clic se produce en un vínculo de la página para la que las experiencias están habilitadas.


### evento regulares o específicos (conductuales)

Los activadores para activar un evento regular o específico (conductual) en el contexto de la Analytics de contenido son:

* Web SDK o AppMeasurements envía un evento.
* Visibilidad cambios en oculta, por ejemplo:
   * Descargas de página
   * Cambiar pestaña
   * Minimizar explorador
   * Cerrar explorador
   * Pantalla de bloqueo
* El URL cambia, lo que da como resultado una modificación del URL relevante.
* Las vistas de recursos grabadas y listas para enviar superan el número de 32.


## Esquemas

Los datos de Content Analytics se recopilan en conjuntos de datos en Experience Platform, según esquemas de Content Analytics específicos. Los esquemas de referencia están disponibles públicamente:

* [Esquema de recursos digitales](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiencia digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema de contenido de evento de experiencia](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
