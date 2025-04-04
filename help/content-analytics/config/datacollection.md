---
title: Recopilación de datos de Content Analytics
description: Información general sobre cómo se recopilan los datos en Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: d4803af9b71ec245f6c4b20e92a4a4c99f235f00
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 1%

---

# Recopilación de datos de Content Analytics

{{release-limited-testing}}

Este artículo explica en detalle cómo Analytics de contenido recopila datos


## Definiciones

En el contexto de este artículo se utilizan las definiciones siguientes:

* **Experiencia**: Una experiencia se define como el contenido de texto de toda una página web. Para la recopilación de datos, Content Analytics registra el Experience ID que se basa en la dirección URL de la página. Posteriormente, el texto de la página se captura mediante el servicio de recuperación.
* **Experience ID**: Una combinación única de la dirección URL relevante (dirección URL base más cualquier parámetro que dirija el contenido de la página) y [versión de experiencia](manual.md#versioning).
   * Usted especifica, como parte de la [configuración](configuration.md), qué parámetros son relevantes para cualquier URL completa dada.
   * Puede definir el [identificador de versión](manual.md#versioning) que se usa.
* **Recurso**: Una imagen. Content Analytics registra la dirección URL del recurso.
* **ID de recurso**: La dirección URL del recurso.
* **URL relevante**: La URL base más cualquier parámetro que dirija el contenido de la página.


## Funcionalidad

La biblioteca Content Analytics recopila datos cuando:

* Content Analytics se incluye en la biblioteca de etiquetas que se carga en la página.
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

1. [Clic o vista grabada](#recorded-view-or-click).
1. [Un evento regular o específico (de comportamiento)](#regular-or-specific-behaviorial-event).

Content Analytics recopila datos de esta manera para reflejar esa secuencia, en lugar de recopilar una vista o un clic por separado para no recopilar el evento inmediatamente posterior a esa vista o clic. Esta forma de recopilar datos de análisis de contenido también reduce la cantidad de datos recopilados. recopilación de datos.

### Vista grabada o clic

Se registra una vista de recursos cuando:

* El recurso no se ha excluido por la configuración de la extensión de Content Analytics.
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


### Evento regular o específico (conductual)

Los déclencheur para activar un evento normal o específico (de comportamiento) en el contexto de Content Analytics son los siguientes:

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

Los datos de Content Analytics se recopilan en conjuntos de datos en Experience Platform, según esquemas de Content Analytics específicos. Los esquemas de referencia están disponibles públicamente:

* [Esquema de recursos digitales](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiencia digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema de contenido de evento de experiencia](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
