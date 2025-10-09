---
title: Recopilación de datos de análisis de contenido
description: Información general sobre cómo se recopilan los datos en Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: ht
source-wordcount: '622'
ht-degree: 100%

---

# Recopilación de datos de análisis de contenido

Este artículo explica en detalle cómo Content Analytics recopila datos

## Definiciones

En el contexto de este artículo se utilizan las definiciones siguientes:

* **Experiencia**: Una experiencia se define como el contenido de texto de toda una página web. Para la recopilación de datos, el análisis de contenido registra el Experience ID que se basa en la dirección URL de la página. Posteriormente, el texto de la página se captura mediante el servicio de recuperación.
* **Experience ID**: Una combinación única de la dirección URL relevante (dirección URL base más cualquier parámetro que dirija el contenido de la página) y [versión de experiencia](manual.md#versioning).
   * Usted especifica, como parte de la [configuración](configuration.md), qué parámetros son relevantes para cualquier URL completa dada.
   * Usted define un [identificador de versión](manual.md#versioning) para usar, de modo que recopile correctamente los cambios en sus experiencias.
* **Recurso**: Una imagen. El análisis de contenido registra la dirección URL del recurso.
* **ID de recurso**: La dirección URL del recurso.
* **URL relevante**: La URL base más cualquier parámetro que dirija el contenido de la página.


## Funcionalidad

Content Analytics requiere el SDK web de Experience Platform Edge Network para recopilar datos de evento de contenido. Esa recopilación de datos de evento se combina con la existente de los datos de evento de comportamiento a través de mecanismos como Experience Platform Edge Network (SDK web, API de servidor) o el conector de origen de Analytics (por ejemplo, mediante AppMeasurement).

La biblioteca Content Analytics recopila datos cuando:

* Content Analytics se incluye en la biblioteca de etiquetas que se carga en la página.
* La dirección URL de la página está configurada en la [extensión de Content Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, que forma parte de la biblioteca de etiquetas incluida.


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

1. [Clic o vista registrada](#recorded-view-or-click).
1. [Un activador para enviar un evento de Content Analytics](#trigger-to-send-a-content-analytics-event).

El análisis de contenido recopila datos de esta manera para reflejar esa secuencia, en lugar de recopilar una vista o un clic por separado de la recopilación del evento inmediatamente posterior a esa vista o clic. Esta forma de recopilar datos de Content Analytics también reduce la cantidad de datos recopilados.

### Vista registrada o clic

Se registra una vista de recursos cuando:

* La configuración de la extensión de análisis de contenido no ha excluido el recurso.
* El recurso está al 75 % en la vista.
* Ese recurso aún no se ha registrado para esta página.

Se registra un clic en el recurso cuando:

* Se ha visualizado el recurso.
* La configuración de la extensión de análisis de contenido no ha excluido el recurso.
* Un clic directamente en el recurso, que es un vínculo, que lleva a otra página.

Se registra una vista de experiencia cuando:

* Las experiencias están habilitadas en la configuración de Content Analytics.

Se registra un clic en la experiencia cuando:

* Cualquier clic se produce en un vínculo de la página para la que las experiencias están habilitadas.


### Activador para enviar un evento de Content Analytics

Para reducir el número de llamadas que salen de la página, Content Analytics recopila información, pero no la envía inmediatamente. La información de interacción de contenido se recopila y un evento que contiene esa información solo se envía cuando se produce uno de los siguientes activadores:

* Web SDK o AppMeasurement envían un evento.
* La visibilidad cambia a oculta, por ejemplo:
   * La página se descarga
   * Se cambia de pestaña
   * Se minimiza el explorador
   * Se cierra el explorador
   * Se bloquea la pantalla
* La dirección URL cambia, lo que da como resultado una dirección URL relevante modificada.
* Las vistas de recursos registradas y listas para enviar superan el número de 32.

>[!NOTE]
>
>Es muy probable que los eventos adicionales de Content Analytics afecten a cualquier definición de tasa de salida hacia otro sitio basada en el número de eventos en una sesión o una página.
>


## Esquemas

Los datos de análisis de contenido se recopilan en conjuntos de datos en Experience Platform, según esquemas de análisis de contenido específicos. Los esquemas de referencia están disponibles públicamente:

* [Esquema de recursos digitales](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de la experiencia digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema de contenido de evento de experiencia](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
